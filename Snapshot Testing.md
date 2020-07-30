# Snapshot Testing
Ensures your [[UI]] does not change by comparing a currently-rendered component to a snapshot of that component when it was considered to be properly rendered. Test will fail if there are any differences.

> A typical snapshot test case for a mobile app renders a UI component, takes a snapshot, then compares it to a reference snapshot file stored alongside the test. The test will fail if the two snapshots do not match: either the change is unexpected, or the reference snapshot needs to be updated to the new version of the UI component.

## Example
Example test using [[Jest]]:
```js
import React from 'react';
import Link from '../Link.react';
import renderer from 'react-test-renderer';

it('renders correctly', () => {
  const tree = renderer
    .create(<Link page="http://www.facebook.com">Facebook</Link>)
    .toJSON();
  expect(tree).toMatchSnapshot();
});
```
Matching snapshot file:
```js
exports[`renders correctly 1`] = `
<a
  className="normal"
  href="http://www.facebook.com"
  onMouseEnter={[Function]}
  onMouseLeave={[Function]}
>
  Facebook
</a>
`;
```

## Updating Snapshots
Example failing snapshot test in [[Jest]]:
![[Pasted image 45.png]]

When a test fails due to an intentional change to UI, the snapshot must be updated (In [[Jest]] using `jest --updateSnapshot`)

## See Also
[[Testing Create-React-App Jest Enzyme#Snapshot Test]]

## References
Updating: https://jestjs.io/docs/en/snapshot-testing#updating-snapshots
Why: https://jestjs.io/blog/2016/07/27/jest-14.html#why-snapshot-testing
What: https://benmccormick.org/2016/09/19/testing-with-jest-snapshots-first-impressions/
Jest Cheatsheet: https://devhints.io/jest

---

id: 202007281249
tags: #javascript #programming #webdev #testing
primary source: https://jestjs.io/docs/en/snapshot-testing

---