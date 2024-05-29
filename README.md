# (FIXED) `pnpm install` bug

## This bug has been fixed at some point, it does not occur on `6.10.0-rc1-00021-ge0cce98fe279`

A very weird bug I encountered after a system update.  
Tested only on arch linux.  
The bug occurs only on linux kernel versions `linux-6.9.1.arch1-1` or higher.
It does not occur on `linux-6.8.9.arch1-2`.  

The `pnpm` version didn't seem to make a difference in my testing, but here it is anyways.  
```bash
> pnpm --version
9.1.1
```
The `8.8.0` version of `pnpm` also didn't work.  

`npm install` and `bun install` work fine.  

## Reproduce steps

- Make sure you're running linux kernel version `linux-6.9.1.arch1-1` or higher
- Clone this repository
- Run `pnpm install`

The following error message should appear:

```
> pnpm-install-bug-bad-interpreter@1.0.0 prepare ~/pnpm-install-bug-bad-interpreter
> hello-world-npm

sh: ~/pnpm-install-bug-bad-interpreter/node_modules/.bin/hello-world-npm: /bin/sh: bad interpreter: Text file busy
 ELIFECYCLE  Command failed with exit code 126.
```

If it shows the `Hello world NPM` message appears, this means that the bug does not occur.  
