The primary differences between `var`, `let`, and `const` in JavaScript revolve around **scope**, **re-declaration/re-assignment**, and **hoisting**:

---

### Key Differences at a Glance

| Feature | `var` | `let` | `const` |
| --- | --- | --- | --- |
| **Scope** | Function scope | Block scope | Block scope |
| **Re-declaration** | Allowed in the same scope | Not allowed in the same scope | Not allowed in the same scope |
| **Re-assignment** | Allowed | Allowed | **Not allowed** |
| **Hoisting** | Hoisted and initialized as `undefined` | Hoisted, but uninitialized (TDZ) | Hoisted, but uninitialized (TDZ) |
| **Initialization** | Optional when declaring | Optional when declaring | **Required** when declaring |

---

### Detailed Breakdown

#### 1. Scope

* **`var` (Function Scoped):** If declared inside a function, `var` is accessible anywhere in that function. If declared inside an `if` block or `for` loop, it "leaks" outside into the surrounding function or global scope.
* **`let` & `const` (Block Scoped):** Variables declared with `let` or `const` only exist within the specific block `{ ... }` where they are created.

```javascript
if (true) {
  var x = 10;
  let y = 20;
  const z = 30;
}

console.log(x); // 10 (var leaked out of the block)
console.log(y); // ReferenceError: y is not defined
console.log(z); // ReferenceError: z is not defined

```

---

#### 2. Re-declaration and Re-assignment

* **`var`:** Allows both re-declaration and re-assignment, which can lead to accidental overwrites.
```javascript
var a = 1;
var a = 2; // Valid!
a = 3;     // Valid!

```


* **`let`:** Cannot be re-declared in the same scope, but its value **can** be reassigned.
```javascript
let b = 1;
// let b = 2; // Error: Identifier 'b' has already been declared
b = 3;        // Valid!

```


* **`const`:** Cannot be re-declared or reassigned. It must be given an initial value upon declaration.
```javascript
const c = 1;
// c = 2;     // Error: Assignment to constant variable.
// const d;   // Error: Missing initializer in const declaration

```



> **Note on `const` with Objects and Arrays:**
> `const` prevents re-assigning the reference to a variable, but it does **not** make objects or arrays immutable. You can still modify internal properties or elements:
> ```javascript
> const user = { name: "Alice" };
> user.name = "Bob"; // Valid!
> // user = { name: "Bob" }; // Error!
> 
> ```
> 
> 

---

#### 3. Hoisting & Temporal Dead Zone (TDZ)

All three keywords are hoisted to the top of their scope during parsing:

* **`var`** is hoisted and initialized with `undefined`. Accessing it before declaration yields `undefined`.
```javascript
console.log(a); // undefined
var a = 5;

```


* **`let` and `const**` are hoisted, but stay in a **Temporal Dead Zone (TDZ)** until execution reaches their declaration line. Accessing them prematurely throws a `ReferenceError`.
```javascript
console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 5;

```



---

### Best Practices

1. **Use `const` by default** for all variables to prevent unintentional re-assignments.
2. **Use `let` only when you know the value needs to change** (e.g., loop counters, flag variables).
3. **Avoid `var` in modern JavaScript** to prevent bugs caused by function-scoping and premature hoisting.
