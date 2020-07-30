# Set Up Testing with Node.js, Mocha, and Chai
The is a brief set of instructions guiding you through setting up a minimal testing environment using [[NodeJS]], [[Mocha]], and [[Chai]].

***You are highly encouraged to follow external links to understand the significance of what you are doing / using. You need to be familiar with these resources for later reference***

---

1. Install [Node.js](https://nodejs.org/en/download/)
2. In terminal, `cd` into the dir you want to turn into your project folder and run `npm init` 
    - you may use defaults
3. Run `npm install --save-dev mocha` to install [Mocha](https://mochajs.org/) as a [[Dev Dependency]]
4. Open `package.json` found inside your new project folder.
5. Change `"test":` to: `"test": "mocha"` ([NPM Package scripts](https://docs.npmjs.com/misc/scripts))
6. In the project folder, make a new file `test.js`, where we will write a test.
7. In that file, add the following code:
```js
// https://www.w3schools.com/nodejs/ref_assert.asp
const assert = require('assert');

// `it` is and alias for `test`
// https://mochajs.org/#getting-started
it ('should be equal', () => {
  assert.equal(5, 7);
});
```
9. In terminal, run `npm test`, you will see an output showing test results. The single test will have failed (Who'd be so silly as to assert 5 equals 7?)
10. In terminal, run `npm install --save-dev chai` to install [Chai](https://www.chaijs.com/) as a [[Dev Dependency]]
11. In `test.js` file, change the code as follows:
```js
// https://www.chaijs.com/api/assert/
const assert = require('chai').assert;

it ('should be equal', () => {
  assert.typeOf('Adam', 'string');
});
```
12. In terminal, run `npm test`, you will see an output showing test results. The test passed!
13. 
## See Also
[[FSD Front-end Development Testing Tools Notes]]

## References

---

id: 202007281155
tags: #javascript #webdev #programming
primary source:

---