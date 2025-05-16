# 💸 Accurate Financial Calculator (Floating Point Safe)

**Scenario:**  
Many systems (including major e-commerce and banking platforms) have bugs due to floating point precision errors (e.g., 0.1 + 0.2 !== 0.3). Your task is to implement a type-safe utility in TypeScript for accurate addition, subtraction, multiplication, and division of monetary values, avoiding floating point errors.

**Challenge:**  
Write a utility that performs basic arithmetic on monetary values (as strings or numbers), ensuring results are always correct to two decimal places (e.g., cents). The solution must be robust, type-safe, validate all parameters, and handle edge cases (e.g., rounding, negative values).

## 📋 Requirements

- **Functionality:**
  - Accepts monetary values as strings or numbers.
  - Returns results as strings (to avoid floating point issues).
  - Supports add, subtract, multiply, and divide.
  - Always returns results rounded to two decimal places.
  - Type-safe: use TypeScript types for all inputs and outputs.
  - **Validate all parameters:** Ensure inputs are valid numbers/strings representing valid monetary values. Throw descriptive errors for invalid input.
- **No UI:** Pure logic utility—no UI or framework required.
- **Testing:** Include example usages and test cases (e.g., 0.1 + 0.2, negative values, large numbers, invalid input).

## 🛠 Example

```typescript
addMoney('0.1', '0.2'); // '0.30'
subtractMoney(1.00, 0.42); // '0.58'
multiplyMoney('2.50', 3); // '7.50'
divideMoney('1.00', 3); // '0.33'
addMoney('abc', 1); // throws error
```

## 📝 Notes

- Use TypeScript for all code and interfaces.
- Do not use external libraries for decimal math (no decimal.js, big.js, etc.).
- Focus on correctness, robustness, parameter validation, and clean code.

## ✨ Task

Implement the utility and provide example usages and test cases in a TypeScript playground, Codesandbox, or similar. No UI is required.

## 📦 Answers

[@ahmed-soltan](your-solution-link](https://codesandbox.io/p/sandbox/vanilla-typescript-vanilla-ts)
