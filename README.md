# Libft – Custom C Standard Library

Libft is a personal implementation of the C standard library developed as part of the 42 curriculum at 42 Amman. It includes over 50 functions for string manipulation, memory operations, character analysis, and linked list management. The goal of this project is to gain a deep understanding of how standard C functions work by recreating them from scratch and organizing them into a reusable static library.

---

## Purpose

This project provides:
- A hands-on understanding of C fundamentals and memory management
- A reusable static library for use in future 42 projects
- A foundation for writing safe, efficient, and modular C code

---

## Features

### Standard Library Reimplementations
- Recreated over 40 libc functions (e.g., `memcpy`, `strchr`, `strlen`, `isdigit`)
- All functions begin with the `ft_` prefix and follow the same behavior as their standard counterparts

### Additional Utility Functions
- String handling: `ft_split`, `ft_strjoin`, `ft_strtrim`, `ft_substr`
- Number conversion: `ft_itoa`
- Output functions: `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`
- Character mapping and iteration: `ft_strmapi`, `ft_striteri`

### Linked List Module (Bonus)
- Implemented custom `t_list` structure
- Functions for creating, iterating, modifying, and deleting singly linked lists
- Includes `ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`, `ft_lstmap`, and more

### Performance and Reliability
- Zero memory leaks (verified with Valgrind)
- Full edge-case coverage for all functions
- POSIX-compliant and portable across Linux and macOS
- Optimized with static inline helpers and simplified logic paths

---

## Technologies & Standards

### Core Implementation
| Category        | Details                                                                 |
|-----------------|-------------------------------------------------------------------------|
| **Language**    | C89 (ANSI C) - Strict compatibility with legacy systems                |
| **Compiler**    | `cc` with `-Wall -Wextra -Werror` flags for maximum warning detection   |
| **Archiving**   | `ar rcs` for creating optimized static library                         |
| **Debugging**   | Valgrind 3.18+ for memory leak detection and profiling                 |

### Compliance Standards
| Standard       | Requirements                                                                 |
|---------------|-----------------------------------------------------------------------------|
| **Norminette** | 42 School's code style: <br> - No more than 25 lines per function <br> - 5 functions max per file <br> - Mandatory header format |
| **POSIX**     | Fully compatible with IEEE Std 1003.1-2017 specifications                   |
| **Safety**    | All functions handle edge cases: <br> - NULL pointer inputs <br> - Zero-length operations <br> - Invalid ranges |

### Toolchain Verification
```bash
# Example build and verification commands
$ make re && make bonus          # Full rebuild with bonuses
$ valgrind --leak-check=full ./test_program  # Memory check
$ norminette *.c *.h            # Style validation
```
---

## Project Structure

```

libft/
├── Makefile
├── libft.h
├── \*.c (function source files)
├── \*.o (object files after compilation)
├── libft.a (final static library)

````

---

## Build Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/tuqasaeed/libft.git
   cd libft
    ```

2. Compile the library:

   ```bash
   make
   ```

3. Compile with bonus functions:

   ```bash
   make bonus
   ```

4. Clean object files:

   ```bash
   make clean
   ```

5. Clean everything:

   ```bash
   make fclean
   ```

6. Rebuild everything from scratch:

   ```bash
   make re
   ```

---

## Usage Example

To use `libft.a` in your own project:

```c
#include "libft.h"

int main(void)
{
    char *s = ft_strdup("Hello, 42!");
    ft_putendl_fd(s, 1);
    free(s);
    return 0;
}
```

Compile your project with:

```bash
cc main.c -L. -lft
```

---


## License

This repository is part of the 42 curriculum and intended for educational use. Reuse or distribution outside of 42's policy is discouraged unless properly credited.

