# coq-to-ocaml-to-js [![Main workflow](https://github.com/imbsky/coq-to-ocaml-to-js/workflows/Main%20workflow/badge.svg)](https://github.com/imbsky/coq-to-ocaml-to-js/actions)

This repository is nothing more than a proof of concept using Coq's Extraction,
BuckleScript, Rollup, Terser, and Closure Compiler to generate safe and fast
JavaScript. and I'm not used to Coq at all, so don't hesitate to send PR if you
can write better example code!

## Prerequirements

- Make sure you have the required dependencies installed:
  - `Node.js`: 13.0.1
  - `yarn`: 1.19.1
  - `esy`: 0.5.8

## Overview

```
Coq Code
  |
  | (Use Coq Compiler)
  v
OCaml Code
  |
  | (Use BuckleScript)
  v
Optimized JavaScript Code
  |
  | (Use Rollup, Terser, Closure Compiler)
  v
More Optimized JavaScript Code
```

```
.
├── coq
│   └── sigma.v
├── javascript
│   └── sigma.js
├── lib
│   └── es6
│       └── ocaml
│           └── sigma.js
└── ocaml
    ├── sigma.ml
    └── sigma.mli
```

## Build Instructions

```bash
# Install Node.js packages
yarn

# Install and build OCaml packages
esy

# Cleanup
yarn clean

# Extract to OCaml
cd ocaml && esy coqc ../coq/*.v && cd -

# Compile OCaml to JavaScript
yarn build
```
