---

id: 202007231011
tags:
 - #javascript
 - #typescript
 - #programming
source: https://basarat.gitbook.io/typescript/type-system/generics

---

# Generics in TypeScript
Generics are a way to define meaningful type dependencies between members. Members include:
- [[Class]] instance members
- Class Methods
- [[Function]] arguments
- function return values

Generics are defined in as a list of aliases, inside angled brackets, of class or function signatures:
`function reverse<T>(Items: T[]): T[] { }`

Here, `<T>` defines a Generic Alias. `Items` is an array of whatever concrete type `T` is when called. The `reverse` function will return an array of `T` type. `T` will become a concrete type when the function is called:
```js
// Case 1
let reversedOne = reverse([1, 2, 3]);
// Case 2
let reversedTwo = reverse(['1', '2', '3']);
// Types for both are known statically:
reversedOne[0] = '1';     // Type Error!
reversed[0] = 1;       // Okay
```

In the first case, `T` will be `number[]` so `reverse` returns a `number[]`. In the second, `T` is a `string[]` and so `reverse` returns `string[]` as well

Generics allow [[Models (TypeScript)|Models]] to be statically-typed, strongly typed, and flexible for a variety of scenarios. For instance:

```js
// A typical FIFO Queue class
class Queue {
  private data = [];
  push(item) { this.data.push(item); }
  pop() { return this.data.shift(); }
}
```
This Queue class is very flexible, but that also means you can push multiple types into the Queue, and you have no guarantee about what will pop out!
```js
const queue = new Queue();
queue.push(0);
queue.push("1"); // Oops a mistake
```
You could try to enforce a specific data type as follows, but this would require a seperate Queue class model for each type you want to use:
```js
class QueueNumber extends Queue {
  push(item: number) { super.push(item); }
  pop(): number { return this.data.shift(); }
}
```
Enter Generics.
## References
https://codingblast.com/typescript-union-types-type-guards-type-aliases/
