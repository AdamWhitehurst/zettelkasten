---

id: 202007221555
tags:
 - #programming
source: https://en.wikipedia.org/wiki/Interface_(computing)

---

# Interface
Used to mean either:
 - A shared boundary between two or more separate parts of a computer system.
 - An abstract type that contains no data but defines behaviors / fields in its signature.
 
 Think of an interface as a *contract*. When one part of code defines an interface, it is making a contract to say: "An object with this interface will provide these methods--with specific return types--and have these fields."

Convention is to prepend interface names with `I` to denote that it is an interface. This is optional and depends on the language.

###### TypeScript Example
```js

export interface IPerson {
	firstName: string;
	middleName: string;
	lastName: string;
	// this member is optional
	age?: number;
};

```


## References
https://basarat.gitbook.io/typescript/type-system/interfaces
https://coryrylan.com/blog/rich-domain-models-with-typescript