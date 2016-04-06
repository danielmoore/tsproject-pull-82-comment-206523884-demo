This repo is a demonstration of a tsproject typing loading bug [being discussed](https://github.com/ToddThomson/tsproject/pull/82#issuecomment-206523884)

To replicate the bug, simply clone this repo and run `tsc` in it. You should get:

```
1 import * as stream from "stream";
                          ~~~~~~~~

node_modules/tsproject/TsProject.d.ts(1,25): error TS2307: Cannot find module 'stream'.


3 tsproject.src('whatever');
            ~~~

test1.ts(3,11): error TS2339: Property 'src' does not exist on type 'typeof "/Users/vbq655/Development/tsproject-demo/node_modules/tsproject/TsProject"'.
```

[`test1.ts`] shows the correct import usage of tsproject - and if you look at the output ([`test1.js`]), the form is correct. It just doesn't typecheck.

[`test2.ts`] shows the correctly typed invocation, but the emitted JavaScript ([`test2.js`]) is incorrect.

[`test1.ts`]: ./test1.ts
[`test2.ts`]: ./test2.ts
[`test1.js`]: ./test1.js
[`test2.js`]: ./test2.js
