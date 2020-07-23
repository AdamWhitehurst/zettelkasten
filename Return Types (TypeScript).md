---

id: 202007221539
tags: [ #typescript #javascript #programming ]
source:

---

# Return Types in TypeScript
Specify what the Type of the returned value of a [[Function]] will be. Denoted by appending a colon, and the type of return to the end of a function signature:
```js

function add(x: number, y: number): number {
	return x + y;
}
```
In this example, `: number` specifies the return type for `add` function.

## References
https://www.typescriptlang.org/docs/handbook/functions.html
