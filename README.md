# C-Bed

[![Version](https://img.shields.io/badge/version-1.0.1-blue)](https://www.clibs.co.uk/c-bed.html)

**C-Bed** is a unit testing and mocking framework designed specifically for C programming — providing isolated tests, dependency mocking, and automatic memory-issue detection with minimal tooling. Developed by **C Libs**, it allows you to write fast, reliable unit tests for C code without external dependencies.

## Overview

Testing C code properly can be a challenge — dependencies, side-effects, memory issues and lack of isolation all contribute to fragile tests. C-Bed gives you the tools to perform true unit testing and mocking:

- A lightweight header + static library.  
- Mocking support so you can isolate functions from their dependencies.  
- Automatic memory leak and corruption detection during tests.  
- Easy integration: include the header, link the library, write tests.  
- Online documentation: [https://www.clibs.co.uk/doc/c-bed/index.html](https://www.clibs.co.uk/doc/c-bed/index.html)  
- Product page: [https://www.clibs.co.uk/c-bed.html](https://www.clibs.co.uk/c-bed.html)

## Features

- Unit testing support (TDD or retroactive)  
- Mocking framework for function isolation  
- Memory-leak and memory-corruption detection built into tests  
- Assertion macros (e.g., `ASSERT_EQ`, `ASSERT_TRUE`, `ASSERT_NULL`)  
- Setup/teardown support for test suites  
- Header + static library, minimal dependencies

## Installation

1. Download the latest release from the [C-Bed product page](https://www.clibs.co.uk/c-bed.html).  
2. Extract and build according to the documentation.  
3. Include in your test project:

   ```c
   #include <c-bed/c-bed.h>
   ```
4. Link your test runner executable with `libc-bed.a`:

   ```sh
   gcc -o my_tests my_tests.c -L/path/to/c-bed/lib -lc-bed
   ```  
5. See the full reference and examples at [C-Bed Documentation](https://www.clibs.co.uk/doc/c-bed/index.html).

## Example

Minimal test runner example:

```c
#include <c-bed/c-bed.h>
#include "src/mycode.c"

void test_my_function_returns_expected()
{
    ASSERT_EQ(42, my_function("foo"));
}

int main(int argc, char *argv[])
{
    C_BED_TEST tests[] =
    {
        UNIT_TEST(test_my_function_returns_expected)
    };

    return RUN_TESTS(tests);
}
```

See worked examples in the documentation: [https://www.clibs.co.uk/doc/c-bed/c-bed/example.html](https://www.clibs.co.uk/doc/c-bed/c-bed/example.html)

## License

**Free for personal use.**  
Commercial licenses are available — please contact **sales@clibs.co.uk** for details.  
Full license terms on the [product page](https://www.clibs.co.uk/c-bed.html).

## Contributing

C-Bed is maintained and distributed by **C Libs**.  
For feature requests, issue reports, or licensing discussions please contact: **sales@clibs.co.uk**

## Acknowledgements

© 2022–2025 **C Libs** — All rights reserved.  
[https://www.clibs.co.uk](https://www.clibs.co.uk)
