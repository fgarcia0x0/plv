# plv
 plv (Propositional Logic Validator) is a grammar recognizer using pll library.
 
# Requirements
- [cmake](https://cmake.org/)
- [ninja-build](https://ninja-build.org/)
- A compiler with support c++ 17
- if you build `pll` test coverage, you need to be installed [gtest](https://github.com/google/googletest)

# How to clone and compile
- Clone this repo as: ```git clone --recurse-submodules "https://github.com/fgarcia0x0/plv.git"```
- In terminal, type: ```cd plv && cmake -S . -B build -GNinja -DCMAKE_BUILD_TYPE=Release```
