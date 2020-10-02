# Auto imports not working with project references

https://github.com/microsoft/TypeScript/issues/39778

1. clone, switch to autoimport-no-ref, yarn install
2. Open lib/b/b.ts in vscode
3. Type someA in - Expected: autoimport suggests import { someA } from '../a', actual: no autoimport
