# Bug 1. Autocomplete doesn't work if typescript in devDependencies in root package.json.
 
 Steps to reproduce
 
1. clone, yarn install
1. switch to broken-autoimport-b branch
2. Open lib/b/b.ts in vscode, type `someC`
3. Expect to see someC in autocomplete, what i see: no someC in autocomplete
 
Autocomplete works if typescript in dependencies

1. Replace devDependencies to dependencies in root package.json
2. Restart tsserver or vscode
3. Open lib/b/b.ts in vscode, type `someC`
4. Expect to see someC in autocomplete, what i see: someC present in autocomplete

# Bug 2. Autocomplete doesn't work via references in tsconfig.json

https://github.com/microsoft/TypeScript/issues/39778

Steps to reproduce

1. yarn install
2. Open lib/b/b.ts in vscode, type `someA`
3. Expect to see someA in autocomplete

Currently autocomplete works only with includes (cpu eating on big projects) and with types in package.json.
