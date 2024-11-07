# Rust hooks for pre-commit

[pre-commit](https://pre-commit.com) hooks for [Rust](https://www.rust-lang.org) tools.

## Usage

First, install the pre-commit Python package.

Second, create a `.pre-commit-config.yaml` file in the top level of your Git-based project with the following content:

```yaml
- repo: https://github.com/berquist/pre-commit-rust
  rev: main
  hooks:
    - id: cargo-fmt
    - id: cargo-check
    - id: cargo-clippy
    - id: cargo-test
```

Finally, install the pre-commit hook locally and run it for the first time:

```bash
pre-commit install
pre-commit run -a
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
