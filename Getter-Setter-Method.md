In JavaScript, **getter** and **setter** methods are used to define how to access and set the properties of an object. They allow for controlled access to the internal properties of an object, enabling encapsulation and validation of data.

### **What Are Getter and Setter Methods?**

1. **Getter Methods (`get`)**:
   - Used to retrieve the value of a property.
   - Acts like a method but is accessed like a property.
   - Can include additional logic when retrieving the property value.

2. **Setter Methods (`set`)**:
   - Used to update or modify the value of a property.
   - Provides a way to validate or preprocess data before setting the property.

---

### **Syntax**

```javascript
let obj = {
  // Getter
  get propertyName() {
    // Logic for getting the value
    return "value";
  },

  // Setter
  set propertyName(value) {
    // Logic for setting the value
    console.log("Setting value:", value);
  },
};
```

---

### **Example Usage**

#### **Basic Example**

```javascript
let person = {
  firstName: "Aryan",
  lastName: "Maurya",

  // Getter for fullName
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },

  // Setter for fullName
  set fullName(value) {
    let parts = value.split(" ");
    this.firstName = parts[0];
    this.lastName = parts[1];
  },
};

console.log(person.fullName); // Output: Aryan Maurya

// Using the setter
person.fullName = "John Doe";
console.log(person.firstName); // Output: John
console.log(person.lastName);  // Output: Doe
```

---

#### **With Validation in Setter**

```javascript
let account = {
  balance: 1000,

  // Getter for balance
  get accountBalance() {
    return `Your balance is $${this.balance}`;
  },

  // Setter with validation
  set accountBalance(value) {
    if (value < 0) {
      console.log("Invalid amount! Balance cannot be negative.");
    } else {
      this.balance = value;
    }
  },
};

console.log(account.accountBalance); // Output: Your balance is $1000

account.accountBalance = 500; // Sets balance to 500
console.log(account.accountBalance); // Output: Your balance is $500

account.accountBalance = -100; // Invalid amount
// Output: Invalid amount! Balance cannot be negative.
```

---

### **Defining Getters and Setters with `Object.defineProperty`**

Another way to define getters and setters is by using `Object.defineProperty()`.

#### **Syntax**
```javascript
Object.defineProperty(obj, "propertyName", {
  get: function () {
    // Logic for getting the value
  },
  set: function (value) {
    // Logic for setting the value
  },
});
```

#### **Example**

```javascript
let car = {
  brand: "Toyota",
  speed: 120,
};

Object.defineProperty(car, "description", {
  get: function () {
    return `${this.brand} is running at ${this.speed} km/h.`;
  },
  set: function (value) {
    let parts = value.split(" ");
    this.brand = parts[0];
    this.speed = parseInt(parts[1]);
  },
});

console.log(car.description); // Output: Toyota is running at 120 km/h

car.description = "Honda 150"; // Updates brand and speed
console.log(car.description); // Output: Honda is running at 150 km/h
```

---

### **Advantages of Getters and Setters**

1. **Encapsulation**:
   - Encapsulate the logic for getting and setting properties, making the code more maintainable.

2. **Validation**:
   - Validate data before setting a property (e.g., ensuring age is positive).

3. **Computed Properties**:
   - Dynamically compute properties based on internal object data.

4. **Controlled Access**:
   - Restrict direct modification of object properties.

---

### **Key Notes**

1. **Usage as Properties**:
   - Getters and setters are accessed like normal object properties, not methods.
   - For example, you write `obj.property` instead of `obj.property()`.

2. **Default Values**:
   - If no setter is defined for a property, attempting to set its value has no effect.

3. **Performance Considerations**:
   - Avoid computationally heavy logic in getters as they are invoked each time the property is accessed.

4. **Backward Compatibility**:
   - `get` and `set` were introduced in ECMAScript 5, so they may not work in very old JavaScript environments.

---

### **Advanced Example**

#### **Using Class Syntax**

```javascript
class Rectangle {
  constructor(width, height) {
    this._width = width;
    this._height = height;
  }

  // Getter for area
  get area() {
    return this._width * this._height;
  }

  // Setter for width with validation
  set width(value) {
    if (value <= 0) {
      console.log("Width must be positive.");
    } else {
      this._width = value;
    }
  }

  // Setter for height with validation
  set height(value) {
    if (value <= 0) {
      console.log("Height must be positive.");
    } else {
      this._height = value;
    }
  }
}

let rect = new Rectangle(10, 20);
console.log(rect.area); // Output: 200

rect.width = 15; // Updates width
console.log(rect.area); // Output: 300

rect.height = -5; // Invalid input
// Output: Height must be positive.
```

---

### **Conclusion**

Getters and setters in JavaScript are powerful tools for managing object properties. They improve code readability, provide validation, and help enforce rules when accessing or updating properties. They are especially useful in classes and when working with dynamic or computed properties.