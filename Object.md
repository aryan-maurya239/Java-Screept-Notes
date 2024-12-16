### **Detailed Notes on Objects in JavaScript**

---

### **What are Objects in JavaScript?**

In JavaScript, an **object** is a non-primitive data type that allows you to store multiple key-value pairs. Objects are one of the fundamental building blocks of JavaScript, used to store and organize data and behavior (methods). They are the backbone of object-oriented programming in JavaScript.

---

### **Creating Objects in JavaScript**

1. **Object Literals:**
   ```javascript
   const person = {
       name: "Aryan",
       age: 25,
       greet: function () {
           console.log(`Hello, my name is ${this.name}`);
       }
   };
   person.greet(); // Output: Hello, my name is Aryan
   ```

2. **Using the `Object` Constructor:**
   ```javascript
   const person = new Object();
   person.name = "Aryan";
   person.age = 25;
   person.greet = function () {
       console.log(`Hello, my name is ${this.name}`);
   };
   person.greet();
   ```

3. **Factory Functions:**
   ```javascript
   function createPerson(name, age) {
       return {
           name: name,
           age: age,
           greet() {
               console.log(`Hello, my name is ${this.name}`);
           }
       };
   }
   const person1 = createPerson("Aryan", 25);
   person1.greet();
   ```

4. **Constructor Functions:**
   ```javascript
   function Person(name, age) {
       this.name = name;
       this.age = age;
       this.greet = function () {
           console.log(`Hello, my name is ${this.name}`);
       };
   }
   const person2 = new Person("Aryan", 25);
   person2.greet();
   ```

5. **Using ES6 Classes:**
   ```javascript
   class Person {
       constructor(name, age) {
           this.name = name;
           this.age = age;
       }
       greet() {
           console.log(`Hello, my name is ${this.name}`);
       }
   }
   const person3 = new Person("Aryan", 25);
   person3.greet();
   ```

---

### **Accessing and Modifying Object Properties**

1. **Dot Notation:**
   ```javascript
   console.log(person.name); // Access
   person.name = "Aryan Maurya"; // Modify
   ```

2. **Bracket Notation:**
   ```javascript
   console.log(person["name"]); // Access
   person["name"] = "Aryan Maurya"; // Modify
   ```

3. **Adding New Properties:**
   ```javascript
   person.city = "New Delhi";
   ```

4. **Deleting Properties:**
   ```javascript
   delete person.city;
   ```

---

### **Object Methods**

An object method is a function that is a property of an object.

- Defining a Method:
  ```javascript
  const car = {
      brand: "Tesla",
      model: "Model 3",
      start() {
          console.log("The car has started");
      }
  };
  car.start(); // Output: The car has started
  ```

- Using the `this` Keyword:
  The `this` keyword refers to the current object.
  ```javascript
  const car = {
      brand: "Tesla",
      model: "Model 3",
      getDetails() {
          console.log(`${this.brand} ${this.model}`);
      }
  };
  car.getDetails(); // Output: Tesla Model 3
  ```

---

### **Common Object Methods in JavaScript**

1. **`Object.keys(obj)`**
   - Returns an array of the object's property names.
   ```javascript
   const keys = Object.keys(person);
   console.log(keys); // ["name", "age", "greet"]
   ```

2. **`Object.values(obj)`**
   - Returns an array of the object's values.
   ```javascript
   const values = Object.values(person);
   console.log(values); // ["Aryan", 25, ƒ]
   ```

3. **`Object.entries(obj)`**
   - Returns an array of `[key, value]` pairs.
   ```javascript
   const entries = Object.entries(person);
   console.log(entries); // [["name", "Aryan"], ["age", 25], ["greet", ƒ]]
   ```

4. **`Object.assign(target, ...sources)`**
   - Copies properties from one or more objects to a target object.
   ```javascript
   const target = {};
   const source = { age: 30 };
   Object.assign(target, source);
   console.log(target); // { age: 30 }
   ```

5. **`Object.freeze(obj)`**
   - Prevents adding, removing, or modifying properties.
   ```javascript
   const frozenObj = Object.freeze(person);
   frozenObj.name = "New Name"; // No effect
   ```

6. **`Object.seal(obj)`**
   - Prevents adding or removing properties but allows modification of existing ones.
   ```javascript
   const sealedObj = Object.seal(person);
   sealedObj.name = "New Name"; // Allowed
   sealedObj.city = "New City"; // Not allowed
   ```

7. **`Object.hasOwnProperty(property)`**
   - Checks if an object has a specific property as its own (not inherited).
   ```javascript
   console.log(person.hasOwnProperty("name")); // true
   ```

---

### **Prototype and Prototypal Inheritance**

1. **Prototype:**
   - Every JavaScript object has an internal prototype (`[[Prototype]]`), which is a reference to another object or `null`.

   ```javascript
   const obj = {};
   console.log(obj.__proto__); // Object prototype
   ```

2. **Prototypal Inheritance:**
   - Objects can inherit properties and methods from other objects.

   ```javascript
   const parent = { greet: () => console.log("Hello from parent") };
   const child = Object.create(parent);
   child.greet(); // Hello from parent
   ```

---

### **Advanced Object Concepts**

1. **Nested Objects:**
   ```javascript
   const person = {
       name: "Aryan",
       address: {
           city: "New Delhi",
           zip: 110001
       }
   };
   console.log(person.address.city); // Output: New Delhi
   ```

2. **Destructuring:**
   ```javascript
   const { name, address: { city } } = person;
   console.log(name); // Aryan
   console.log(city); // New Delhi
   ```

3. **Spread Syntax:**
   - Used to copy or merge objects.
   ```javascript
   const obj1 = { a: 1, b: 2 };
   const obj2 = { c: 3 };
   const mergedObj = { ...obj1, ...obj2 };
   console.log(mergedObj); // { a: 1, b: 2, c: 3 }
   ```

4. **JSON (JavaScript Object Notation):**
   - A lightweight data-interchange format.

   **Stringify:**
   ```javascript
   const jsonString = JSON.stringify(person);
   console.log(jsonString);
   ```

   **Parse:**
   ```javascript
   const jsonObject = JSON.parse(jsonString);
   console.log(jsonObject);
   ```

5. **`this` in Objects:**
   - The `this` keyword refers to the object that calls the method.
   ```javascript
   const user = {
       name: "Aryan",
       greet() {
           console.log(`Hi, I am ${this.name}`);
       }
   };
   user.greet(); // Output: Hi, I am Aryan
   ```

---

### **Shallow Copy vs. Deep Copy**

1. **Shallow Copy:**
   - Copies references to nested objects.
   ```javascript
   const original = { a: 1, b: { c: 2 } };
   const shallowCopy = { ...original };
   shallowCopy.b.c = 10; // Affects original
   ```

2. **Deep Copy:**
   - Creates a true copy of all nested objects.
   ```javascript
   const deepCopy = JSON.parse(JSON.stringify(original));
   ```

---

### **Comparison of Objects**

- **Equality Comparison:**
  - Objects are compared by reference, not value.
  ```javascript
  const obj1 = { a: 1 };
  const obj2 = { a: 1 };
  console.log(obj1 === obj2); // false
  ```

---

### **Use Cases of Objects:**

1. **Modeling Real-World Entities:**
   ```javascript
   const car = { brand: "Tesla", model: "Model S", year: 2024 };
   ```

2. **Storing Key-Value Data:**
   ```javascript
   const userScores = { Aryan: 100, John: 95 };
   ```

3. **Dynamic Behavior:**
   ```javascript
   const calculator = {
       add(a, b) {
           return a + b;
       }
   };
   console.log(calculator.add(3, 5)); // 8
   ```

By mastering JavaScript objects, you unlock the potential to write clean, efficient, and modular code that models complex real-world systems.