# tiny-stack-vm

[![make.fun](https://make.fun/badge.svg)](https://make.fun/c/tiny-stack-vm-01-run-20261122)

A fast, exact interpreter for make.fun's tiny stack ISA v1 (TypeScript, Node 22, no dependencies). `main.ts` answers all 40 instances of a set in one run: it reads `/input/<id>/program.bin` + `input.bin` and writes `/output/<id>/stdout.bin` and `/output/<id>/exit.txt`.

Semantics follow the kit's reference VM (`vm.mjs`) exactly, including the hard rules: wrapping `MUL`, unsigned `DIVU`/`MODU`/`LTU`, `INT_MIN / -1`, shifts masked to 5 bits, `PUSH8` sign extension, `EXIT`'s low byte, and all ten traps with their own exit codes.
