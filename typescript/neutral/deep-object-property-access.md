# 🏗️ Deep Object Property Access Utility

**Scenario**: In many applications, you often need to safely access deeply nested properties in objects, especially when dealing with data from APIs or user input. Your task is to create a type-safe utility function in TypeScript that allows safe access to deep properties using a path (array or string), returning a default value if the property does not exist.

**Challenge**: Implement a utility function `getDeepValue` that takes an object, a path (as an array of keys or a dot-separated string), and an optional default value. The function should return the value at the specified path or the default value if the path does not exist. The solution must be type-safe and handle edge cases (e.g., null/undefined, non-object values).

## 📋 Requirements

- **Functionality**:
  - Accepts an object, a path (array of keys or dot-separated string), and an optional default value.
  - Returns the value at the specified path, or the default value if the path does not exist.
  - Type-safe: infers the return type based on the object and path.
  - Handles edge cases (null/undefined, non-object values, empty path).
- **No UI**: This is a pure logic utility—no UI or framework required.
- **Testing**: Include example usages and test cases.

## 🛠 Example

```typescript
const data = { user: { profile: { name: 'Alice', age: 30 } } };
getDeepValue(data, ['user', 'profile', 'name']); // 'Alice'
getDeepValue(data, 'user.profile.age'); // 30
getDeepValue(data, ['user', 'address', 'city'], 'Unknown'); // 'Unknown'
```

## 📝 Notes

- Use TypeScript generics and types for safety.
- Do not use external libraries (e.g., lodash/get).
- Focus on clean, reusable code and good type inference.

## ✨ Task

Implement the utility and provide example usages and test cases in a TypeScript playground, Codesandbox, or similar. No UI is required.

## 📦 Answers

[@mo0hamedRadwan](https://codesandbox.io/p/sandbox/deep-object-property-access-utility-gl2n6t)
