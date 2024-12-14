# Rust

- <https://www.rust-lang.org/>

## Guides

- <https://doc.rust-lang.org/book/>
- <https://doc.rust-lang.org/reference/>
- <https://cheats.rs/>
- <https://google.github.io/comprehensive-rust/>
- <https://github.com/rust-embedded/rust-raspberrypi-OS-tutorials>
- <https://upsuper.github.io/rust-cheatsheet/>
- <https://rust-unofficial.github.io/patterns/>
- <https://teach-rs.tweede.golf/>
- <https://github.com/johnthagen/min-sized-rust>
- <https://doc.rust-lang.org/nightly/nomicon/>
- <https://marabos.nl/atomics/>

## Useful commands

```sh
# install cargo-hack https://github.com/taiki-e/cargo-hack
cargo +stable install cargo-hack --locked

cargo hack check --feature-powerset --all-targets
cargo hack test --feature-powerset --all-targets

cargo doc --lib --no-deps --all-features

cargo clippy --all-targets --all-features -- -D warnings

# timings build
cargo build --timings
```

## Tests

```sh
cargo test --features feat,second
cargo test -- --nocapture
```
