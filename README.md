Autocomplete not working via references in tsconfig.json

Steps to reproduce

1. type `someA` in `b/b.ts`
2. Expect to see someA in autocomplete

Currently autocomplete working only with includes (cpu eating on big projects) and with types in package.json.

Autocomplete doesn't work with direct imports (without "types" in package.json)
