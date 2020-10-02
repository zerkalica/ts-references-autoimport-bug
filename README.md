# Wrong autoimport presense for dependency not in package.json

https://github.com/microsoft/TypeScript/issues/40911

Package 'b' depends only on 'c', package 'c' depends on 'a'.

Autoimport in any file in 'b' sees 'a' as a relative import.

Steps to reproduce

1. Clone, switch to wrong-autoimport-presense branch, yarn install
2. Open lib/b/b.ts in vscode, type someA
3. Expected: no autoimport, actual: autoimport present and broken (relative)
