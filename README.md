This repo is a demonstration of a tsproject typing loading bug [being discussed](https://github.com/ToddThomson/tsproject/pull/82#issuecomment-206523884)

To replicate the bug, simply clone this repo and run `tsc` in it. You should get:

```
1 import * as tsproject from 'tsproject';
                             ~~~~~~~~~~~

test.ts(1,28): error TS2307: Cannot find module 'tsproject'.
```
