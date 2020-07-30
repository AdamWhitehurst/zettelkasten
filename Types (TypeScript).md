---

id: 202007221517
tags:
 - #javascript
 - #typescript
 - #programming
source: https://www.typescriptlang.org/docs/handbook/basic-types.html

---

# Types in TypeScript
Primitive [[Types (TypeScript)|Types]] are any Type that is not a [[Numbers (TypeScript)|number]], [[Strings (TypeScript)|string]], [[Booleans (TypeScript)|boolean]], [[BigInt (TypeScript)|BigInt]], [[Symbol (TypeScript)|symbol]], [[Null (TypeScript)|null]], or [[undefined (TypeScript)|undefined]]. 

Non-Primitive Types include: [[Objects (TypeScript)|objects]], [[Arrays (TypeScript)|Array]], [[Tuples in TypeScript|Tuples]], along with any [[Custom Types (TypeScript)| Custom-Defined Types]].

Intersection Types are a Type which must implement multiple [[Interface]]s at once. Thus, the intersection will have ALL properties of the intersected Types.

Union Types are a Type which may be any one of several types. You can use Type Guarding techniques to differentiate what concrete type you have when using Union Types.

```js
import { Bear, Man, Pig } from './index';

// May be a Man or Pig type
// This is a Union:
let man: Man | Pig;

// This Type Alias is an Intersection:
type ManBearPig: Man & Bear & Pig;

// This must be ALL of Man, Bear, and Pig Types:
let mBP: ManBearPig;
```


## References
Intersection types: https://codingblast.com/typescript-intersection-types/
Unions, Type Guards, and Type Aliases: https://codingblast.com/typescript-union-types-type-guards-type-aliases/
