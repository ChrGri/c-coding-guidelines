# C Coding Guidelines & AI Agent Instructions

## 1. General Instructions
- **Target Language:** C.
- Treat these rules as your highest priority when generating, modifying, or refactoring code.

## 2. Restricted Data Types
- **NO Double Precision:** The use of double-precision floating-point variables (e.g., `double`, `float64`) is strictly forbidden. Always use single-precision (e.g., `float`, `float32`) instead.

## 3. Code Formatting (Allman Style)
- Strictly use the **Allman style** for all code formatting.
- Opening and closing curly braces `{ }` MUST **always be placed on a new line** and share the same indentation level as their associated control statement (e.g., function declaration, `if`, `for`, `while`).

**Correct Example:**
```c
void myExampleFunction()
{
    if (condition)
    {
        // Code goes here
    }
}
```

## 4. General Naming Conventions
- **Functions:** Use `camelCase` (e.g., `calculateValue`, `initHardware`).
- **Variables:** Use `camelCase` for the base name, followed by the mandatory type suffix.
- **Macros & Constants:** Use `UPPER_SNAKE_CASE` for `#define` macros and `enum` values (e.g., `MAX_BUFFER_SIZE`).

## 5. Scope Prefixes
To easily identify the scope of a variable, use the following prefixes before the `camelCase` name:
- **Global variables:** Prefix with `g_` (Example: `uint32 g_systemState_u32;`).
- **File-static variables:** Prefix with `s_` (Example: `uint32 s_localCounter_u32;`).
- **Local variables:** No prefix, just the base name and suffix (Example: `uint32 loopIndex_u32;`).

## 6. Variable Suffixes by Data Type
Every variable MUST have a suffix indicating its exact data type. The suffix is separated from the base variable name by an underscore `_`.

### 6.1 Scalar Base Types
Append the short name of the type to the end of the variable:
- `float32` -> `_fl32` (Example: `float32 tempValue_fl32;`)
- `int32`   -> `_i32`  (Example: `int32 counter_i32;`)
- `uint16`  -> `_u16`  (Example: `uint16 status_u16;`)
- `uint32`  -> `_u32`  (Example: `uint32 config_u32;`)

### 6.2 Boolean Types
For boolean variables (e.g., `bool` from `<stdbool.h>` or custom `boolean` types), use the suffix `_b`:
- `bool` / `boolean` -> `_b` (Example: `bool isReady_b;`, `boolean hasError_b;`)

### 6.3 Pointers
If the variable is a pointer, add the letter `p` immediately after the underscore, before the data type:
- **Pointer to uint32:** `_pu32` (Example: `uint32 *hardwareRegister_pu32;`)
- **Pointer to float32:** `_pfl32` (Example: `float32 *sensorReadings_pfl32;`)
- **Pointer to bool:** `_pb` (Example: `bool *statusFlag_pb;`)

### 6.4 Array Dimensions
If the variable is an array, the number of dimensions MUST be represented by the letter `a` immediately following the underscore (and before the data type or pointer indicator):
- **1 Dimension:** one `a` -> `_a<Type>` 
  (Example: `uint32 myData_au32[10];`)
- **2 Dimensions:** two `a`s -> `_aa<Type>` 
  (Example: `uint32 myMatrix_aau32[5][5];`)
- **3 Dimensions:** three `a`s -> `_aaa<Type>` 
  (Example: `uint32 myTensor_aaau32[3][3][3];`)
- **Array of Pointers:** `a` followed by `p` -> `_ap<Type>`
  (Example: `uint32 *myPointerList_apu32[5];`)
- **Array of Booleans:** `a` followed by `b` -> `_ab`
  (Example: `bool activeStates_ab[8];`)

## 7. Structs, Typedefs, and Enums
- **Struct Names:** Use `PascalCase` for the struct name itself.
- **Typedefs:** Always append `_t` to custom types defined via `typedef`.
- **Struct Members:** Apply the standard variable suffix rules to struct members.

**Correct Example:**
```c
typedef struct SensorData
{
    uint32 timestamp_u32;
    float32 temperature_fl32;
    uint16 rawValues_au16[3];
    bool isValid_b;
} SensorData_t;
```
