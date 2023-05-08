# Danogo Bonds Exchange

## Prerequisites

For now you'll need:
- rust installed, see [rustup](https://rustup.rs).

Run command:
```
cargo install aiken --version 1.0.3-alpha --root ./
or
cargo install --git https://github.com/aiken-lang/aiken.git --root ./
```
If not install direnv pls run command:
```
export PATH=$PWD/bin:$PATH
```

## Implement Cardano Smart Contract with Aiken

Write validators in the `validators` folder, and supporting functions in the `lib` folder using `.ak` as a file extension.

For example, as `validators/always_true.ak`

```gleam
pub fn spend(_datum: Data, _redeemer: Data, _context: Data) -> Bool {
  True
}
```

Validators are named after their purpose, so one of:

- `spent`
- `mint`
- `withdraw`
- `publish`

## Building

```sh
aiken build
```

## Testing

You can write tests in any module using the `test` keyword. For example:

```gleam
test foo() {
  1 + 1 == 2
}
```

To run all tests, simply do:

```sh
aiken check
```

To run only tests matching the string `foo`, do:

```sh
aiken check -m foo
```

## Documentation

If you're writing a library, you might want to generate an HTML documentation for it.

Use:

```sh
aiken docs
```

## Resources

Find more on the [Aiken's user manual](https://aiken-lang.org).

## Licensing

The primary license for Danogo V1 Core is the Business Source License 1.1 (`BUSL-1.1`), see [`LICENSE`](./LICENSE).