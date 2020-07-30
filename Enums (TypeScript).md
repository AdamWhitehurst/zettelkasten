---

id: 202007221135
tags:
 - #typescript
 - #javascript
 - #programming
source: https://www.typescriptlang.org/docs/handbook/basic-types.html#enum

---

# Enums in TypeScript
Enums provide a convenient way to give friendly names to [[Numbers (TypeScript)]] and/or [[Strings (TypeScript)]] values. This allows us to type check against different sets of values.

The elements of a single Enum do not need to be of the same type. Therefore, there are three types of Enum: 1) Numeric, 2) String, 3) Heterogenous

Enum values can also be computed. When the enum includes computed and constant members, the uninitiated enum members must either come first or must come after other initialized members with constant values

More details and things to watch for when using Enums: https://blog.logrocket.com/why-typescript-enums-suck/

```js
// Enums start numeric values at 0, but can be set manually.
// Subsequent values will continue to increment by 1
enum Colors {
	Red = 3,
	Blue,
	Green,
};

console.log(Color.Green); // 5

enum Age {
	Adam = 24,
	Evan = 26,
	Matt = 30,
};

function totalAge(age1: Age, age2: Age) {
	return age1 + age2;
}

console.log(totalAge(Age.Adam, Age.Evan)); // 50

console.log(totalAge(Age.Adam, 10)); // Type Error! 10 is not an Age

// You can access Enum values by their numeric:
console.log(Age[24]); // Adam

// A Heterogenous Enum
enum FavoriteThings {
	name = 'Adam',
	number = 4,
}

// Computed Enum Values
enum PrintMedia {
	Handwriting,
    Newspaper = 2,
    Newsletter = getPrintMediaCode('newsletter'),
    Magazine = Newsletter * 3,
    Book = 10,
	Tweet,
}

// This would cause an error (uninitiated following a computed)
enum PrintMedia {
    Newsletter = getPrintMediaCode('newsletter'),
    Newspaper, // Error: Enum member must have initializer
    Book,
    Magazine = Newsletter * 3,
}

```


## References
https://www.tutorialsteacher.com/typescript/typescript-enum
