---

id: 202007221606
tags: [ #programming #typescript ]
source: https://basarat.gitbook.io/typescript/main-1/barrel

---

# Barrel
A way to rollup exports from several [[Module|modules]] into a single convenient module. The barrel itself is also a module, that imports from other modules. Its sole purpose is to re-export selected exports of the modules it imports.

###### Example (TypeScript)
imagine you have three separate files in the `demo/` directory, with `class` definitions:
```js
// demo/foo.ts
export class Foo {}

// demo/bar.ts
export class Bar {}

// demo/baz.ts
export class Baz {}
```
This would require three imports in another file, like so:
```js
// otherFolder/script.ts:

import { Foo } from '../demo/foo';
import { Bar } from '../demo/bar';
import { Baz } from '../demo/baz';
```
But you could use a barrel called `demo/index.ts` ...
```js
// demo/index.ts
export * from './foo'; // re-export all of its exports
export * from './bar'; // re-export all of its exports
export * from './baz'; // re-export all of its exports
```
... To make the original import look like:
```js
// otherFolder/script.ts: 

// demo/index.ts is implied by JS import rules
import { Foo, Bar, Baz } from '../demo';

```

## References
https://scrimba.com/p/pKwrCg/cN727S3

