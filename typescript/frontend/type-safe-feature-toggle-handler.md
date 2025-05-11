# 🌟 Type-Safe Feature Toggle Handler

**Scenario**: You are a software engineer building a feature toggle system for a SaaS application. The backend API (`/api/feature-toggles`) returns a list of feature toggles, but the data is messy due to legacy issues (e.g., missing fields, wrong types). Your task is to create a **type-safe** TypeScript utility to clean up the API response and provide a reliable interface for the frontend team.

**Challenge**: Write a `fetchFeatureToggles` function that processes a raw API response, validates it, and returns a clean, type-safe list of feature toggles. Include a method to check if a specific feature is enabled.

## 📋 Requirements

- **Feature Toggle Structure**:
  - `name`: string (required, non-empty)
  - `enabled`: boolean (required)
  - `variant`: string (optional, defaults to empty string if null/undefined)
- **Function Behavior**:
  - Input: Raw API response (type `any` to simulate real-world messiness)
  - Output: Object with:
    - `getToggles`: Returns the cleaned array of `FeatureToggle` objects
    - `isFeatureEnabled`: Checks if a feature is enabled (case-insensitive name matching)
  - Validate data: Filter out invalid toggles (e.g., missing `name`/`enabled`, wrong types)
  - Throw descriptive errors for invalid input (e.g., non-array response)
- **Handle Real-World Edge Cases**:
  - Null/undefined entries
  - Deprecated fields (e.g., `isActive` instead of `enabled`)
  - Malformed data (e.g., `enabled` as a string)
  - Empty response arrays

## 🛠 Example

```typescript
// Mock API response (messy, real-world data)
const rawApiResponse = [
  { name: "darkMode", enabled: true, variant: "v1" },
  { name: "analytics", enabled: "true" }, // Invalid: enabled should be boolean
  { name: "", enabled: false }, // Invalid: empty name
  { name: "notifications", isActive: true }, // Deprecated field
  null, // Invalid: null entry
];

// Expected usage
const toggleManager = fetchFeatureToggles(rawApiResponse);
console.log(toggleManager.getToggles());
// [{ name: "darkMode", enabled: true, variant: "v1" }]
console.log(toggleManager.isFeatureEnabled("DARKMODE")); // true
console.log(toggleManager.isFeatureEnabled("analytics")); // false
```

## 📝 Notes

- Use TypeScript types to ensure data integrity
- Implement error handling for invalid input
- Ensure the utility is flexible and can handle future changes in the API response

## 🎯 Task

Please create a Codesandbox example that demonstrates the solution to the challenge.

## 📦 Answers

[@mo0hamedRadwan](https://codesandbox.io/p/devbox/sharp-currying-3s6r77)
[@ahmed_wael](https://codesandbox.io/p/sandbox/rx2n4y)
