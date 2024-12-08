Here’s a detailed guide to **JavaScript operators**, including their types, usage, and examples.

---

## **JavaScript Operators**

Operators are special symbols or keywords used to perform operations on variables, values, or data types. They are broadly classified into the following types:

### **1. Arithmetic Operators**
These are used to perform basic mathematical operations.

| Operator | Description              | Example         | Result       |
|----------|--------------------------|-----------------|--------------|
| `+`      | Addition                 | `5 + 3`         | `8`          |
| `-`      | Subtraction              | `5 - 3`         | `2`          |
| `*`      | Multiplication           | `5 * 3`         | `15`         |
| `/`      | Division                 | `6 / 3`         | `2`          |
| `%`      | Modulus (Remainder)      | `5 % 2`         | `1`          |
| `**`     | Exponentiation (ES6)     | `2 ** 3`        | `8`          |
| `++`     | Increment                | `let a = 5; a++`| `6` (postfix)|
| `--`     | Decrement                | `let a = 5; a--`| `4` (postfix)|

---

### **2. Assignment Operators**
Used to assign values to variables.

| Operator | Description              | Example         | Result       |
|----------|--------------------------|-----------------|--------------|
| `=`      | Assign                   | `x = 10`        | `x = 10`     |
| `+=`     | Add and assign            | `x += 5`        | `x = x + 5`  |
| `-=`     | Subtract and assign       | `x -= 5`        | `x = x - 5`  |
| `*=`     | Multiply and assign       | `x *= 5`        | `x = x * 5`  |
| `/=`     | Divide and assign         | `x /= 5`        | `x = x / 5`  |
| `%=`     | Modulus and assign        | `x %= 5`        | `x = x % 5`  |
| `**=`    | Exponentiate and assign   | `x **= 2`       | `x = x ** 2` |

---

### **3. Comparison Operators**
Used to compare two values and return a Boolean result.

| Operator | Description              | Example          | Result       |
|----------|--------------------------|------------------|--------------|
| `==`     | Equal to                 | `5 == '5'`       | `true`       |
| `===`    | Strict equal to          | `5 === '5'`      | `false`      |
| `!=`     | Not equal to             | `5 != 3`         | `true`       |
| `!==`    | Strict not equal to      | `5 !== '5'`      | `true`       |
| `>`      | Greater than             | `5 > 3`          | `true`       |
| `<`      | Less than                | `5 < 3`          | `false`      |
| `>=`     | Greater than or equal to | `5 >= 5`         | `true`       |
| `<=`     | Less than or equal to    | `5 <= 3`         | `false`      |

---

### **4. Logical Operators**
Used to perform logical operations.

| Operator | Description              | Example                  | Result       |
|----------|--------------------------|--------------------------|--------------|
| `&&`     | Logical AND              | `true && false`          | `false`      |
| `||`     | Logical OR               | `true || false`          | `true`       |
| `!`      | Logical NOT              | `!true`                  | `false`      |

---

### **5. Bitwise Operators**
Operate on binary representations of numbers.

| Operator | Description              | Example    | Binary      | Result |
|----------|--------------------------|------------|-------------|--------|
| `&`      | AND                     | `5 & 1`    | `0101 & 0001` | `0001` (1) |
| `|`      | OR                      | `5 | 1`    | `0101 | 0001` | `0101` (5) |
| `^`      | XOR                     | `5 ^ 1`    | `0101 ^ 0001` | `0100` (4) |
| `~`      | NOT                     | `~5`       | `~0101`       | `...1010` (-6) |
| `<<`     | Left shift              | `5 << 1`   | `0101 << 1`   | `1010` (10) |
| `>>`     | Right shift             | `5 >> 1`   | `0101 >> 1`   | `0010` (2)  |
| `>>>`    | Zero-fill right shift   | `5 >>> 1`  | `0101 >>> 1`  | `0010` (2)  |

---

### **6. String Operators**
Perform operations on strings.

| Operator | Description               | Example               | Result         |
|----------|---------------------------|-----------------------|----------------|
| `+`      | Concatenation             | `'Hello' + ' World'`  | `'Hello World'`|
| `+=`     | Concatenate and assign    | `str += ' World'`     | `str = str + ' World'` |

---

### **7. Type Operators**
Used to check or manipulate the type of values.

| Operator | Description               | Example            | Result         |
|----------|---------------------------|--------------------|----------------|
| `typeof` | Returns the type of value | `typeof 5`         | `'number'`     |
| `instanceof` | Checks instance        | `arr instanceof Array` | `true`     |

---

### **8. Ternary Operator**
A shorthand for conditional statements.

| Operator | Description                       | Example                          | Result    |
|----------|-----------------------------------|----------------------------------|-----------|
| `? :`    | Ternary/Conditional Operator      | `5 > 3 ? 'Yes' : 'No'`           | `'Yes'`   |

---

### **9. Nullish Coalescing Operator (`??`)**
Returns the right-hand operand if the left-hand operand is `null` or `undefined`.

| Operator | Description              | Example          | Result    |
|----------|--------------------------|------------------|-----------|
| `??`     | Nullish Coalescing       | `null ?? 'Hello'`| `'Hello'` |

---

### **10. Optional Chaining Operator (`?.`)**
Safely access deeply nested properties without errors.

| Operator | Description                       | Example            | Result      |
|----------|-----------------------------------|--------------------|-------------|
| `?.`     | Optional Chaining                 | `obj?.prop`        | `undefined` |

---

### **11. Comma Operator**
Used to evaluate multiple expressions in a single statement.

| Operator | Description              | Example             | Result |
|----------|--------------------------|---------------------|--------|
| `,`      | Sequential evaluation    | `let a = (1, 2, 3)` | `3`    |

---

### **12. Unary Operators**
Operate on a single operand.

| Operator | Description              | Example       | Result    |
|----------|--------------------------|---------------|-----------|
| `+`      | Converts to a number     | `+'5'`        | `5`       |
| `-`      | Negates a number         | `-5`          | `-5`      |
| `!`      | Logical NOT              | `!true`       | `false`   |
| `++`     | Increment                | `++x`         | `x + 1`   |
| `--`     | Decrement                | `--x`         | `x - 1`   |

---

### **Operator Precedence**
Determines the order of evaluation in expressions with multiple operators. For example:

```javascript
let result = 5 + 3 * 2; // Multiplication occurs before addition
console.log(result);    // Output: 11
```

To override precedence, use parentheses:

```javascript
let result = (5 + 3) * 2;
console.log(result); // Output: 16
```

### **Operator Associativity**
Defines the order of evaluation when operators have the same precedence. For example:
- **Left-to-Right:** `+, -, *, /`
- **Right-to-Left:** `=, **`

---

This covers a detailed breakdown of all JavaScript operators. Let me know if you'd like a cheat sheet or additional examples!
Here are additional examples for each category of JavaScript operators to reinforce your understanding.

---

### **1. Arithmetic Operators**
Perform basic mathematical operations.

```javascript
let a = 10;
let b = 3;

console.log(a + b);  // 13 (Addition)
console.log(a - b);  // 7 (Subtraction)
console.log(a * b);  // 30 (Multiplication)
console.log(a / b);  // 3.3333333333333335 (Division)
console.log(a % b);  // 1 (Modulus)
console.log(a ** b); // 1000 (Exponentiation)

// Increment and Decrement
let x = 5;
console.log(++x); // 6 (Pre-increment: increments first, then returns the value)
console.log(x++); // 6 (Post-increment: returns the value, then increments)
console.log(x);   // 7
```

---

### **2. Assignment Operators**
Combine assignment with operations.

```javascript
let x = 10;
x += 5;  // Equivalent to x = x + 5
console.log(x); // 15

x *= 2;  // Equivalent to x = x * 2
console.log(x); // 30

x -= 10; // Equivalent to x = x - 10
console.log(x); // 20

x /= 4;  // Equivalent to x = x / 4
console.log(x); // 5

x %= 3;  // Equivalent to x = x % 3
console.log(x); // 2
```

---

### **3. Comparison Operators**
Compare values and return a Boolean.

```javascript
console.log(5 == '5');  // true (Equality operator checks only value)
console.log(5 === '5'); // false (Strict equality checks value and type)

console.log(10 != '10');  // false
console.log(10 !== '10'); // true

console.log(7 > 5);   // true
console.log(7 >= 7);  // true
console.log(3 < 5);   // true
console.log(3 <= 2);  // false
```

---

### **4. Logical Operators**
Combine or invert Boolean values.

```javascript
let a = true, b = false;

console.log(a && b); // false (AND: true only if both operands are true)
console.log(a || b); // true (OR: true if at least one operand is true)
console.log(!a);     // false (NOT: inverts the Boolean value)
console.log(!b);     // true
```

---

### **5. Bitwise Operators**
Operate at the binary level.

```javascript
console.log(5 & 1);  // 1 (AND: 0101 & 0001 = 0001)
console.log(5 | 1);  // 5 (OR: 0101 | 0001 = 0101)
console.log(5 ^ 1);  // 4 (XOR: 0101 ^ 0001 = 0100)
console.log(~5);     // -6 (NOT: inverts all bits of 0101 to 1010)

console.log(5 << 1); // 10 (Left shift: 0101 becomes 1010)
console.log(5 >> 1); // 2 (Right shift: 0101 becomes 0010)
console.log(5 >>> 1); // 2 (Zero-fill right shift)
```

---

### **6. String Operators**
Work with string concatenation.

```javascript
let str1 = "Hello";
let str2 = "World";

console.log(str1 + " " + str2); // "Hello World"
str1 += ", JavaScript";
console.log(str1); // "Hello, JavaScript"
```

---

### **7. Type Operators**
Work with data types.

```javascript
console.log(typeof 42);          // "number"
console.log(typeof "JavaScript"); // "string"
console.log(typeof true);         // "boolean"

let arr = [1, 2, 3];
console.log(arr instanceof Array); // true
console.log(arr instanceof Object); // true
```

---

### **8. Ternary Operator**
A shorthand for `if-else`.

```javascript
let age = 18;
let message = (age >= 18) ? "You are an adult" : "You are a minor";
console.log(message); // "You are an adult"
```

---

### **9. Nullish Coalescing Operator (`??`)**
Return the right-hand value if the left-hand value is `null` or `undefined`.

```javascript
let name = null;
console.log(name ?? "Default Name"); // "Default Name"

let value = 0;
console.log(value ?? 10); // 0 (since 0 is not null or undefined)
```

---

### **10. Optional Chaining (`?.`)**
Safely access deeply nested properties.

```javascript
let user = {
  name: "Aryan",
  address: {
    city: "Delhi"
  }
};

console.log(user?.address?.city);    // "Delhi"
console.log(user?.address?.zipcode); // undefined
console.log(user?.contact?.phone);  // undefined (without errors)
```

---

### **11. Comma Operator**
Evaluate multiple expressions.

```javascript
let result = (1 + 2, 3 + 4); // Evaluates both but returns the last value
console.log(result); // 7
```

---

### **12. Unary Operators**
Operate on a single operand.

```javascript
console.log(+"123");    // 123 (converts to number)
console.log(-"123");    // -123
console.log(!false);    // true (logical NOT)

let y = 10;
console.log(++y); // 11 (pre-increment)
console.log(y--); // 11 (post-decrement)
console.log(y);   // 10
```

---

### **Operator Precedence and Associativity**
Operator precedence determines evaluation order.

```javascript
console.log(5 + 3 * 2); // 11 (* is evaluated before +)
console.log((5 + 3) * 2); // 16 (Parentheses override precedence)

// Associativity example
let result = 10 - 5 - 2; // Left-to-right: (10 - 5) - 2 = 3
console.log(result);

let a = b = c = 5; // Right-to-left: c = 5, b = c, a = b
console.log(a, b, c); // 5 5 5
```

---

Let me know if you’d like additional examples or clarifications on specific operators!