# Broken autoimport of module without index reexport

https://github.com/microsoft/TypeScript/issues/40913

## Example 1

Package 'b' depends on 'a', but 'a' has no index.ts and types in package.json.

Steps to reproduce

1. clone, switch to no-autoimport-wo-index, yarn install
2. Open lib/b/b.ts in vscode, type `someA`
3. Expected: autoimport suggest `import { someA } from '@some/lib-a/a'`, actual: no autoimport

## Example 2

Package 'd' depends only on 'c', 'c' depends on 'a', but 'a' has no index.ts and types in package.json.

Steps to reproduce

1. clone, switch to no-autoimport-wo-index, yarn install
2. Open lib/d/d.ts in vscode, type `someA`
3. Expected: no someA in autoimport, actual: autoimport suggests broken `import { someA } from '../a/a'`
