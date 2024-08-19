# Defines
`typedef` `define`

```
Quasar/src/Core/Defines.h
```

??? note "Author"
    [Rounak Paul](mailto:paulrounak1999@gmail.com)
    
    Dated: 19th March 2024

## Types

!!! warning "Important"
    Use the following defined types in Quasar Engine to avoid varying size of types from compiler to compiler. The following have been static asserted to have the expected size. This size is very important to avoid unknown behavours in varipus modules like Renderer or Event system. 

!!! note "Unsigned int types"

    | Quasar symbol     |  typedef                      |
    |-------------------|-------------------------------|
    | u8                | unsigned char                 |
    | u16               | unsigned short                |
    | u32               | unsigned int                  |
    | u64               | unsigned long long            |

!!! note "Signed int types"

    | Quasar symbol     |  typedef                      |
    |-------------------|-------------------------------|
    | i8                | signed char                   |
    | i16               | signed short                  |
    | i32               | signed int                    |
    | i64               | signed long long              |

!!! note "Floating point types"

    | Quasar symbol     |  typedef                      |
    |-------------------|-------------------------------|
    | f32               | float                         |
    | f64               | double                        |

!!! note "Boolean types"

    | Quasar symbol     |  typedef                      |
    |-------------------|-------------------------------|
    | b32               | int                           |
    | b8                | bool                          |

## Defines

```cpp
#define TRUE true
```

```cpp
#define FALSE false
```

```cpp
#define INVALID_ID_U64 18446744073709551615UL
```

```cpp
#define INVALID_ID 4294967295U
```

```cpp
#define INVALID_ID_U16 65535U
```

```cpp
#define INVALID_ID_U8 255U
```

!!! info "Windows"
    ```cpp
    // API export
    #define QS_API __declspec(dllexport)

    // API import
    #define QS_API __declspec(dllimport)
    ```

!!! info "Mac & Linux"
    ```cpp
    // API export
    #define QS_API __attribute__((visibility("default")))

    // API import
    #define QS_API
    ```

```cpp
// Clamp
#define QS_CLAMP(value, min, max) ((value <= min) ? min : (value >= max) ? max : value)
```

```cpp
// Min
#define QS_MIN(x, y) (x < y ? x : y)
```

```cpp
// Max
#define QS_MAX(x, y) (x > y ? x : y)
```

```cpp
#define GIBIBYTES(amount) (amount * 1024 * 1024 * 1024)
```

```cpp
#define MEBIBYTES(amount) (amount * 1024 * 1024)
```

```cpp
#define KIBIBYTES(amount) (amount * 1024)
```

```cpp
#define GIGABYTES(amount) (amount * 1000 * 1000 * 1000)
```

```cpp
#define MEGABYTES(amount) (amount * 1000 * 1000)
```

```cpp
#define KILOBYTES(amount) (amount * 1000)
```

```cpp
QS_INLINE u64 get_aligned(u64 operand, u64 granularity) {
    return ((operand + (granularity - 1)) & ~(granularity - 1));
}
```

```cpp
QS_INLINE range get_aligned_range(u64 offset, u64 size, u64 granularity) {
    return range{get_aligned(offset, granularity), get_aligned(size, granularity)};
}
```