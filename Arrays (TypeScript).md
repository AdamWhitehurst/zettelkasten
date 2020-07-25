---

id: 202007221103
tags: [ #typescript #javascript #programming ]
source: https://www.typescriptlang.org/docs/handbook/basic-types.html#array

---

# Arrays in TypeScript

A collection of specific [[Types (TypeScript)]]s of data, denoted by that type followed by `[]`. 

[[Element]]s of an Array are access by `arrayName[arrayIndex]`. 

May also be specified with [[Generic Types (TypeScript)]] :. `let list: Array<elemType> = ...`

Array declarations allocate sequential [[memory blocks]]. Each block represents an array element

**Arrays are static**. Unlike [[JavaScript]] arrays, [[TypeScript]] arrays cannot be resized once initialized.

Array element values can be modified, but not deleted.

For methods on `Array` object, see: 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

```js
const arrOne: string[] = ['Hello world'];
// arrOne[0] === 'Hello world'

// any[] means each entry could be anything
const arrTwo: any[] = [{}, true, 'any'];

// To specify and array that may contain multiple types, those
// types need to be within (), otherwise it will be interpretted
// as "arrThree may be a single number or an array of booleans"
const arrThree: (number|boolean)[] = [true, 1, false, 0];

// Multidimensional arrays work too
const arrFour: boolean[][] = [ [true, false] ];

// Preallocating size, this is an array that can hold
// four strings:
const arrFive: string[] = new Array(4);

```


## References
https://www.tutorialspoint.com/typescript/typescript_arrays.htm
https://scrimba.com/p/pKwrCg/cM9dmTP
