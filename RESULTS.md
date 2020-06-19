# C++ designated initializers
Looks like designated initializers support for C++ depends on platform, C++ dialect and compiler version.

## Windows 10
- Building for: Visual Studio 16 2019
- The C compiler identification is MSVC 19.26.28806.0

**C++11**
> set (CMAKE_CXX_STANDARD 11)
```
..\src\main.cpp(6): error C7555: use of designated initializers requires at least '/std:c++latest'
..\src\main.cpp(6): error C4576: a parenthesized type followed by an initializer list is a non-standard explicit type conversion syntax
```

_**Note:** even set to C++20 MSVC seems to not fully support it._
> set (CMAKE_CXX_STANDARD 20)
```
..\src\main.cpp(6): error C4576: a parenthesized type followed by an initializer list is a non-standard explicit type conversion syntax
```
---
MinGW
- The C compiler identification is GNU 8.1.0
- The CXX compiler identification is GNU 8.1.0

_**gcc 8+** support C+2a features_
```
succeeds
```

---
## Ubuntu 18.04
- The C compiler identification is GNU 7.5.0
- The CXX compiler identification is GNU 7.5.0

_**Note:** GNU 7.5.0 only supports up to C++17_
> set (CMAKE_CXX_STANDARD 17)
```
src/main.cpp: In function ‘int main(int, const char**)’:
gravity/src/shared/gravity_macros.h:46:97: sorry, unimplemented: non-trivial designated initializers not supported
 #define VALUE_FROM_NULL                     ((gravity_value_t){.isa = gravity_class_null, .n = 0})
                                                                                                 ^
src/main.cpp:6:29: note: in expansion of macro ‘VALUE_FROM_NULL’
     gravity_value_t value = VALUE_FROM_NULL;
                             ^~~~~~~~~~~~~~~
```