# Rust hooks for pre-commit

[pre-commit](https://pre-commit.com) hooks for [Rust](https://www.rust-lang.org) tools.

## Using Rust tools with pre-commit

```yaml
- repo: https://github.com/berquist/pre-commit-rust
  rev: main
  hooks:
    - id: cargo-fmt
    - id: cargo-check
    - id: cargo-clippy
    - id: cargo-test
```

## Passing arguments to rustfmt

```yaml
- repo: https://github.com/berquist/pre-commit-rust
  rev: main
  hooks:
    - id: cargo-fmt
      args: ['--verbose', '--', '--edition', '2018' ]
```

Note: `cargo fmt` picks up "edition" automatically from `Cargo.toml`, so specifying this isn't necessary in most cases.
