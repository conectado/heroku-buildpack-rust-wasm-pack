# Heroku buildpack for Rust and wasm-pack

This is a Heroku buildpack for Rust and wasm-pack with support for [cargo][] and [rustup][].  Features include:

- Caching of builds between deployments.
- Automatic updates to the latest stable Rust by default.
- Support for `export` so that other buildpacks can access the Rust toolchain.
- Support for compiling Rust-based extensions for projects written in other languages.

[cargo]: http://crates.io/
[rustup]: https://www.rustup.rs/

## Using this buildpack

To deploy an application to Heroku, we recommend installing the [Heroku CLI][].

If you're creating a new Heroku application, `cd` to the directory containing your code, and run:

```sh
heroku create --buildpack https://github.com/conectado/heroku-buildpack-rust-wasm-pack.git
```

This will only work if your application has a `Cargo.toml` and uses `git`. If you want to set a particular name for application, see `heroku create --help` first.

To use this as the buildpack for an existing application, run:

```sh
heroku buildpacks:add --index 1 https://github.com/conectado/heroku-buildpack-rust-wasm-pack.git
```
