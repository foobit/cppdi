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

**C++20**
> set (CMAKE_CXX_STANDARD 20)
```
..\src\main.cpp(6): error C4576: a parenthesized type followed by an initializer list is a non-standard explicit type conversion syntax
```
---
MinGW
- The C compiler identification is GNU 8.1.0
- The CXX compiler identification is GNU 8.1.0

```
succeeds
```

---
## Ubuntu 18.04
- The C compiler identification is GNU 7.5.0
- The CXX compiler identification is GNU 7.5.0
```
```