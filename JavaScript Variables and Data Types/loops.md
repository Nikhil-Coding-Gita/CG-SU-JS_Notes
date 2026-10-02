**JavaScript Loops – Beginner Friendly Notes**

---

### Introduction to Loops

Loops help us **repeat** a task many times without writing the same code again and again.

**Real-life analogy**  
Instead of saying:  
“Wash plate 1, wash plate 2, wash plate 3…”  
We say: “Wash plates from 1 to 10”.

**Why use loops?**
- Save time and reduce code
- Easy to handle large data (100 items or 1000 items)
- Used in real projects: printing reports, checking emails, games, animations

**Types of loops we will learn**
- `for` loop → Best when we know how many times to repeat
- `while` loop → Best when we don’t know the exact number of times
- `do...while` loop → Runs at least once
- `for...in` → Used for objects
- `for...of` → Used for arrays and strings

---

### 1. For Loop

The most popular loop when the number of repetitions is known.

**Syntax**
```js
for (initialization; condition; update) {
  // code to repeat
}
```

**How it works (simple steps)**
- Start with a value (`initialization`)
- Check the condition
- If true → run the code
- Update the counter
- Repeat until condition becomes false

**Classic Example – Print 1 to 5**
```js
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
// Output: 1 2 3 4 5
```

**Try in Console**  
Open Chrome → Press F12 → Go to Console → Paste this:
```js
for (let i = 1; i <= 3; i++) {
  console.log("Loop running: " + i);
}
```

**Common Mistakes**
- Forgetting `i++` → Infinite loop (browser freezes)
- Using `i < 5` instead of `i <= 5` → Misses the last number
- Using `var` instead of `let` → Variable leaks outside the loop

---

#### Activity Time – For Loop

1. Print numbers from 1 to 10 using a `for` loop.  
2. Print all even numbers from 2 to 20.  
3. Print the multiplication table of 9.  
4. Find the sum of first 10 natural numbers.  
5. Find the multiplication (product) of first 10 natural numbers.  
6. Print numbers 1 to 5 in a **single line**.  
7. Print `*` five times  
   - in different lines  
   - in the same line  
8. Given an array `[10, 20, 30, 40, 50]`, print all elements using a `for` loop.  
9. Given a string `"CodingGita"`, print each character using a `for` loop.

---

### 1.1 Reverse For Loop

Used when we want to go from higher number to lower number (countdown style).

**Classic Example**
```js
for (let i = 10; i >= 1; i--) {
  console.log(i);
}
// Output: 10 9 8 7 6 5 4 3 2 1
```

**Reverse an Array**
```js
const arr = [10, 20, 30, 40, 50];
for (let i = arr.length - 1; i >= 0; i--) {
  console.log(arr[i]);
}
```

---

#### Activity Time – Reverse For Loop

1. Print all even numbers from 20 down to 2 using a reverse `for` loop.  
2. Print the multiplication table of 8 in reverse (from `8 × 10 = 80` down to `8 × 1 = 8`).  
3. Given an array `[10, 20, 30, 40, 50]`, print all elements in reverse order (do **not** use `.reverse()`).  
4. Given a string `"CodingGita"`, print all characters in reverse order (do **not** use `.reverse()` or `.split()`).

---

### 1.2 Nested For Loop

A loop inside another loop.  
Outer loop runs once → Inner loop completes all its rounds.

**Classic Example – Multiplication Table**
```js
for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 3; j++) {
    console.log(i + " × " + j + " = " + (i * j));
  }
}
```

**Star Pattern Example**
```js
for (let i = 1; i <= 5; i++) {
  let row = "";
  for (let j = 1; j <= i; j++) {
    row += "* ";
  }
  console.log(row);
}
```

---

#### Activity Time – Nested For Loop

1. Print this pattern:
```
*
**
***
****
*****
```

2. Print this pattern:
```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

3. Print this pattern:
```
5 4 3 2 1
4 3 2 1
3 2 1
2 1
1
```

---

### 1.3 Break and Continue

Special keywords to control the loop.

| Keyword     | What it does                          |
|-------------|---------------------------------------|
| `break`     | Completely stops the loop             |
| `continue`  | Skips the current round and goes next |

**Break Example**
```js
for (let i = 1; i <= 10; i++) {
  if (i === 5) break;
  console.log(i);
}
// Output: 1 2 3 4
```

**Continue Example**
```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i);
}
// Output: 1 2 4 5
```

---

#### Activity Time – Break & Continue

1. Print numbers from 1 to 20 but stop completely when you reach 13 (`break`).  
2. Print numbers from 1 to 15 but skip all multiples of 3 (`continue`).  
3. Print only odd numbers from 1 to 20 using `continue`.

---

### 2. While Loop

Used when we **don’t know** exactly how many times the loop should run.  
Condition is checked **before** the loop starts.

**Syntax**
```js
while (condition) {
  // code
  // update the condition
}
```

**Classic Example – Countdown**
```js
let count = 5;
while (count > 0) {
  console.log(count);
  count--;
}
// Output: 5 4 3 2 1
```

**Important**  
If the condition is false at the beginning → loop never runs.

---

#### Activity Time – While Loop

1. Print numbers from 1 to 10 using a `while` loop.  
2. Print all even numbers from 2 to 20 using `while`.  
3. Find the sum of first 10 natural numbers using `while`.  
4. Keep printing numbers starting from 1 until the number becomes greater than 50.  
5. Reverse a number using only a `while` loop (Example: 1234 → 4321).

---

### 3. Do...While Loop

Very similar to `while`, but the code runs **at least once** (even if condition is false).

**Syntax**
```js
do {
  // code
} while (condition);
```

**Classic Example**
```js
let i = 1;
do {
  console.log(i);
  i++;
} while (i <= 5);
```

**Special Behavior**
```js
let x = 10;
do {
  console.log("This runs once");
} while (x < 5);   // condition is false, still runs once
```

---

#### Activity Time – Do...While Loop

1. Print numbers from 1 to 5 using `do...while`.  
2. Keep generating a random number between 1–10 until you get 7. Count how many tries it took.  
3. Create a simple menu:  
   - Show “1. Start  2. Exit”  
   - Keep asking until user chooses 2.  
4. Print the multiplication table of 7 using `do...while`.

---

### 4. for...in Loop

Used to loop through the **keys (property names)** of an object.

**Syntax**
```js
for (let key in object) {
  // code
}
```

**Classic Example**
```js
const student = {
  name: "Riya",
  age: 20,
  course: "JavaScript"
};

for (let key in student) {
  console.log(key + " → " + student[key]);
}
```

**Note**  
`for...in` is mainly for objects. For arrays, prefer `for...of`.

---

#### Activity Time – for...in

1. Create an object of your favorite movie (title, year, rating) and print all keys and values using `for...in`.  
2. Count how many properties an object has using only `for...in` (without `Object.keys()`).  
3. Given a marks object, calculate the total marks using `for...in`.

---

### 5. for...of Loop

Used to loop through the **values** of arrays, strings, and other iterables.

**Syntax**
```js
for (let value of iterable) {
  // code
}
```

**Classic Example – Array**
```js
const fruits = ["Apple", "Banana", "Mango"];
for (let fruit of fruits) {
  console.log(fruit);
}
```

**Classic Example – String**
```js
const str = "Hello";
for (let char of str) {
  console.log(char);
}
```

---

#### Activity Time – for...of

1. Print all elements of an array `[10, 20, 30, 40, 50]` using `for...of`.  
2. Print each character of the string `"CodingGita"` using `for...of`.  
3. Find the largest number in an array using only `for...of` (no `Math.max`).  
4. Count how many vowels are present in a string using `for...of`.

---

### Quick Comparison Table

| Loop Type     | Best For                     | Gives          | Runs at least once? |
|---------------|------------------------------|----------------|---------------------|
| `for`         | Known number of times        | Index          | No                  |
| `while`       | Unknown number of times      | Condition      | No                  |
| `do...while`  | Must run at least once       | Condition      | Yes                 |
| `for...in`    | Object properties (keys)     | Keys           | No                  |
| `for...of`    | Arrays & Strings             | Values         | No                  |

---

**Teacher’s Quick Tips**
- Always make sure the loop condition becomes false one day → otherwise infinite loop.
- Prefer `for...of` for arrays and strings.
- Prefer `for...in` only for objects.
- Practice pattern printing daily – it makes nested loops crystal clear.

These notes are short, interactive, and perfect for beginners. Practice every Activity Time section!
