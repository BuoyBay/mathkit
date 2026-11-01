---
title: "mathkit typed API"
summary: "Source-derived public signatures, properties, parameters, defaults, and return values."
category: "Reference"
order: 21
types: ["Numeric", "RoundingMode"]
dependencies: []
symbols: ["Numeric", "RoundingMode"]
related: ["api.md", "getting-started.md", "index.md"]
---

# mathkit typed API

Generated from the package source declarations. Platform guards are shown where present; inherited members are documented on the base type. See the [API contracts](api.md) for behavior and limitations.

## RoundingMode

`Public Enum RoundingMode As Integer`

### Values

| Name | Type | Value / Default | Description |
| --- | --- | --- | --- |
| `ToEven` | `RoundingMode` | — | — |
| `AwayFromZero` | `RoundingMode` | — | — |
| `TowardZero` | `RoundingMode` | — | — |
| `TowardNegativeInfinity` | `RoundingMode` | — | — |
| `TowardPositiveInfinity` | `RoundingMode` | — | — |

## Numeric

`Public Class Numeric`

Scalar numerical helpers. Invalid domains throw InvalidArgumentException; checked integer overflow and scaled-rounding overflow throw OverflowException; integer zero divisors throw DivideByZeroException.

### Epsilon

`Public Shared Function Epsilon() As Double`

No parameters.

#### Returns

| Type |
| --- |
| `Double` |

### MaxValue

`Public Shared Function MaxValue() As Double`

No parameters.

#### Returns

| Type |
| --- |
| `Double` |

### MinNormal

`Public Shared Function MinNormal() As Double`

No parameters.

#### Returns

| Type |
| --- |
| `Double` |

### MinSubnormal

`Public Shared Function MinSubnormal() As Double`

No parameters.

#### Returns

| Type |
| --- |
| `Double` |

### Tau

`Public Shared Function Tau() As Double`

No parameters.

#### Returns

| Type |
| --- |
| `Double` |

### IsNaN

`Public Shared Function IsNaN(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### IsFinite

`Public Shared Function IsFinite(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### IsInfinity

`Public Shared Function IsInfinity(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### IsInteger

`Public Shared Function IsInteger(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### IsSafeInteger

`Public Shared Function IsSafeInteger(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### IsNegativeZero

`Public Shared Function IsNegativeZero(x As Double) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Boolean` |

### CopySign

`Public Shared Function CopySign(magnitude As Double, sign As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `magnitude` | `Double` | `ByVal` | Required |
| `sign` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### IsClose

`Public Shared Function IsClose(a As Double, b As Double, relativeTolerance As Double = 1.0e-9, absoluteTolerance As Double = 0.0) As Boolean`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |
| `relativeTolerance` | `Double` | `ByVal` | `1.0e-9` |
| `absoluteTolerance` | `Double` | `ByVal` | `0.0` |

#### Returns

| Type |
| --- |
| `Boolean` |

### Clamp

`Public Shared Function Clamp(x As Double, lo As Double, hi As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |
| `lo` | `Double` | `ByVal` | Required |
| `hi` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### ClampInteger

`Public Shared Function ClampInteger(x As Integer, lo As Integer, hi As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Integer` | `ByVal` | Required |
| `lo` | `Integer` | `ByVal` | Required |
| `hi` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Lerp

`Public Shared Function Lerp(a As Double, b As Double, t As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |
| `t` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### InverseLerp

`Public Shared Function InverseLerp(a As Double, b As Double, x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Degrees

`Public Shared Function Degrees(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Radians

`Public Shared Function Radians(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Truncate

`Public Shared Function Truncate(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### RoundEven

`Public Shared Function RoundEven(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### RoundAwayFromZero

`Public Shared Function RoundAwayFromZero(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### RoundDigits

`Public Shared Function RoundDigits(x As Double, digits As Integer, mode As RoundingMode = RoundingMode.ToEven) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |
| `digits` | `Integer` | `ByVal` | Required |
| `mode` | `RoundingMode` | `ByVal` | `RoundingMode.ToEven` |

#### Returns

| Type |
| --- |
| `Double` |

### CheckedAdd

`Public Shared Function CheckedAdd(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### CheckedSubtract

`Public Shared Function CheckedSubtract(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### CheckedNegate

`Public Shared Function CheckedNegate(a As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### CheckedAbs

`Public Shared Function CheckedAbs(a As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### CheckedMultiply

`Public Shared Function CheckedMultiply(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### CheckedPower

`Public Shared Function CheckedPower(a As Integer, exponent As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `exponent` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Gcd

`Public Shared Function Gcd(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Lcm

`Public Shared Function Lcm(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### IntegerSqrt

`Public Shared Function IntegerSqrt(n As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `n` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Factorial

`Public Shared Function Factorial(n As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `n` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Binomial

`Public Shared Function Binomial(n As Integer, k As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `n` | `Integer` | `ByVal` | Required |
| `k` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### FloorDiv

`Public Shared Function FloorDiv(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### EuclideanMod

`Public Shared Function EuclideanMod(a As Integer, b As Integer) As Integer`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Integer` | `ByVal` | Required |
| `b` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Integer` |

### Hypot

`Public Shared Function Hypot(a As Double, b As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Hypot3

`Public Shared Function Hypot3(a As Double, b As Double, c As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |
| `c` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Log1p

`Public Shared Function Log1p(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Expm1

`Public Shared Function Expm1(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Cbrt

`Public Shared Function Cbrt(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Exp2

`Public Shared Function Exp2(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Asinh

`Public Shared Function Asinh(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Acosh

`Public Shared Function Acosh(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Atanh

`Public Shared Function Atanh(x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### LogAddExp

`Public Shared Function LogAddExp(a As Double, b As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### LogSumExp

`Public Shared Function LogSumExp(values As Array Of Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `values` | `Array Of Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |

### Linspace

`Public Shared Function Linspace(a As Double, b As Double, count As Integer) As Array Of Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `a` | `Double` | `ByVal` | Required |
| `b` | `Double` | `ByVal` | Required |
| `count` | `Integer` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Array Of Double` |

### Horner

`Public Shared Function Horner(coefficients As Array Of Double, x As Double) As Double`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `coefficients` | `Array Of Double` | `ByVal` | Required |
| `x` | `Double` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Double` |
