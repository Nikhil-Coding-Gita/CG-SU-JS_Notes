**Activity Questions & Answers**  
**Conditional Statements**

---

### 1. `if` Statement

**Q1.** Write a program to check if a number is even.  
```js
let num = 8;

if (num % 2 === 0) {
  console.log("Even number");
}
```

**Q2.** Check if the temperature is greater than 30°C and print “It’s Hot”.  
```js
let temperature = 35;

if (temperature > 30) {
  console.log("It’s Hot");
}
```

**Q3.** Check if a person’s age is 18 or above and print “Eligible to vote”.  
```js
let age = 20;

if (age >= 18) {
  console.log("Eligible to vote");
}
```

---

### 2. `if...else` Statement

**Q1.** Check whether a number is positive or negative.  
```js
let num = -5;

if (num > 0) {
  console.log("Positive");
} else {
  console.log("Negative");
}
```

**Q2.** Check if a given year is a leap year or not (basic check: divisible by 4).  
```js
let year = 2024;

if (year % 4 === 0) {
  console.log("Leap year");
} else {
  console.log("Not a leap year");
}
```

**Q3.** Check if a character is a vowel or consonant (for a single lowercase letter).  
```js
let char = "e";

if (char === "a" || char === "e" || char === "i" || char === "o" || char === "u") {
  console.log("Vowel");
} else {
  console.log("Consonant");
}
```

---

### 3. `if...else if...else` Statement

**Q1.** Write a program that prints the ticket price based on age  
(Child < 12: ₹100, Adult 12–59: ₹200, Senior ≥ 60: ₹150).  
```js
let age = 25;

if (age < 12) {
  console.log("Ticket Price: ₹100");
} else if (age <= 59) {
  console.log("Ticket Price: ₹200");
} else {
  console.log("Ticket Price: ₹150");
}
```

**Q2.** Check the temperature and print: “Cold” (< 15), “Pleasant” (15–25), “Hot” (> 25).  
```js
let temp = 22;

if (temp < 15) {
  console.log("Cold");
} else if (temp <= 25) {
  console.log("Pleasant");
} else {
  console.log("Hot");
}
```

**Q3.** Find the largest among three numbers.  
```js
let a = 45, b = 78, c = 32;

if (a >= b && a >= c) {
  console.log("Largest number is:", a);
} else if (b >= a && b >= c) {
  console.log("Largest number is:", b);
} else {
  console.log("Largest number is:", c);
}
```

---

### 4. Nested `if` Statement

**Q1.** Check if a number is positive and divisible by 5.  
```js
let num = 25;

if (num > 0) {
  if (num % 5 === 0) {
    console.log("Positive and divisible by 5");
  }
}
```

**Q2.** Create a simple exam result system:  
first check if marks ≥ 35 (pass), then check if marks ≥ 90 (excellent).  
```js
let marks = 92;

if (marks >= 35) {
  console.log("Passed");
  if (marks >= 90) {
    console.log("Excellent");
  }
} else {
  console.log("Failed");
}
```

**Q3.** Check if a user is logged in and is an admin, then show “Admin Panel”.  
```js
let isLoggedIn = true;
let isAdmin = true;

if (isLoggedIn) {
  if (isAdmin) {
    console.log("Admin Panel");
  }
}
```

---

### 5. `switch` Statement

**Q1.** Write a program that prints the month name based on month number (1–12).  
```js
let month = 5;

switch (month) {
  case 1: console.log("January"); break;
  case 2: console.log("February"); break;
  case 3: console.log("March"); break;
  case 4: console.log("April"); break;
  case 5: console.log("May"); break;
  case 6: console.log("June"); break;
  case 7: console.log("July"); break;
  case 8: console.log("August"); break;
  case 9: console.log("September"); break;
  case 10: console.log("October"); break;
  case 11: console.log("November"); break;
  case 12: console.log("December"); break;
  default: console.log("Invalid month");
}
```

**Q2.** Create a grading system using switch (A, B, C, D, F).  
```js
let grade = "B";

switch (grade) {
  case "A":
    console.log("Excellent");
    break;
  case "B":
    console.log("Good");
    break;
  case "C":
    console.log("Average");
    break;
  case "D":
    console.log("Poor");
    break;
  case "F":
    console.log("Fail");
    break;
  default:
    console.log("Invalid grade");
}
```

**Q3.** Build a simple menu: 1 → Pizza, 2 → Burger, 3 → Pasta, and print the selected item.  
```js
let choice = 2;

switch (choice) {
  case 1:
    console.log("You selected Pizza");
    break;
  case 2:
    console.log("You selected Burger");
    break;
  case 3:
    console.log("You selected Pasta");
    break;
  default:
    console.log("Invalid choice");
}
```

---

### 6. Ternary Operator

**Q1.** Check whether a number is positive or negative using ternary.  
```js
let num = -8;
let result = num > 0 ? "Positive" : "Negative";
console.log(result);
```

**Q2.** Assign “Pass” or “Fail” based on marks (≥ 35).  
```js
let marks = 40;
let result = marks >= 35 ? "Pass" : "Fail";
console.log(result);
```

**Q3.** Find the minimum of two numbers using ternary operator.  
```js
let a = 25, b = 18;
let min = a < b ? a : b;
console.log("Minimum is:", min);
```

---

**Note for Mentors:**  
You can change the variable values while checking answers to test different cases (edge cases like 0, negative numbers, boundary values, etc.).
