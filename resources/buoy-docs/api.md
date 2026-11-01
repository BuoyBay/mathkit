---
title: "MathKit scalar numerics"
summary: "Checked integers and stable Double helpers, with explicit numerical contracts."
category: "Reference"
order: 1
keywords: ["mathkit", "rounding", "integer", "numerical"]
related: ["index.md", "getting-started.md", "typed-api.md"]
---

# MathKit 0.1.0

Import `mathkit`; all operations are `Numeric` Shared functions. Pure Buoy,
no FFI or package dependencies. Integer operations use signed 64-bit values.

## Contracts

- `Epsilon()`, `MaxValue()`, `MinNormal()`, `MinSubnormal()`, `Tau()` return
  binary64 constants (epsilon is the gap above one).
- `IsNaN`, `IsFinite`, `IsInfinity`, `IsInteger`, `IsSafeInteger` classify
  Doubles. Safe integers have magnitude at most 2^53-1. `IsNegativeZero`
  detects zero's sign using its reciprocal. `CopySign` copies a non-NaN
  sign, including negative zero; a NaN sign throws. NaN payloads are unspecified.
- `IsClose(a,b,relativeTolerance=1e-9,absoluteTolerance=0)` uses
  |a-b| <= max(absTol, relTol*max(|a|,|b|)), evaluated with scaling to avoid
  overflow. Tolerances must be finite and nonnegative. Equal infinities are
  close; NaNs and unequal infinities are not. Boundary comparisons remain
  subject to floating-point rounding.
- `Clamp` allows infinite bounds, propagates a NaN input, and rejects NaN or
  reversed bounds. `ClampInteger` rejects reversed bounds.
- `Lerp(a,b,t)` and `InverseLerp(a,b,x)` require finite inputs. Lerp preserves
  endpoints and avoids overflow for interpolation t in [0,1]; extrapolation
  can overflow. InverseLerp rejects equal endpoints and scales overflowing
  differences; ill-conditioned differences can lose precision. `Degrees`
  and `Radians` convert angles without reducing them.
- `Truncate`, `RoundEven`, `RoundAwayFromZero` return Double integer values;
  the latter means nearest with half ties away from zero. Nonfinite values
  propagate. Signed zero is preserved.
- `RoundDigits(x,digits,mode=ToEven)` explicitly computes binary64
  `scale=pow(10,digits)`, `rounded=round(x*scale)`, then `rounded/scale`.
  This is NOT exact decimal rounding of the original binary value. For nonnegative
  digits, values already beyond the scaled integer-precision threshold are returned
  unchanged, avoiding needless overflow and loss of low integer bits. Digits
  must be -308..308; finite scaled overflow throws. Scaling can underflow,
  the scale is approximate, and unscaling can overflow. Modes: `ToEven`,
  `AwayFromZero` (nearest, half ties away), `TowardZero`,
  `TowardNegativeInfinity`, `TowardPositiveInfinity`.
- `CheckedAdd`, `CheckedSubtract`, `CheckedMultiply`, `CheckedNegate`,
  `CheckedAbs`, `CheckedPower` check before every potentially overflowing
  operation. Power requires a nonnegative exponent; 0^0 is 1.
- `Gcd` returns a nonnegative gcd, with gcd(0,0)=0. An unrepresentable
  positive 2^63 throws. `Lcm` returns nonnegative lcm, zero if either input
  is zero. `IntegerSqrt` returns floor(sqrt(n)) exactly for nonnegative n.
  `Factorial` accepts 0..20. `Binomial(n,k)` requires 0<=k<=n and cancels
  denominators before multiplication, accepting every representable result.
- `FloorDiv` rounds the quotient toward negative infinity; zero divisor and
  MinValue/-1 throw. `EuclideanMod` returns 0<=r<|divisor|, including a
  MinValue divisor. It is distinct from signed floor-division remainder.
- `Hypot`/`Hypot3` scale before squaring; infinity wins over NaN.
  `Log1p` preserves tiny x and requires x>=-1; -1 returns -infinity.
  `Expm1` uses a series near zero. `Cbrt` uses a logarithmic seed and Newton
  refinement. `Exp2` combines a fractional exponential with exact binary scaling, avoiding
  an optimizer-generated exp2 import missing from the installed link stubs. `Asinh`, `Acosh` (x>=1),
  `Atanh` (|x|<=1, signed infinities at endpoints) use stable identities.
  These helpers propagate NaN and preserve signed zero when mathematically
  applicable. Overflow/underflow follow binary64 arithmetic.
- `LogAddExp` and `LogSumExp` use maximum shifting; NaN wins over infinity.
  Empty/all-negative-infinity LogSumExp returns negative infinity. Summation
  uses compensation and Log1p after omitting one maximum term, preserving
  small corrections such as LogSumExp([0,-40]); it is not exact or guaranteed
  reproducible across all platforms.
- `Linspace(a,b,count)` requires finite endpoints and nonnegative count;
  0 gives empty, 1 gives [a], otherwise includes both endpoints. Allocation
  is caller-budgeted. `Horner(coefficients,x)` takes highest-degree first;
  empty yields zero. Arithmetic is ordinary multiply/add, not fused.

Invalid domains throw `InvalidArgumentException`; unrepresentable checked integer results
and scaled-rounding overflow throw `OverflowException`. Integer zero divisors throw
`DivideByZeroException`.
No Fma is supplied. No correctly-rounded, universal ulp bound, mathematical
conformance, or non-Linux runtime guarantee is claimed. Native Math functions
and compiler floating-point behavior remain dependencies. See the verifier's
retained JSON for measured errors against high-precision Python Decimal
oracles and the exact coverage of six-target semantic checks.

## Use and verification

Maintainers run the private validation suite before release. See the repository README for public build instructions.

## Observed validation

The Linux x86-64 corpus covers 1,909 integer cases, 474 real cases, 100
closeness comparisons, 11 real-domain rejection cases and standalone boundary
assertions. Against 800-digit Decimal references rounded to binary64, maximum
observed errors were 3 ulps for Expm1, 1 ulp for Log1p/Cbrt/Asinh/Atanh/Acosh/
Hypot/Exp2/LogAddExp, and 0 ulps for the sampled Hypot3/LogSumExp/rounding
cases. These finite-sample observations are not general error bounds.
Independent review and non-Linux native execution are not included here.


A separate independent review corpus observed up to 4 ulps for Expm1, 2 for several scaled helpers, and 7 for a cancellation-sensitive LogSumExp case. Those measurements are corpus-specific, not uniform accuracy bounds. The local review corrections use endpoint-oriented interpolation for same-sign values near t=1 and a pure-Buoy Exp2 path tested at -O0/-O2.
