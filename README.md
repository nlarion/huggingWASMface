## A Rust program that will compile (some) parts of huggingface's tokenizer into WASM exposed by the method "ight"
default vocab and merges taken from gpt2. those are then pasted into the lib.rs as static vars, because WASM doesn’t support std::file... this could be rectified by loading them in js and passing the files to WASM, then rust could then use the files, but... seems more trouble than it's worth (to me).

## this is probably a dumb idea and will make me rewrite the tokenizer in JS ¯&#92;&#95;(ツ)&#95;/¯

## Build:
```console
wasm-pack build --target web
```
for plugin.
wasm-pack build --release --target no-modules 
## TL;DR: you can get tokens from huggingface's tokenizer in WASM
