---

id: 202007230931
tags: #javascript #typescript #programming
source: https://coryrylan.com/blog/rich-domain-models-with-typescript

---

# Models in TypeScript
Models are a normal Class definition of a specific domain within your code, following [[Domain-Driver Design]] principles. The goal of a model is to separate implementation and enforce business logic.

Models allow Classes to define [[Access Modifiers]] to its members.

```js

export class User {
  private _firstName: string;
  private _age: number;

  get firstName() {
    return this._firstName;
  }

  get age() {
    return this._age;
  }

  constructor(firstName: string, age: number) {
    this.setName(firstName);
    this.setAge(age);
  }

  setName(firstName: string) {
    // Enforce Business Logic:
    if (this.validName(firstName)) {
      this._firstName = firstName;
    }
  }

  setAge(age: number) {
  	// Enforce Business Logic:
    if (age >= 18) {
      this._age = age;
    } else {
      throw new Error('User age must be greater than 18');
    }
  }

  private validName(name: string) {
    if (name.length > 0 && /^[a-zA-Z]+$/.test(name)) {
      return true;
    } else {
      throw new Error('Invalid name format');
    }
  }
}

const user = new User('John', 18);
user.setName('Jack');
console.log(user.firstName); // Jack

const user2 = new User('John', 17);
// Error: User age must be greater than 18

```
## References

