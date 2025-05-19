# 🔍 Debounced Search Input with API Integration

**Scenario**: You are building a search feature for a web application. The search input should fetch results from an API, but to avoid excessive requests, you need to debounce the input. The solution should be type-safe and user-friendly, providing feedback during loading and handling errors gracefully.

**Challenge**: Implement a debounced search input component that fetches data from a mock API endpoint as the user types. The component should only trigger the API call after the user stops typing for a specified delay (e.g., 400ms). You may use any frontend framework (React, Angular, Vue, etc.), but your solution must be written in TypeScript.

## 📋 Requirements

- **Debounced Input**:
  - Wait for a pause in typing (e.g., 400ms) before making the API call.
  - Cancel previous requests if the user types again before the delay.
- **API Integration**:
  - Use a mock API endpoint (e.g., https://jsonplaceholder.typicode.com/users?q=your_query).
  - Display search results in a list below the input.
  - Show a loading indicator while fetching.
  - Display an error message if the API call fails.
- **Type Safety**:
  - Use TypeScript types for API responses and component state.
- **Framework Choice**:
  - You may use any frontend framework (React, Angular, Vue, etc.).
  - Clearly indicate your chosen framework in your answer.
- **User Experience**:
  - Handle empty states (no results, no input).
  - Ensure accessibility (label the input, keyboard navigation for results).

## 🛠 Example

```typescript
// Example API endpoint usage (fetch users by name)
fetch('https://jsonplaceholder.typicode.com/users?q=alice')
  .then(res => res.json())
  .then(data => console.log(data));
```

## 📝 Notes

- Use TypeScript for all code.
- You may use libraries/utilities for debouncing (e.g., lodash.debounce) or implement your own.
- Focus on clean, maintainable code and a good user experience.
- You may use mock data or a public API for demonstration.

## 🚀 Task

Create a Codesandbox (or similar) example that demonstrates your solution. Clearly indicate which framework you used.

## 📦 Answers

[@ahmedxwael](https://codesandbox.io/p/sandbox/ymynxh)
[@ahmed-soltan](https://codesandbox.io/p/sandbox/type-safe-feature-toggle-handler-cjr2yq)
[@mo0hamedRadwan](https://codesandbox.io/p/devbox/q45ccc)
[@0xyosef](https://codesandbox.io/p/devbox/staging-bush-447psy)
