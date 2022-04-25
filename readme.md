# Oden development

## Pre reqs

1. install rust (https://rustup.rs/)
2. brew install llvm
3. in .zshrc: export PATH=$(brew --prefix llvm)/bin:$PATH
4. rustup target add your-arch-here

## Developing

1. Clone down the following into a folder

- swc
- dprint-swc-ecma-ast-view
- oden_lint
- oden_doc
- oden_ast
- oden

2. cd swc && comment out binding_core_wasm
3. cd oden && cargo update
4. fix any dep issues
5. cargo build
6. cargo run

## Deploying

1. bump the version in oden
2. build the binaries

- cargo build -r --target aarch64-apple-darwin
- cargo build -r --target x86_64-apple-darwin
- cargo build -r --target x86_64-pc-windows-msvc
- cargo build -r --target x86_64-unknown-linux-gnu

3. zip each `oden` as `oden-[arch].zip`
4. create a new release in github with those zips: https://github.com/dalscript/oden-alphas/releases
