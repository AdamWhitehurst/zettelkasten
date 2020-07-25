---

id: 202007231032
tags: [ #programming ]
source: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers

---

# Access Modifiers
Access Modifiers are a principle of [[Object-Oriented Design]] that defines who can use members of a [[Class]]. In other words, it defines the accessibility level of fields on a class. It is similar to scope in that that regard. Access Modifiers include:
- Private: Only this class may access this member
- Protected: This class and decendants may access this member
- Public: Anyone may access this member

Additional features related to access modifiers include:
- readonly: May only be set are initialization. Affterwards, it will behave as a constant
- Internal: The member may only be accessed by code in the same assembly
- Accessors: `get` and `set` methods, which restrict how members are mutated and retrieved

TypeScript Example:
```js
class Foo {
 private x: number;
 protected y: number;
 public z: number;
 
 saveData(foo: Foo): void {
 	this.x = 1; // ok
 	this.y = 1; // ok
 	this.z = 1; // ok

 	foo.x = 1; // ok 
 	foo.y = 1; // ok 
 	foo.z = 1; // ok
 }
}

class Bar extends Foo {
 getData(foo: Foo, bar: Bar) {
 	this.y = 1; // ok
 	this.z = 1; // ok

 	bar.y = 1; // ok
 	bar.z = 1; // ok
	foo.z = 1; // ok

 	foo.x = 1; // Error, x only accessible within A 
 	bar.x = 1; // Error, x only accessible within A 
 	bar.y = 1; // Error, y only accessible through instance of B 
 }
}

```
## References
C# Access Modifiers: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers
Access Modifiers in TypeScript: https://www.dotnettricks.com/learn/typescript/access-modifiers