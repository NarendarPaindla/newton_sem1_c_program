Here's a reference table for standard C data types (typical sizes on a 64-bit system, e.g., GCC/Linux — sizes can vary by compiler/platform):

## Integer Types

| Data Type | Size (bytes) | Size (bits) | Range in Powers of 2 | Range (Values) |
|---|---|---|---|---|
| `char` (signed) | 1 | 8 | −2⁷ to 2⁷−1 | −128 to 127 |
| `unsigned char` | 1 | 8 | 0 to 2⁸−1 | 0 to 255 |
| `short int` (signed) | 2 | 16 | −2¹⁵ to 2¹⁵−1 | −32,768 to 32,767 |
| `unsigned short int` | 2 | 16 | 0 to 2¹⁶−1 | 0 to 65,535 |
| `int` (signed) | 4 | 32 | −2³¹ to 2³¹−1 | −2,147,483,648 to 2,147,483,647 |
| `unsigned int` | 4 | 32 | 0 to 2³²−1 | 0 to 4,294,967,295 |
| `long int` (signed) | 8 | 64 | −2⁶³ to 2⁶³−1 | −9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `unsigned long int` | 8 | 64 | 0 to 2⁶⁴−1 | 0 to 18,446,744,073,709,551,615 |
| `long long int` (signed) | 8 | 64 | −2⁶³ to 2⁶³−1 | −9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `unsigned long long int` | 8 | 64 | 0 to 2⁶⁴−1 | 0 to 18,446,744,073,709,551,615 |

## Floating Point Types

| Data Type | Size (bytes) | Size (bits) | Precision | Approx. Range |
|---|---|---|---|---|
| `float` | 4 | 32 | ~6–7 decimal digits | ±3.4 × 10³⁸ (min positive: ~1.2 × 10⁻³⁸) |
| `double` | 8 | 64 | ~15–16 decimal digits | ±1.7 × 10³⁰⁸ (min positive: ~2.2 × 10⁻³⁰⁸) |
| `long double` | 12 or 16 (platform dependent) | 96/128 | ~18–19 decimal digits | ±1.1 × 10⁴⁹³² (varies by platform) |

## Other Types

| Data Type | Size (bytes) | Notes |
|---|---|---|
| `_Bool` / `bool` (C99+) | 1 | 0 or 1 |
| `void` | — | No size (incomplete type) |
| pointer (e.g. `int*`) | 8 (on 64-bit), 4 (on 32-bit) | Depends on architecture, not data type |

### Key formula for signed integer ranges (n = number of bits):
```
Minimum = -2^(n-1)
Maximum =  2^(n-1) - 1
```

### Key formula for unsigned integer ranges:
```
Minimum = 0
Maximum = 2^n - 1
```

**Note:** Exact sizes of `int`, `long`, etc. are *not fixed by the C standard* — they're compiler/platform dependent (this table reflects the common **LP64** model used on 64-bit Linux/macOS with GCC/Clang). On Windows (LLP64), `long` is typically 4 bytes instead of 8. For guaranteed-size integers, use `<stdint.h>` types like `int8_t`, `uint16_t`, `int32_t`, `int64_t`, etc.

Want me to include the `<stdint.h>` fixed-width types table too, or show how to verify these sizes using `sizeof()` and `limits.h` on your own system?
