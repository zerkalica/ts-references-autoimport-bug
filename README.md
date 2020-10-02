# Autocomplete doesn't work if typescript in devDependencies in monorepos root package.json

https://github.com/microsoft/TypeScript/issues/40869

Steps to reproduce

1. Clone, switch to broken-autoimport-b branch, yarn install
2. Open lib/b/b.ts in vscode, type `someC`
3. Expected: autoimport suggest `import {someC} from '@some/lib-c'`, actual: no someC in autoimport

Autocomplete works if typescript present in dependencies section of root package.json:

1. Replace devDependencies to dependencies in root package.json
2. Restart tsserver or vscode
3. Open lib/b/b.ts in vscode, type someC
4.** Expected and actual behavior**: someC in autocomplete
