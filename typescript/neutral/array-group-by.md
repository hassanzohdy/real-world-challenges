# 🗂️ Generic Array groupBy Utility

**Scenario**: Grouping items in an array by a specific property or computed key is a common task in data processing and reporting. Your task is to implement a generic, type-safe `groupBy` utility function in TypeScript that can group array items by any key or function.

**Challenge**: Write a function `groupBy` that takes an array and a key (string) or a key-extracting function, and returns an object where each key is a group and the value is an array of items in that group. The solution should be type-safe and work with any array of objects or values.

## 📋 Requirements

- **Functionality**:
  - Accepts an array and a key (string) or a function to extract the group key.
  - Returns an object mapping group keys to arrays of items.
  - Type-safe: infers types for keys and values.
- **No UI**: This is a pure logic utility—no UI or framework required.
- **Testing**: Include example usages and test cases.

## 🛠 Example

```typescript
const users = [
  { id: 1, role: "admin" },
  { id: 2, role: "user" },
  { id: 3, role: "admin" },
];
const grouped = groupBy(users, "role");
// {
//   admin: [ { id: 1, role: 'admin' }, { id: 3, role: 'admin' } ],
//   user: [ { id: 2, role: 'user' } ]
// }

const numbers = [1, 2, 3, 4, 5, 6];
const evenOdd = groupBy(numbers, (n) => (n % 2 === 0 ? "even" : "odd"));
// {
//   odd: [1, 3, 5],
//   even: [2, 4, 6]
// }
```

## 📝 Notes

- Use TypeScript generics and types for safety.
- Do not use external libraries (e.g., lodash/groupBy).
- Focus on clean, reusable code and good type inference.

## ✨ Task

Implement the utility and provide example usages and test cases in a TypeScript playground, Codesandbox, or similar. No UI is required.

## 📦 Answers

[@mo0hamedRadwan](https://codesandbox.io/p/sandbox/intelligent-rgb-vfgvmy)
