---
title: "MathKit scalar numerics"
summary: "Checked integers and stable Double helpers, with explicit numerical contracts."
category: "Reference"
order: 1
keywords: ["mathkit", "rounding", "integer", "numerical"]
related: ["index.md", "getting-started.md", "typed-api.md"]
---

# Install and use

Copy `mathkit-0.1.0.buipkg` into the consumer `packages/` directory.
Use `Import mathkit` and call `Numeric.CheckedAdd`, `Numeric.Hypot` or
other Shared functions. See the standalone `examples/mathkit/main.bui`.

Invalid domains throw `InvalidArgumentException`; checked integer overflow and
scaled-rounding overflow throw `OverflowException`; integer zero divisors throw
`DivideByZeroException`.
Read [contracts](api.md) before using decimal rounding or extrapolation.


Save the following as `main.bui` in your consumer project. Package archives and any dependencies must be installed as described above.

```buoy
Import mathkit
Sub Main()
    Print Numeric.Binomial(66, 33)
    Print Numeric.Hypot(3.0e200, 4.0e200)
    Print Numeric.Log1p(1.0e-16)
    Print Numeric.RoundDigits(2.675, 2, RoundingMode.ToEven)
End Sub
```
