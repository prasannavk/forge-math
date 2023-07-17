# forge-math 
forge-math contains implementations in C++ for 3d math inspired by code https://gamemath.com/. Some parts of the code
are modernized as the original code is C++99.

## Contents

This example project contains the `geom` library,
an application `geom_app` which uses this library,
and a test-suite which tests the library.

Any pull-requests or commits to the repository trigger GitHub Actions,
which will compile the code and run the tests.

Project structure:

- [src](src)
  - the `geom` library source code
  - this is where the meat of the project is: the implementation
- [include/geom](include/geom)
  - the `geom` library headers
  - the public interface of the library
- [app](app)
  - the application which uses the `geom` library
- [tests](tests)
  - the test code
  - each `x.cpp` file has a corresponding `x_t.cpp` file here with tests
- [ext](ext)
  - external libraries, e.g. Catch2 testing framework
- [.github/workflows/ci.yml](.github/workflows/ci.yml)
  - the GitHub Actions configuration

## Compiling

To compile the project and run the tests:

```
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make
make test
```

## Documentation

If you have Doxygen installed you can also build the documentation by enabling the `BUILD_DOCS` CMake option, and then running `make doxygen`:

```
cmake .. -DCMAKE_BUILD_TYPE=Release -DBUILD_DOCS=ON
make doxygen
```

This will generate the documentation in the `html` folder.