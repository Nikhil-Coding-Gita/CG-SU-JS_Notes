
# Variables and Data Types in JavaScript

## Introduction to Variables

A **variable** is a named container used to store a data value in a JavaScript program or In JavaScript, variable names are called **identifiers**. When naming variables, you must follow specific syntax rules enforced by the language, along with standard conventions used by developers.

**Key Concepts**

* **Declaration vs. Assignment:** Declaring a variable creates it (e.g., `let age;`), while assigning a value puts data inside it (e.g., `age = 25;`).
* **Dynamic Typing:** JavaScript variables are dynamically typed, meaning a single variable can hold a number, then later be reassigned to hold a string or boolean.

**Declaration Keywords**

* `const`: Used by default for values that will **not** be reassigned. It is block-scoped.
* `let`: Used for variables whose values **will change** over time. It is block-scoped.
* `var`: The legacy declaration method from older JavaScript. It is function-scoped and generally avoided in modern development due to hoisting and scope issues.

```javascript
// Variable declaration and initialization
const birthYear = 1998; // Cannot be reassigned
let currentAge = 25;    // Can be reassigned later

currentAge = 26;        // Valid reassignment

```
You can think of a variable as a **labeled box** that stores some information:

```text
name       → "John"
age        → 25
isStudent  → true
```

The value stored in a variable can be used later in the program.

For example:

```javascript
let age = 25;

console.log(age);
```

Output:

```text
25
```

Variables are useful because they allow us to:

* Store data.
* Reuse data.
* Change data when required.
* Perform calculations using stored values.
* Give meaningful names to values.

**Syntax Rules (Mandatory)**

* **Allowed Characters:** Variable names can only contain letters (`a-z`, `A-Z`), digits (`0-9`), underscores (`_`), and dollar signs (`$`).
* **First Character Rule:** A variable name **cannot start with a digit**. It must begin with a letter, an underscore, or a dollar sign.
* **Case Sensitivity:** Variable names are case-sensitive (`myVariable` and `myvariable` are treated as two distinct variables).
* **No Reserved Keywords:** You cannot use JavaScript reserved keywords (such as `let`, `const`, `var`, `function`, `if`, `class`, or `return`) as variable names.
* **No Spaces or Hyphens:** Variable names cannot contain spaces or hyphens (`-`).

---

**Naming Conventions (Best Practices)**

* **Use CamelCase:** Use lowerCamelCase for standard variable and function names (e.g., `userName`, `totalCartPrice`).
* **UPPERCASE for Hardcoded Constants:** Use uppercase with underscores for values that never change during program execution (e.g., `MAX_RETRY_COUNT`, `API_BASE_URL`).
* **Descriptive Names:** Choose clear, self-explanatory names over single letters (e.g., `itemCount` instead of `x`), except for simple loop counters (e.g., `i`).
* **Default to `const`:** Use `const` by default for all variable declarations. Only use `let` when you know the variable's value needs to be reassigned later. Avoid using `var` in modern JavaScript.

```javascript
// Valid Declarations
const maxScore = 100;
let _privateData = "secret";
let $element = document.querySelector("#app");
let user2 = "Bob";

// Invalid Declarations
// let 2user = "Alice";    // Error: Cannot start with a number
// let user-name = "Bob";   // Error: Cannot contain hyphens
// let class = "Physics";   // Error: 'class' is a reserved keyword

```

JavaScript provides three keywords for declaring variables:

1. **`var`** – Older/legacy way of declaring variables.
2. **`let`** – Modern way to declare variables whose values can change.
3. **`const`** – Modern way to declare variables that cannot be reassigned.


---

# Variable Declaration Keywords

## 1. `var`

`var` is the older way of declaring variables in JavaScript.

```javascript
var name = "John";
var age = 25;
```

The value of a `var` variable can be changed:

```javascript
var age = 25;

age = 30;

console.log(age);
```

Output:

```text
30
```

`var` also allows the same variable to be declared again in the same scope:

```javascript
var age = 25;
var age = 30;

console.log(age);
```

Output:

```text
30
```

Because of some older behavior of `var`, such as **function scope and hoisting**, modern JavaScript generally prefers `let` and `const`.

---

## 2. `let`

`let` is the modern way to declare a variable when its value may need to change.

```javascript
let age = 25;

age = 30;

console.log(age);
```

Output:

```text
30
```

A `let` variable can be **reassigned**, but it cannot be **redeclared in the same scope**.

```javascript
let age = 25;

age = 30; // Valid
```

But:

```javascript
let age = 25;

// let age = 30; // Error
```

`let` is **block-scoped**, meaning it is available only within the block `{ }` where it is declared.

---

## 3. `const`

`const` is used when a variable should not be **reassigned** after its initial value is given.

```javascript
const PI = 3.14159;
```

This is not allowed:

```javascript
const PI = 3.14159;

PI = 3.14; // Error
```

A `const` variable must be initialized when it is declared:

```javascript
const age = 25;
```

This is invalid:

```javascript
const age; // Error
```

### Important: `const` and Objects/Arrays

`const` prevents reassignment of the variable, but it does not make an object or array completely immutable.

For example:

```javascript
const person = {
    name: "Alice"
};

person.name = "Bob";

console.log(person.name);
```

Output:

```text
Bob
```

This works because we are modifying a property of the existing object, not assigning a completely new object to `person`.

But this is not allowed:

```javascript
const person = {
    name: "Alice"
};

person = {
    name: "Bob"
}; // Error
```

### General rule

Use:

```javascript
const
```

by default.

Use:

```javascript
let
```

when the value needs to be changed.

Avoid `var` in modern JavaScript unless you specifically need its legacy behavior.

---

# JavaScript Data Types

A **data type** defines the kind of value stored or being operated on.

JavaScript has several built-in data types.

They are broadly divided into:

```text
Data Types
│
├── Primitive Data Types
│   ├── Number
│   ├── String
│   ├── Boolean
│   ├── Undefined
│   ├── Null
│   ├── Symbol
│   └── BigInt
│
└── Non-Primitive / Reference Data Types
    ├── Object
    ├── Array
    └── Function
```

JavaScript is **dynamically typed**, so a variable can hold a value of one type and later hold a value of another type.

```javascript
let value = 10;

value = "Hello";

value = true;
```

All three assignments are valid.

---

# 1. Primitive Data Types

Primitive data types represent individual values.

JavaScript has seven primitive data types:

1. Number
2. String
3. Boolean
4. Undefined
5. Null
6. Symbol
7. BigInt

---

## a) Number

The `Number` type represents numeric values.

JavaScript uses the `Number` type for both **integers** and **floating-point numbers**.

```javascript
let integerNumber = 42;
let floatNumber = 3.14;
let negativeNumber = -10;
```

### Scientific notation

JavaScript also supports scientific notation:

```javascript
let scientificNotation = 2.5e3;

console.log(scientificNotation);
```

Output:

```text
2500
```

Here:

```text
2.5e3 = 2.5 × 10³ = 2500
```

### Special Number values

JavaScript's `Number` type also includes special values such as:

```javascript
Infinity
-Infinity
NaN
```

Example:

```javascript
console.log(10 / 0);
```

Output:

```text
Infinity
```

`NaN` means **Not-a-Number**.

```javascript
console.log("Hello" * 5);
```

Output:

```text
NaN
```

Interestingly:

```javascript
typeof NaN
```

returns:

```text
"number"
```

---

# b) String

A `String` represents textual data.

Strings can be written using:

### Single quotes

```javascript
let message = 'Hello';
```

### Double quotes

```javascript
let message = "Hello";
```

### Backticks

```javascript
let message = `Hello`;
```

Single and double quotes are commonly used for normal strings.

Backticks create a **template literal**, which is especially useful when inserting variables or expressions into strings.

```javascript
let name = "Alice";

console.log(`Hello ${name}`);
```

Output:

```text
Hello Alice
```

The `${}` syntax is called **interpolation**.

It can also contain expressions:

```javascript
let a = 10;
let b = 20;

console.log(`Sum = ${a + b}`);
```

Output:

```text
Sum = 30
```

---

# c) Boolean

The Boolean data type represents a logical value.

It has only two possible values:

```javascript
true
false
```

Example:

```javascript
let isStudent = true;
let isLoggedIn = false;
```

Boolean values are commonly used when representing conditions.

```javascript
let age = 20;

console.log(age >= 18);
```

Output:

```text
true
```

---

# d) Undefined

`undefined` represents the absence of an assigned value in situations where JavaScript produces `undefined`.

The most common example is a variable that has been declared but has not been assigned a value.

```javascript
let unassignedVariable;

console.log(unassignedVariable);
```

Output:

```text
undefined
```

Other examples include accessing a property that does not exist:

```javascript
let obj = {};

console.log(obj.nonExistentProperty);
```

Output:

```text
undefined
```

A function that does not explicitly return a value also returns `undefined`:

```javascript
function noReturn() {
}

console.log(noReturn());
```

Output:

```text
undefined
```

The type of `undefined` is:

```javascript
typeof undefined
```

Output:

```text
"undefined"
```

---

# e) Null

`null` represents an **intentional absence of a value**.

Unlike `undefined`, which JavaScript commonly produces automatically in certain situations, `null` is normally assigned explicitly by the programmer.

```javascript
let emptyValue = null;

console.log(emptyValue);
```

Output:

```text
null
```

For example, suppose a variable is intended to store a selected user:

```javascript
let selectedUser = null;
```

This means:

> There is currently no selected user intentionally.

---

# Difference Between `undefined` and `null`

Understanding the difference between `undefined` and `null` is important.

## `undefined`

* Usually indicates that a value has not been provided or initialized.
* JavaScript can produce it automatically.
* A declared variable without an assigned value has the value `undefined`.
* `typeof undefined` returns `"undefined"`.

Example:

```javascript
let value;

console.log(value);
```

Output:

```text
undefined
```

---

## `null`

* Represents an intentional absence of a value.
* It is normally assigned explicitly by the programmer.
* `typeof null` returns `"object"`.
* This is a historical JavaScript quirk.

Example:

```javascript
let value = null;

console.log(value);
```

Output:

```text
null
```

### Comparison

```javascript
let a;
let b = null;

console.log(a); // undefined
console.log(b); // null
```

### More examples

```javascript
// undefined

let unassignedVar;

console.log(unassignedVar); // undefined

let obj = {};

console.log(obj.nonExistentProperty); // undefined

function noReturn() {}

console.log(noReturn()); // undefined
```

```javascript
// null

let emptyValue = null;

console.log(emptyValue); // null

function findUser(id) {
    // If no user is found, intentionally return null
    return null;
}

console.log(findUser(101)); // null
```

### `==` vs `===` with null and undefined

```javascript
console.log(undefined == null);
```

Output:

```text
true
```

This happens because `==` performs loose equality comparison with type coercion rules.

But:

```javascript
console.log(undefined === null);
```

Output:

```text
false
```

`===` performs strict equality comparison, so the types must also match.

In modern JavaScript, `===` is generally preferred when you want predictable comparisons.

---

# f) Symbol

`Symbol` is a primitive data type introduced in **ES6**.

A Symbol represents a **unique and immutable value**.

```javascript
const uniqueId = Symbol("id");
```

Two Symbols with the same description are still different:

```javascript
const id1 = Symbol("id");
const id2 = Symbol("id");

console.log(id1 === id2);
```

Output:

```text
false
```

Symbols are commonly useful when a unique property key is required.

```javascript
const id = Symbol("id");

const user = {
    name: "Alice",
    [id]: 101
};
```

The Symbol description `"id"` is only descriptive; it does not make different Symbols equal.

---

# g) BigInt

`BigInt` is used to represent **integers larger than the safe range of JavaScript's `Number` type**.

A BigInt literal is written by adding `n` at the end of an integer.

```javascript
const bigNumber = 1234567890123456789012345678901234567890n;
```

Notice:

```text
n
```

at the end.

Example:

```javascript
const a = 1000000000000000000n;
const b = 2n;

console.log(a * b);
```

BigInt should not normally be mixed directly with `Number` in arithmetic:

```javascript
10n + 5; // Error
```

Instead, use the same type:

```javascript
10n + 5n;
```

The type can be checked using:

```javascript
console.log(typeof 10n);
```

Output:

```text
bigint
```

---

# 2. Non-Primitive (Reference) Data Types

Non-primitive values are commonly represented as **objects** in JavaScript.

The commonly encountered types in this category are:

* Object
* Array
* Function

Unlike primitive values, objects and arrays can contain collections of values and properties.

---

## a) Object

An object is a collection of **key-value pairs**, also called properties.

```javascript
let person = {
    name: "Alice",
    age: 30,
    isStudent: false
};
```

Here:

```text
name       → "Alice"
age        → 30
isStudent  → false
```

Properties can be accessed using **dot notation**:

```javascript
console.log(person.name);
console.log(person.age);
```

Output:

```text
Alice
30
```

They can also be accessed using **bracket notation**:

```javascript
console.log(person["name"]);
```

Output:

```text
Alice
```

Objects allow us to group related information together.

---

## b) Array

An array is an ordered collection of values.

```javascript
let numbers = [1, 2, 3, 4, 5];
```

Array elements are accessed using an **index**.

JavaScript arrays use **zero-based indexing**, meaning the first element has index `0`.

```text
Value:  10   20   30   40
Index:   0    1    2    3
```

Example:

```javascript
let numbers = [10, 20, 30, 40];

console.log(numbers[0]);
console.log(numbers[2]);
```

Output:

```text
10
30
```

Arrays can contain values of different data types:

```javascript
let mixedArray = [1, "hello", true, null];
```

Although arrays are commonly treated as a separate data structure, technically an array is an **object** in JavaScript.

Therefore:

```javascript
typeof [1, 2, 3]
```

returns:

```text
"object"
```

---

## c) Function

A function is a reusable block of code designed to perform a particular task.

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
```

The function can be called using:

```javascript
console.log(greet("Alice"));
```

Output:

```text
Hello, Alice!
```

Functions can accept **parameters** and can **return values**.

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(10, 20));
```

Output:

```text
30
```

Functions are technically objects in JavaScript, but `typeof` gives functions the special result `"function"`.

---

# Checking Types with `typeof` Operator

The `typeof` operator is used to determine the type of a value.

Syntax:

```javascript
typeof value
```

or:

```javascript
typeof variable
```

Examples:

```javascript
console.log(typeof 42);            // "number"
console.log(typeof 3.14);          // "number"
console.log(typeof "hello");       // "string"
console.log(typeof true);          // "boolean"
console.log(typeof undefined);     // "undefined"
console.log(typeof null);          // "object"
console.log(typeof {});            // "object"
console.log(typeof []);            // "object"
console.log(typeof function(){});  // "function"
console.log(typeof 10n);           // "bigint"
console.log(typeof Symbol("id"));  // "symbol"
```

### Important `typeof` points

#### `typeof null`

```javascript
console.log(typeof null);
```

Output:

```text
"object"
```

This is a **historical quirk in JavaScript**.

`null` is still a primitive value even though `typeof null` returns `"object"`.

#### `typeof []`

```javascript
console.log(typeof []);
```

Output:

```text
"object"
```

To specifically check whether a value is an array, use:

```javascript
console.log(Array.isArray([]));
```

Output:

```text
true
```

---

# Variable Naming Rules

JavaScript has rules that must be followed when naming variables.

## 1. A variable name must start with:

* A letter
* Underscore `_`
* Dollar sign `$`

Valid:

```javascript
let firstName;
let _private;
let $element;
```

---

## 2. Subsequent characters can contain:

* Letters
* Digits
* Underscores
* Dollar signs

Valid:

```javascript
let user123;
let student_name;
let $price;
```

A variable cannot start with a number.

Invalid:

```javascript
let 123user;
```

---

## 3. Variable names are case-sensitive

JavaScript treats uppercase and lowercase letters as different.

```javascript
let age = 20;
let Age = 30;

console.log(age);
console.log(Age);
```

Output:

```text
20
30
```

Therefore:

```text
myVar
myvar
MYVAR
```

are three different names.

---

## 4. Reserved keywords cannot be used

JavaScript has reserved words that have special meanings.

Examples:

```text
var
let
const
function
return
class
if
else
for
while
```

These cannot normally be used as variable names.

Invalid:

```javascript
let function;
let return;
let class;
```

---

# Variable Declaration and Assignment

There are three related concepts:

### Declaration

Creating a variable:

```javascript
let message;
```

Here, `message` has been declared.

Its value is:

```text
undefined
```

### Assignment

Giving a value to an existing variable:

```javascript
message = "Hello, World!";
```

### Declaration + Initialization

Declaring and assigning a value at the same time:

```javascript
let name = "Alice";
```

Here, `name` is declared and initialized with `"Alice"`.

---

## Reassignment

A variable declared using `let` can be assigned a new value.

```javascript
let age = 25;

age = 30;

console.log(age);
```

Output:

```text
30
```

A `const` variable cannot be reassigned:

```javascript
const MAX_USERS = 100;

// MAX_USERS = 200; // Error
```

---

## Multiple Variables

JavaScript allows multiple variables to be declared in one statement:

```javascript
let age = 25, isStudent = true;
```

However, separate declarations are often easier to read:

```javascript
let age = 25;
let isStudent = true;
```

---

# Type Coercion

**Type coercion** means JavaScript automatically converts a value from one data type to another in certain situations.

For example:

```javascript
console.log("5" + 3);
```

Output:

```text
"53"
```

Here, the number `3` is converted to a string because the `+` operator is being used with a string.

Similarly:

```javascript
console.log(5 + "3");
```

Output:

```text
"53"
```

---

## Mathematical Operators and Coercion

With operators such as `-`, `*`, and `/`, JavaScript often converts numeric strings into numbers.

```javascript
console.log("5" - 3);
```

Output:

```text
2
```

The string `"5"` is converted into the number `5`.

```javascript
console.log("5" * "2");
```

Output:

```text
10
```

Both strings are converted into numbers.

Another example:

```javascript
console.log("10" / "2");
```

Output:

```text
5
```

---

# Explicit Type Conversion

JavaScript also allows us to manually convert values.

### Convert to Number

```javascript
let value = "25";

let number = Number(value);

console.log(number);
```

Output:

```text
25
```

### Convert to String

```javascript
let age = 25;

let text = String(age);

console.log(text);
```

Output:

```text
"25"
```

### Convert to Boolean

The `Boolean()` function converts a value to `true` or `false`.

```javascript
console.log(Boolean(0));    // false
console.log(Boolean(1));    // true
console.log(Boolean(""));   // false
console.log(Boolean("a"));  // true
```

This is **explicit conversion**, because the programmer explicitly calls `Number()`, `String()`, or `Boolean()`.

---

# Best Practices

### 1. Use `const` by default

If you don't need to reassign a variable, use `const`.

```javascript
const userName = "John Doe";
```

Use `let` when the value needs to change:

```javascript
let itemCount = 0;

itemCount = 1;
```

---

### 2. Use meaningful variable names

Good:

```javascript
const studentName = "John";
const totalPrice = 500;
```

Avoid unclear names:

```javascript
const x = "John";
const a = 500;
```

Meaningful names make code easier to understand.

---

### 3. Use camelCase

JavaScript commonly uses **camelCase** for variable names.

Examples:

```javascript
let firstName;
let lastName;
let userAge;
let totalAmount;
```

---

### 4. Use uppercase for constants when appropriate

Constants representing fixed configuration values are often written in uppercase:

```javascript
const MAX_SIZE = 100;
const API_KEY = "example";
```

This is a naming convention, not a special JavaScript rule.

---

### 5. Initialize variables when practical

If you already know the initial value, declare and initialize the variable together:

Instead of:

```javascript
let name;
name = "Alice";
```

you can write:

```javascript
let name = "Alice";
```

However, declaring first and assigning later is perfectly valid when the program requires it.

---

# Example: Area Calculator

The following example combines variables, `const`, arithmetic operations, template literals, and `typeof`.

```javascript
// Calculate area of a rectangle
const length = 10;
const width = 5;

const area = length * width;

console.log(`The area of the rectangle is: ${area}`);

console.log(`Length: ${length}, Type: ${typeof length}`);
console.log(`Width: ${width}, Type: ${typeof width}`);
console.log(`Area: ${area}, Type: ${typeof area}`);
```

Output:

```text
The area of the rectangle is: 50
Length: 10, Type: number
Width: 5, Type: number
Area: 50, Type: number
```

### How it works

```javascript
const length = 10;
```

Creates a constant containing the rectangle's length.

```javascript
const width = 5;
```

Creates a constant containing the rectangle's width.

```javascript
const area = length * width;
```

Calculates:

```text
10 × 5 = 50
```

The template literal:

```javascript
`The area of the rectangle is: ${area}`
```

inserts the value of `area` into the string.

And:

```javascript
typeof length
```

checks the data type of `length`.

---

# Summary Table

| Data Type | Category  | Example              | `typeof` Result | Description                  |
| --------- | --------- | -------------------- | --------------- | ---------------------------- |
| Number    | Primitive | `42`, `3.14`         | `"number"`      | Numeric values               |
| String    | Primitive | `"hello"`, `'world'` | `"string"`      | Textual data                 |
| Boolean   | Primitive | `true`, `false`      | `"boolean"`     | Logical values               |
| Undefined | Primitive | `undefined`          | `"undefined"`   | Absence of an assigned value |
| Null      | Primitive | `null`               | `"object"`*     | Intentional absence of value |
| Symbol    | Primitive | `Symbol("id")`       | `"symbol"`      | Unique value                 |
| BigInt    | Primitive | `123n`               | `"bigint"`      | Large integers               |
| Object    | Reference | `{name: "John"}`     | `"object"`      | Collection of properties     |
| Array     | Reference | `[1, 2, 3]`          | `"object"`      | Ordered collection of values |
| Function  | Reference | `function(){}`       | `"function"`    | Reusable/callable code       |

`*` `typeof null` returning `"object"` is a historical JavaScript quirk.

---

## Quick Revision

```text
VARIABLES
│
├── var   → old, function-scoped, reassignable, redeclarable
├── let   → modern, block-scoped, reassignable
└── const → modern, block-scoped, cannot be reassigned
```

```text
PRIMITIVE DATA TYPES
│
├── Number
├── String
├── Boolean
├── Undefined
├── Null
├── Symbol
└── BigInt
```

```text
REFERENCE / NON-PRIMITIVE
│
├── Object
├── Array
└── Function
```

```text
IMPORTANT
│
├── typeof → checks type
├── undefined → value not provided/available
├── null → intentionally empty
├── Type coercion → automatic conversion
└── const → cannot be reassigned
```

This version stays within the scope of your original notes while making each existing topic substantially clearer and more complete.
