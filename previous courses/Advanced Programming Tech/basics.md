## pointers
## memory leaks

### **C++ Value Categories: A Contrast**


| **Category** | **Description**                                                                                             | **Key Traits**                                                                                | **Examples**                     |
| ------------ | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | -------------------------------- |
| **Lvalue**   | Expression referring to a named, addressable object with a persistent memory location.                      | Can appear on the left-hand side of an assignment (`modifiable`), except for `const` lvalues. | `int x = 42; x;`                 |
| **Xvalue**   | An "eXpiring" value that represents a resource that can be reused (e.g., the result of `std::move`).        | Temporary but addressable; eligible for moving.                                               | `std::move(obj);`                |
| **Prvalue**  | A "Pure rvalue" that is a temporary, unnamed object (value or literal) without a persistent memory address. | Cannot be assigned to or modified. Represents temporary results.                              | `42`, `1 + 2`, `i * 3`           |
| **Glvalue**  | "Generalized lvalue"; encompasses both **lvalues** and **xvalues**.                                         | Refers to objects that have an identifiable location in memory.                               | `int x = 5; (x); std::move(x);`  |
| **Rvalue**   | Encompasses **prvalues** and **xvalues**; represents temporary objects or expressions.                      | Can bind to rvalue references (`&&`) but not to lvalue references (`&`).                      | `42`, `i + 1`, `std::move(obj);` |


1. **Lvalue vs. Rvalue**:
    
    - **Lvalue**: Has a name and address, persists beyond the expression.
    - **Rvalue**: Temporary, without a name or address (includes prvalues and xvalues).
2. **Glvalue vs. Rvalue**:
    
    - **Glvalue**: Refers to an object with an address (includes lvalues and xvalues).
    - **Rvalue**: Includes prvalues and xvalues; prvalues are purely temporary.
3. **Xvalue vs. Prvalue**:
    
    - **Xvalue**: Represents a temporary but can still be moved or have an address.
    - **Prvalue**: Purely temporary and cannot have an address.


```cpp
#include <iostream>
#include <utility> // For std::move

int generate() {
    return 42; // Prvalue
}

int main() {
    int x = 10;                 // `x` is an lvalue.
    int& lref = x;              // `lref` is an lvalue reference.
    int&& rref = generate();    // `generate()` returns a prvalue, bound to an rvalue reference.

    std::cout << x << std::endl; // `x` is an lvalue (glvalue).
    std::cout << std::move(x);  // `std::move(x)` is an xvalue (glvalue).

    int y = generate();         // `generate()` is a prvalue.
    int z = x + y;              // `x + y` is a prvalue (temporary result).

    return 0;
}
```
----
