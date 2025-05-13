# 🌲 Efficient Immutable Data Structure (Persistent Map/Tree)

**Scenario**: In modern applications, especially those involving state management, undo/redo functionality, collaborative editing, or time-travel debugging, immutable data structures are essential for performance, reliability, and advanced features. Your task is to design and implement an efficient, type-safe immutable data structure (such as a persistent map or tree) in TypeScript that can support these real-world scenarios.

**Challenge**: Build a persistent (immutable) map or tree data structure that allows efficient updates (set, delete), retrievals, and versioning, while preserving previous versions for features like undo/redo, collaborative editing, and state snapshots. The solution should be type-safe, performant, and easy to use in a variety of advanced use cases.

## 📋 Requirements

- **Core Functionality**:
  - Implement a persistent (immutable) map or tree structure.
  - Support efficient set, get, and delete operations.
  - Each update returns a new version, preserving previous versions (structural sharing encouraged).
  - Type-safe interfaces for all operations.
  - **You must implement the provided interface below.**
- **Advanced Use Cases**:
  - **Undo/Redo**: Allow traversing backward and forward through previous versions.
  - **Time-Travel Debugging**: Enable inspection of any previous state/version.
  - **Collaborative Editing**: Support merging changes from multiple users (basic merge logic is sufficient).
  - **State Snapshots**: Allow saving and restoring named snapshots of the data structure.
- **Performance**:
  - Optimize for minimal memory usage and fast operations (avoid deep cloning).
- **Extensibility**:
  - Easy to extend for additional features (e.g., branching, conflict resolution).
- **Testing**:
  - Provide example usage and test cases demonstrating immutability, efficiency, and advanced features.
- **No UI**: This is a pure logic/data structure challenge.

## 🧩 Interface to Implement

```typescript
interface PersistentMapInterface<K, V> {
  /**
   * Returns a new PersistentMap with the given key set to the specified value.
   * Does not mutate the original map.
   */
  set(key: K, value: V): PersistentMapInterface<K, V>;

  /**
   * Retrieves the value associated with the given key, or undefined if not present.
   */
  get(key: K): V | undefined;

  /**
   * Returns a new PersistentMap with the given key removed.
   * Does not mutate the original map.
   */
  delete(key: K): PersistentMapInterface<K, V>;

  /**
   * Merges another PersistentMap into this one, returning a new PersistentMap containing keys/values from both.
   * In case of conflicts, values from the other map may take precedence (implementation-defined).
   */
  merge(other: PersistentMapInterface<K, V>): PersistentMapInterface<K, V>;

  /**
   * Serializes the current state of the map to a string (optionally with a name for the snapshot).
   */
  snapshot(name?: string): string;
}

interface PersistentMapStatic {
  /**
   * Restores a PersistentMap from a serialized snapshot string.
   */
  restore<K, V>(snapshot: string): PersistentMapInterface<K, V>;
}
```

Your class should implement `PersistentMapInterface<K, V>`. You may also provide a static `restore` method as shown above for restoring from a snapshot.

## 🛠 Example

```typescript
// Basic usage
const map1 = new PersistentMap<string, number>();
const map2 = map1.set("a", 1);
const map3 = map2.set("b", 2);
const map4 = map3.delete("a");

console.log(map1.get("a")); // undefined
console.log(map2.get("a")); // 1
console.log(map3.get("b")); // 2
console.log(map4.get("a")); // undefined

// Undo/Redo
const history = [map1, map2, map3, map4];
let current = history[3]; // map4
current = history[1]; // undo to map2
console.log(current.get("a")); // 1

// Time-travel debugging
function inspectVersion(version: PersistentMapInterface<string, number>) {
  // Print or analyze the state at this version
}
inspectVersion(history[0]); // Initial state
inspectVersion(history[2]); // After adding 'b'

// State snapshots
const snapshot = map3.snapshot("before-delete");
// ... make more changes
const restored = PersistentMap.restore(snapshot);
console.log(restored.get("a")); // 1

// Collaborative editing (basic merge)
const user1 = map1.set("a", 1);
const user2 = map1.set("b", 2);
const merged = user1.merge(user2); // Should contain both 'a' and 'b'
console.log(merged.get("a")); // 1
console.log(merged.get("b")); // 2
```

## 📝 Notes

- Use TypeScript for all code and interfaces.
- Focus on structural sharing for efficiency (avoid full copies on each update).
- You may implement a persistent map, tree, or similar structure.
- Implementing full CRDTs is not required, but basic merge logic is encouraged.
- No UI or framework required.

## 🚀 Task

Implement the data structure and provide example usages and test cases in a TypeScript playground, Codesandbox, or similar. Demonstrate advanced features like undo/redo, time-travel, snapshots, and merging. No UI is required.

## 📦 Answers

[@your_github_username](your-solution-link)
