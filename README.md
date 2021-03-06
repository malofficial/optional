# `cl::optional` [![Build Status](https://travis-ci.org/clechasseur/optional.svg?branch=master)](https://travis-ci.org/clechasseur/optional) [![Build status](https://ci.appveyor.com/api/projects/status/iww7x8wpe239rm6x/branch/master?svg=true)](https://ci.appveyor.com/project/clechasseur/optional-le1xi/branch/master) [![Build status](https://ci.appveyor.com/api/projects/status/g3ktx9cqbgrmhrw9/branch/master?svg=true)](https://ci.appveyor.com/project/clechasseur/optional-ax6fo/branch/master) [![Build status](https://ci.appveyor.com/api/projects/status/n3hthqbbo7vefs2e/branch/master?svg=true)](https://ci.appveyor.com/project/clechasseur/optional-yh8gx/branch/master) [![Build status](https://ci.appveyor.com/api/projects/status/ipgnembb9r2p28q6/branch/master?svg=true)](https://ci.appveyor.com/project/clechasseur/optional/branch/master) [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/clechasseur/optional/master/LICENSE)
Implementation of `std::optional` from the C++17 specification, but for C++11 compilers. For API reference, see:
http://en.cppreference.com/w/cpp/utility/optional

## TL;DR
```c++
#include <cl/optional.h>
#include <iostream>
#include <string>

int main()
{
  cl::optional<std::string> o1;
  cl::optional<std::string> o2("Hello, world!");
  
  std::cout << std::boolalpha
            << o1.has_value() << std::endl      // Prints "false"
            << o2.has_value() << std::endl      // Prints "true"
            << o1.value_or("Foo") << std::endl  // Prints "Foo"
            << o2.value_or("Foo") << std::endl; // Prints "Hello, world!"

  return 0;
}
```

## Installing
The library is header-only. Therefore, to add it to your project, simply copy the content of the [`lib`](https://github.com/clechasseur/optional/tree/master/lib) directory to a suitable place in your structure and add that path to your include paths. Look at the `test` projects/makefile for examples.

## Compiler support
`cl::optional` aims to be compatible with C++11 compilers. It has been successfully tested with the following compilers; YMMV.

* Microsoft Visual Studio 2012
* GCC 4.8.4
* Clang 3.4.0

Some advanced features, such as `constexpr` support, `noexcept` support, etc. will only be available if your compiler supports them.

Compilers are auto-detected on a best-effort basis, but if your compiler is not properly detected, you can turn advanced features on and off through specific `#define`s. Look at the beginning of `optional.h` for details.
