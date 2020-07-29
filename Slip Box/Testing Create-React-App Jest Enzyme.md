# Set Up Testing with Node.js, Mocha, and Chai
The is a brief set of instructions guiding you through setting up a minimal testing environment using [[NodeJS]], [[Jest]], and [[Enzyme]].

***You are highly encouraged to follow external links to understand the significance of what you are doing / using. You need to be familiar with these resources for later reference***

---

1. Install [Node.js](https://nodejs.org/en/download/)
2. In terminal, `cd` into the dir you want to be the **parent** of your project folder and run `npx create-react-app skills`
    - This downloads (if you don't already have it) and runs [`create-react-app`](https://github.com/facebook/create-react-app)
    - `create-react-app` comes preinstalled with [Jest](https://jestjs.io/)
3. `cd skills`
4. Install [Enzyme](https://enzymejs.github.io/enzyme/) and its [[React]] adapter package: `npm i --save-dev enzyme enzyme-adapter-react-16` as [[Dev Dependency|Dev Dependencies]]
5. Inside `skills/src/` you will see `App.js` and `App.test.js` files. The first is the actual App component, and the second is a file containing tests for that component. [`*.test.js` is the idomatic pattern for test files relating to `*`](https://create-react-app.dev/docs/running-tests/)
6. Inside the `src/` dir, make a new file called [`setupTests.js`](https://create-react-app.dev/docs/running-tests/#initializing-test-environment)
7. Add the following code to `setupTests.js`: 
```js
// ES6 syntax
import { configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

// https://enzymejs.github.io/enzyme/docs/installation/react-16.html
configure({ adapter: new Adapter() }});
```
8. In `App.test.js`, add the following test code:
```js
import { shallow } from 'enzyme';

// -snip-

// Add `describe` for scope
// https://jestjs.io/docs/en/api#describename-fn
describe('App', () => {
  it('Should have only one child component', () => {
    // shallow-render our component
    // https://enzymejs.github.io/enzyme/docs/api/ShallowWrapper/shallow.html
    const comp = shallow(<App />);
    // Expect is like assert
    // https://jestjs.io/docs/en/expect
    expect(comp).toHaveLength(1);
  });
});

```
9. In terminal, run `npm test` and you should see two tests have passed, and the `describe` scope has organized your custom-added tests into different scopes! Neat!
10. Now add the following test that actually finds a component in the shallow-rendered DOM:
```js
describe('App', () => {

  // -snip-

  it('Should have Logo component', () => {
    const comp = shallow(<App />);
    // Find the element by selector
    // https://enzymejs.github.io/enzyme/docs/api/ReactWrapper/find.html
    const logo = comp.find('.App-logo');
    expect(logo.length).toBe(1);
  });
});
```

## Snapshot Test
11. To add a [[Snapshot Testing|Snapshot Test]], [`npm install react-test-renderer`](https://reactjs.org/docs/test-renderer.html), then add the following test code:
```js
import renderer from 'react-test-renderer';

// -snip-

describe('App', () => {
  it('Matches Header component', () => {
  	// Save DOM Tree as a json tree
    const tree = renderer.create(<App/>).toJSON();
    // https://jestjs.io/docs/en/snapshot-testing
    expect(tree).toMatchSnapshot();
    
    // The first time this runs, a snapshot of
    // this component will be saved by Jest
  });
});

```
- See [[Snapshot Testing]] for details

## See Also
[[FSD Front-end Development Testing Tools Notes]]
[[Testing Node Mocha Chai]]

## References
Jest Cheatsheet: https://devhints.io/jest

---

id: 202007281156
tags: [ #javascript #webdev #programming ]
primary source:

---