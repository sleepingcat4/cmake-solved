Linking third-party libraries is a difficult task in C++ programming. Because third-party libraries after installation are not automatically included in the core language. It needs to be linked. 

A definite way: Link third-party library using file-path **(.h)** is definitely the easiest way. Unfortunately it has obvious development and production drawbacks, while it comes to cross-platform development and understanding (.exe) are different from raw code files being translated to machine code and executed. 

That’s where CMake comes into the scenario. It’s an extremely important tool in C++ programming and makes linking libraries a breeze.

Unfortunately, there’s no reliable tutorial/guidelines to use it. Everyone has their own solutions, some might use extensions on VS code and others Visual Studio solutions and in-built features. Regardless of the preference, it is a knowledge everyone knows but nobody shares. I personally realised this problem while being stuck. That’s why I am making this tutorial. 

## CMake Link

Write a file **(CMakeLists.txt)**

#### Modifications
1. Change file-paths relative to your system
2. add_executable(world hello_world.cpp) [places with “world” change it to the executable name you want to have for your program]

I have used the raylib library in the example. Change the library path to the one you want to link. If you want to have more libraries, add more target, target_link_libraries in the file. 

----------------------------------------
##### Commands to run (on terminal/command-prompt)
Generating CMake files

`cmake .` [if no compiler is specified]


`cmake -G "MinGW Makefiles" .`

Buidling the program through maker file

`mingw32-make`

**Note:** raise an issue on this repository if you need additional help.


