# `pnpm install` bug

A very weird bug I encountered after a system update.  
Tested only on arch linux.  
The bug occurs only on linux kernel versions `linux-6.9.1.arch1-1` or higher.
It does not occur on `linux-6.8.9.arch1-2`.  

The `pnpm` version didn't seem to make a difference in my testing, but here it is anyways.  
```bash
> pnpm --version
9.1.1
```

`npm install` and `bun install` work fine.  

## Reproduce steps

- Make sure you're running linux kernel version `linux-6.9.1.arch1-1` or higher
- Clone this repository
- Run `pnpm install`

The following error message should appear:

```
> pnpm-install-bug-bad-interpreter@1.0.0 prepare ~/pnpm-install-bug-bad-interpreter
> tsc

sh: ~/pnpm-install-bug-bad-interpreter/node_modules/.bin/tsc: /bin/sh: bad interpreter: Text file busy
 ELIFECYCLE  Command failed with exit code 126.
```
