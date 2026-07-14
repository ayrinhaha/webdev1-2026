# Advanced JavaScript Activity: Answer Template

## Task 1: Data Structures & References

```javascript
const library = {
  books: [
    { title: "The Hobbit", author: "J.R.R. Tolkien", isAvailable: true },
    { title: "1984", author: "George Orwell", isAvailable: true },
    { title: "To Kill a Mockingbird", author: "Harper Lee", isAvailable: false }
  ]
};

const copiedLibrary = { ...library };

copiedLibrary.books[0].isAvailable = false;

console.log(library);
console.log(copiedLibrary);

/*
The spread operator creates a shallow copy. Both objects share the same
books array, so changing a book in the copied library also changes the
original. A deep copy can be created using structuredClone(library) or
JSON.parse(JSON.stringify(library)).
*/
```

---

## Task 2: Advanced Conditional Logic (Validation)

```javascript
function validatePassword(password) {
  if (password.length < 8) {
    return "Error: Password must be at least 8 characters long.";
  }

  if (!/[A-Z]/.test(password)) {
    return "Error: Password must contain at least one uppercase letter.";
  }

  if (!/\d/.test(password)) {
    return "Error: Password must contain at least one number.";
  }

  if (/password/i.test(password)) {
    return 'Error: Password must not contain the word "password".';
  }

  return "Strong Password";
}

console.log(validatePassword("abc"));
console.log(validatePassword("abcdefgh"));
console.log(validatePassword("Abcdefgh"));
console.log(validatePassword("Password123"));
console.log(validatePassword("Secure123"));
```

---

## Task 3: Complex Iteration (Algorithms)

```javascript
function generateFibonacci(n) {
  const fibonacci = [];

  for (let i = 0; i < n; i++) {
    if (i === 0) {
      fibonacci.push(0);
    } else if (i === 1) {
      fibonacci.push(1);
    } else {
      fibonacci.push(fibonacci[i - 1] + fibonacci[i - 2]);
    }
  }

  return fibonacci;
}

console.log(generateFibonacci(7));
```

---

## Task 4: Higher-Order Functions & Callbacks

```javascript
function processData(dataArray, callback) {
  return dataArray.map(callback);
}

const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = processData(numbers, number => number * number);

console.log(squaredNumbers);
```

---

## Task 5: Functional Array Methods (Map, Filter, Reduce)

```javascript
const transactions = [
  { type: "deposit", amount: 150 },
  { type: "withdrawal", amount: 50 },
  { type: "deposit", amount: 200 },
  { type: "withdrawal", amount: 80 }
];

const balance = transactions.reduce((total, transaction) => {
  return transaction.type === "deposit"
    ? total + transaction.amount
    : total - transaction.amount;
}, 0);

console.log(balance);
```
