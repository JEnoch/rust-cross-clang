**Docker images for [rust-embedded/cross](https://github.com/rust-embedded/cross), including clang12.**

The images are based on [rustembedded/cross](https://hub.docker.com/r/rustembedded/cross) images, 
but adding clang12 and defining `BINDGEN_EXTRA_CLANG_ARGS="--sysroot=...` with cross-compilation toolchain path
(useful for crates using [bindgen](https://github.com/rust-lang/rust-bindgen)).  
They are published as [jenoch/rust-cross](https://hub.docker.com/repository/docker/jenoch/rust-cross).

You can use them defining such `Cross.toml` file:
```toml
[target.x86_64-unknown-linux-musl]
image = "jenoch/rust-cross:x86_64-unknown-linux-musl"

[target.arm-unknown-linux-gnueabi]
image = "jenoch/rust-cross:arm-unknown-linux-gnueabi"

[target.arm-unknown-linux-gnueabihf]
image = "jenoch/rust-cross:arm-unknown-linux-gnueabihf"

[target.armv7-unknown-linux-gnueabihf]
image = "jenoch/rust-cross:armv7-unknown-linux-gnueabihf"

[target.aarch64-unknown-linux-gnu]
image = "jenoch/rust-cross:aarch64-unknown-linux-gnu"
```
