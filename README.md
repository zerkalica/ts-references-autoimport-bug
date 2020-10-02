# Wrong autoimport presense for dependency not in package.json

https://github.com/microsoft/TypeScript/issues/40911

Package 'b' depends only on 'c', package 'c' depends on 'a'.

Autoimport in any file in 'b' sees 'a' as a relative import.

Steps to reproduce

1. clone, yarn install
2. switch to wrong-autoimport-presense branch
3. Open lib/b/b.ts in vscode, type someA
4. Expected: no autoimport, actual: autoimport present and relative: `import { someA } from '../a'`
