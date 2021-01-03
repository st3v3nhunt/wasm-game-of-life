# wasm-game-of-life

> Run through of the tutorial in the
> [Rust and WebAssembly book](https://rustwasm.github.io/docs/book/introduction.html)

## 🚴 Usage

### 🛠️ Build with `wasm-pack build`

```
wasm-pack build
```

### Run locally via [webpack](https://webpack.js.org/) with `npm run start`

```
cd www && npm run start
```

### Run bench marks

Using [`cargo benchcmp`](https://github.com/BurntSushi/cargo-benchcmp) and the
nightly compiler as per the instructions within the
[making time run faster](https://rustwasm.github.io/docs/book/game-of-life/time-profiling.html#making-time-run-faster)
section.

Install the nightly compiler `rustup toolchain install nightly`. More info at
[installing nightly](https://rust-lang.github.io/rustup/installation/index.html#installing-nightly).

Note the need to remove references to `wasm_bindgen` from `src/lib.rs`.

```
rustup run nightly cargo bench | tee run-results.txt
```

### 🔬 Test in Headless Browsers with `wasm-pack test`

```
wasm-pack test --headless --firefox
```

### 🎁 Publish to NPM with `wasm-pack publish`

```
wasm-pack publish
```

## 🔋 Batteries Included

* [`wasm-bindgen`](https://github.com/rustwasm/wasm-bindgen) for communicating
  between WebAssembly and JavaScript.
* [`console_error_panic_hook`](https://github.com/rustwasm/console_error_panic_hook)
  for logging panic messages to the developer console.
* [`wee_alloc`](https://github.com/rustwasm/wee_alloc), an allocator optimized
  for small code size.
