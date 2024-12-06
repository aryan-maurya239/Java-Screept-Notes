### **Hoisting in JavaScript**

**Definition:**  
Hoisting is JavaScript's default behavior of moving declarations (variables, functions, and classes) to the top of their scope during the compilation phase, **before the code is executed**. This means you can use variables and functions even before they are declared in the code, though how they behave depends on how they were declared.

---

### **How Hoisting Works**
- JavaScript splits the code into two phases:
  1. **Compilation Phase:** Declarations (variables, functions, classes) are added to memory.
  2. **Execution Phase:** Code is executed line by line.

During the compilation phase:
- Variables and function declarations are "hoisted" to the top of their scope (global or block).
- **Only declarations are hoisted, not initializations.**

---

### **Hoisting with Variables**
#### 1. **Using `var`**
- Variables declared with `var` are hoisted to the top of their scope but are initialized with `undefined`.
- You can access the variable **before its declaration**, but its value will be `undefined` until it is explicitly assigned.

Example:
```javascript
console.log(a); // undefined (hoisted, but not initialized)
var a = 10;
console.log(a); // 10
```

What happens:
```javascript
// During compilation:
var a; // Declaration is hoisted
console.log(a); // undefined
a = 10; // Initialization happens during execution
```

#### 2. **Using `let` and `const`**
- Variables declared with `let` and `const` are hoisted but **not initialized**.  
- They remain in the **Temporal Dead Zone (TDZ)** until the code reaches their declaration. Accessing them before their declaration will throw a `ReferenceError`.

Example with `let`:
```javascript
console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 20;
console.log(b); // 20
```

Example with `const`:
```javascript
console.log(c); // ReferenceError: Cannot access 'c' before initialization
const c = 30;
console.log(c); // 30
```

What happens:
- The variable is hoisted, but it is not initialized. The **Temporal Dead Zone** exists from the start of the block until the declaration is encountered.

---

### **Hoisting with Functions**
#### 1. **Function Declarations**
- Function declarations are fully hoisted.
- Both the function's name and its body are hoisted to the top of their scope.  
- You can call the function **before it is defined** in the code.

Example:
```javascript
sayHello(); // Output: Hello!

function sayHello() {
  console.log('Hello!');
}
```

What happens:
```javascript
// During compilation:
function sayHello() {
  console.log('Hello!');
}
sayHello(); // Execution phase
```

#### 2. **Function Expressions**
- Function expressions (using `var`, `let`, or `const`) are not fully hoisted.  
- Only the variable declaration is hoisted, not the function itself.

Example with `var`:
```javascript
console.log(myFunc); // undefined
var myFunc = function() {
  console.log('Hello!');
};
myFunc(); // Output: Hello!
```

Example with `let` or `const`:
```javascript
console.log(myFunc); // ReferenceError
let myFunc = function() {
  console.log('Hello!');
};
myFunc();
```

---

### **Hoisting with Classes**
- Class declarations are hoisted but **not initialized**.
- Accessing a class before its declaration will throw a `ReferenceError`.

Example:
```javascript
const obj = new MyClass(); // ReferenceError: Cannot access 'MyClass' before initialization
class MyClass {
  constructor() {
    this.name = 'Class Example';
  }
}
```

What happens:
- The class declaration is hoisted to the top, but it remains in the **Temporal Dead Zone** until the code reaches its declaration.

---

### **Hoisting in Different Scopes**
#### 1. **Global Scope**
- Variables declared with `var` are hoisted globally.
- Variables declared with `let` and `const` are block-scoped, even in the global scope.

Example:
```javascript
console.log(a); // undefined
var a = 10;

console.log(b); // ReferenceError
let b = 20;

console.log(c); // ReferenceError
const c = 30;
```

#### 2. **Function Scope**
- Variables declared inside a function are hoisted to the top of the function.

Example:
```javascript
function test() {
  console.log(x); // undefined
  var x = 5;
}
test();
```

#### 3. **Block Scope**
- Variables declared with `let` and `const` are hoisted to the top of the block but remain in the TDZ.

Example:
```javascript
{
  console.log(a); // undefined
  var a = 10;

  console.log(b); // ReferenceError
  let b = 20;

  console.log(c); // ReferenceError
  const c = 30;
}
```

---

### **Temporal Dead Zone (TDZ)**
The **Temporal Dead Zone** is the time between entering the scope (block or function) and the actual declaration of the variable. Variables in the TDZ cannot be accessed and will throw a `ReferenceError`.

Key points about TDZ:
1. Applies to `let`, `const`, and classes.
2. Ends when the declaration is encountered during code execution.

Example:
```javascript
{
  // TDZ for b starts here
  console.log(b); // ReferenceError
  let b = 20; // TDZ ends here
  console.log(b); // 20
}
```

---

### **Best Practices to Avoid Issues with Hoisting**
1. **Always declare variables at the top of their scope** to make the code more readable and predictable.
   ```javascript
   var a = 10;
   let b = 20;
   const c = 30;
   ```

2. **Use `let` and `const` instead of `var`.**
   - They avoid unexpected behavior caused by `undefined` values and are block-scoped.

3. **Declare functions before calling them.**
   ```javascript
   function sayHello() {
     console.log('Hello!');
   }
   sayHello();
   ```

4. **Avoid relying on hoisting.**
   - Explicitly declare and initialize variables or functions before using them.

---

### **Summary Table**

| Feature             | `var`                   | `let` / `const`                  | Functions                      | Classes                      |
|---------------------|--------------------------|-----------------------------------|--------------------------------|------------------------------|
| **Hoisted?**        | Yes                     | Yes                              | Yes                           | Yes                         |
| **Initialization?** | `undefined`             | No (TDZ applies)                 | Fully initialized              | No (TDZ applies)            |
| **Errors?**         | No error, value is `undefined` | ReferenceError if accessed before declaration | No error (function body is hoisted) | ReferenceError if accessed before declaration |

Let me know if you'd like further details or examples!