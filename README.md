**Docker images for [cross-rs/cross](https://github.com/cross-rs/cross), including clang12.**

The images are based on [cross-rs/cross Docker images](https://github.com/orgs/cross-rs/packages?repo_name=cross),
but replacing the default clang (3.8 or 6 depending the image) with clang 12. This is useful for instance for [bindgen](https://rust-lang.github.io/rust-bindgen/requirements.html) which requires clang 5 or greater.  
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

[target.aarch64-unknown-linux-musl]
image = "jenoch/rust-cross:aarch64-unknown-linux-musl"
```

**NOTE:** If using `bindgen` you get some `"fatal error: 'xyz.h' file not found"` error, try with `bindgen="0.60"`.