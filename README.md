# Checked integer math

Import `mathkit`; all operations are `Numeric` Shared functions. No FFI
or package dependencies. Integer operations use signed 64-bit values.

## Install

From a Buoy consumer project with BPM installed:

```sh
bpm add mathkit --git https://github.com/BuoyBay/mathkit.git --rev refs/heads/main
```

BPM records the resolved commit in its lockfile. Keep that lockfile with the
consumer project for reproducible installs.

## Example

```basic
Import mathkit
Sub Main()
    Print Numeric.Binomial(66, 33)
    Print Numeric.Hypot(3.0e200, 4.0e200)
    Print Numeric.Log1p(1.0e-16)
    Print Numeric.RoundDigits(2.675, 2, RoundingMode.ToEven)
End Sub
```

## Build from source

With the native `build-packages` driver from [devtools](https://github.com/BuoyBay/devtools)
on your `PATH`, run from this checkout:

```sh
build-packages --root "$PWD" --compile-consumer mathkit
```

The driver checks source targets and compiles an import consumer. See the
[API guide](docs/API.md) for behavior, limits and any host prerequisites.

## Contributing

[Contributing](CONTRIBUTING.md) · [License](LICENSE)
