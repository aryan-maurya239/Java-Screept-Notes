Here’s a comprehensive guide on **JavaScript methods** across various data types, objects, and contexts. I'll categorize them for clarity:

---

### **1. String Methods**

| **Method**                  | **Description**                                                                                           | **Example**                                      |
|-----------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| `.charAt(index)`            | Returns the character at the specified index.                                                            | `"hello".charAt(1)` → `"e"`                     |
| `.charCodeAt(index)`        | Returns the Unicode of the character at the specified index.                                             | `"hello".charCodeAt(0)` → `104`                |
| `.concat(str1, str2, ...)`  | Combines strings into one.                                                                                | `"Hello".concat(" ", "World")` → `"Hello World"`|
| `.includes(substring)`      | Checks if the string contains the specified substring.                                                   | `"hello".includes("ll")` → `true`              |
| `.indexOf(substring)`       | Returns the index of the first occurrence of a substring.                                                | `"hello".indexOf("l")` → `2`                   |
| `.lastIndexOf(substring)`   | Returns the index of the last occurrence of a substring.                                                 | `"hello".lastIndexOf("l")` → `3`               |
| `.slice(start, end)`        | Extracts a section of a string.                                                                          | `"hello".slice(1, 4)` → `"ell"`                |
| `.substring(start, end)`    | Extracts characters between two indices.                                                                | `"hello".substring(1, 4)` → `"ell"`            |
| `.toUpperCase()`            | Converts the string to uppercase.                                                                       | `"hello".toUpperCase()` → `"HELLO"`            |
| `.toLowerCase()`            | Converts the string to lowercase.                                                                       | `"HELLO".toLowerCase()` → `"hello"`            |
| `.trim()`                   | Removes whitespace from both ends.                                                                      | `" hello ".trim()` → `"hello"`                 |
| `.split(delimiter)`         | Splits the string into an array of substrings.                                                          | `"a,b,c".split(",")` → `["a", "b", "c"]`       |
| `.replace(substr, newStr)`  | Replaces the first occurrence of a substring with another string.                                       | `"hello".replace("l", "w")` → `"hewlo"`        |
| `.repeat(n)`                | Repeats the string `n` times.                                                                           | `"ha".repeat(3)` → `"hahaha"`                  |

---

### **2. Array Methods**

| **Method**                | **Description**                                                                                             | **Example**                                          |
|---------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| `.push(element)`          | Adds an element to the end of the array.                                                                    | `[1, 2].push(3)` → `[1, 2, 3]`                     |
| `.pop()`                  | Removes and returns the last element.                                                                       | `[1, 2, 3].pop()` → `3` (array: `[1, 2]`)         |
| `.shift()`                | Removes and returns the first element.                                                                      | `[1, 2, 3].shift()` → `1` (array: `[2, 3]`)       |
| `.unshift(element)`       | Adds an element to the beginning of the array.                                                              | `[1, 2].unshift(0)` → `[0, 1, 2]`                 |
| `.slice(start, end)`      | Returns a shallow copy of a portion of an array.                                                            | `[1, 2, 3].slice(0, 2)` → `[1, 2]`                |
| `.splice(start, deleteCount, items)` | Adds/removes elements at a specific index.                                                        | `[1, 2, 3].splice(1, 1)` → `[2]` (array: `[1, 3]`)|
| `.indexOf(element)`       | Returns the first index of an element.                                                                      | `[1, 2, 3].indexOf(2)` → `1`                      |
| `.lastIndexOf(element)`   | Returns the last index of an element.                                                                       | `[1, 2, 3, 2].lastIndexOf(2)` → `3`               |
| `.includes(element)`      | Checks if the array contains a specific element.                                                            | `[1, 2, 3].includes(2)` → `true`                  |
| `.map(callback)`          | Creates a new array by applying a function to each element.                                                 | `[1, 2, 3].map(x => x * 2)` → `[2, 4, 6]`         |
| `.filter(callback)`       | Creates a new array with elements that pass the test implemented by a callback.                             | `[1, 2, 3].filter(x => x > 1)` → `[2, 3]`         |
| `.reduce(callback, initialValue)` | Reduces the array to a single value by applying a callback function.                                   | `[1, 2, 3].reduce((acc, val) => acc + val)` → `6` |
| `.forEach(callback)`      | Executes a callback for each element (no return).                                                           | `[1, 2, 3].forEach(x => console.log(x))`          |
| `.concat(array)`          | Combines arrays into a new array.                                                                           | `[1, 2].concat([3, 4])` → `[1, 2, 3, 4]`          |
| `.sort(compareFunction)`  | Sorts the array elements.                                                                                   | `[3, 1, 2].sort()` → `[1, 2, 3]`                  |
| `.reverse()`              | Reverses the order of the array.                                                                            | `[1, 2, 3].reverse()` → `[3, 2, 1]`               |
| `.find(callback)`         | Returns the first element that satisfies the callback.                                                      | `[1, 2, 3].find(x => x > 1)` → `2`                |
| `.findIndex(callback)`    | Returns the index of the first element that satisfies the callback.                                          | `[1, 2, 3].findIndex(x => x > 1)` → `1`           |

---

### **3. Object Methods**

| **Method**                      | **Description**                                                                                           | **Example**                                       |
|---------------------------------|-----------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| `Object.keys(obj)`              | Returns an array of the object’s keys.                                                                    | `Object.keys({a: 1, b: 2})` → `["a", "b"]`       |
| `Object.values(obj)`            | Returns an array of the object’s values.                                                                  | `Object.values({a: 1, b: 2})` → `[1, 2]`         |
| `Object.entries(obj)`           | Returns an array of key-value pairs as arrays.                                                            | `Object.entries({a: 1})` → `[["a", 1]]`          |
| `Object.assign(target, source)` | Copies the properties from the source object(s) to the target object.                                     | `Object.assign({}, {a: 1})` → `{a: 1}`           |
| `Object.freeze(obj)`            | Freezes the object, preventing modifications.                                                             | `Object.freeze(obj)`                             |
| `Object.seal(obj)`              | Prevents adding or deleting properties but allows modification of existing ones.                          | `Object.seal(obj)`                               |
| `Object.create(proto)`          | Creates a new object with the specified prototype.                                                        | `Object.create({a: 1})`                          |

---

### **4. Math Methods**

| **Method**             | **Description**                                                                               | **Example**                     |
|------------------------|-----------------------------------------------------------------------------------------------|----------------------------------|
| `Math.abs(x)`          | Returns the absolute value of `x`.                                                            | `Math.abs(-5)` → `5`            |
| `Math.ceil(x)`         | Rounds `x` up to the nearest integer.                                                         | `Math.ceil(4.3)` → `5`          |
| `Math.floor(x)`        | Rounds `x` down to the nearest integer.                                                       | `Math.floor(4.9)` → `4`         |
| `Math.round(x)`        | Rounds `x` to the nearest integer.                                                            | `Math.round(4.5)` → `5`         |
| `Math.max(...args)`    | Returns the largest value from the given numbers.                                             | `Math.max(1, 2, 3)` → `3`       |
| `Math.min(...args)`    | Returns the smallest value from the given numbers.                                            | `Math.min(1, 2, 3)` → `1`       |
| `Math.random()`        | Returns a random number between 0 and 1.                                                      | `Math.random()` → `0.67`        |
| `Math.sqrt(x)`         | Returns the square root of `x`.                                                               | `Math.sqrt(16)` → `4`           |

---

### **5. Date Methods**

| **Method**                  | **Description**                                   | **Example**                                        |
|-----------------------------|---------------------------------------------------|---------------------------------------------------|
| `.getDate()`                | Returns the day of the month (1-31).              | `new Date().getDate()`

 → `7`                     |
| `.getMonth()`               | Returns the month (0-11).                         | `new Date().getMonth()` → `11`                   |
| `.getFullYear()`            | Returns the year.                                 | `new Date().getFullYear()` → `2024`              |
| `.getDay()`                 | Returns the weekday (0-6, Sunday is 0).           | `new Date().getDay()` → `4`                      |
| `.getHours()`               | Returns the hour (0-23).                          | `new Date().getHours()` → `14`                   |

---

Would you like detailed notes on other JavaScript categories, like **DOM manipulation** or **promises**?