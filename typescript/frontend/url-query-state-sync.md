# 🔗 URL Query State Synchronization

**Scenario:**  
Modern web apps often need to keep UI state (like filters, search, or pagination) in sync with the URL query string, so users can share links, use browser navigation, and reload pages without losing state. Your task is to implement a type-safe utility/component in TypeScript that synchronizes UI state with the URL query string.

**Challenge:**  
Build a solution that:
- Reads initial state from the URL query string.
- Updates the URL when the UI state changes (without full page reload).
- Keeps the UI and URL in sync, supporting browser navigation (back/forward).
- Is type-safe and framework-agnostic, but you may use any frontend framework (React, Angular, Vue, etc.).

## 📋 Requirements

- **Functionality:**
  - Syncs UI state (e.g., filters, search, pagination) with the URL query string.
  - Reads initial state from the URL on load.
  - Updates the URL when state changes (push/replace, no reload).
  - Handles browser navigation (back/forward) and keeps UI in sync.
  - Type-safe: use TypeScript types for state and query params.
  - Works with at least two state fields (e.g., `search` and `page`).
- **Framework Choice:**
  - You may use any frontend framework (React, Angular, Vue, etc.).
  - Clearly indicate your chosen framework in your answer.
- **User Experience:**
  - Ensure state is preserved on reload and shareable via URL.
  - Handle empty/invalid query params gracefully.
- **Testing:**
  - Provide example usage and test cases (e.g., changing filters, using browser back/forward).

## 🛠 Example

```typescript
// Example: /products?search=shoes&page=2
// UI state: { search: 'shoes', page: 2 }
// User changes search to 'boots' -> URL updates to /products?search=boots&page=2
// User clicks back -> UI state reverts to { search: 'shoes', page: 2 }
```

## 📝 Notes

- Use TypeScript for all code and interfaces|types.
- You may use browser APIs (window.location, history.pushState, etc.) or framework utilities.
- Focus on clean, reusable, and type-safe code.

## ✨ Task

Implement the solution and provide example usages and test cases in a Codesandbox (or similar). Clearly indicate which framework you used. No backend or UI design required beyond state/query sync.

## 📦 Answers

[@0xyosef](https://codesandbox.io/p/devbox/url-query-state-74tn7l) 

