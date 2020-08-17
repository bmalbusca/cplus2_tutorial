# Standard IO

- ``stdout``: channel 1
- ``stderr``: channel 2

#### Redirecting

>**to ``stdout``is**:
>
> ``command 1> out.txt``
>
> or ``command >> out.txt``
>

>**to ``stderr`` is**:
>
> ``command 2> out.text``
>

> **to both:** `` program > out.txt 2>&1`` or in different files using ``program 1>stdout.txt 2>stderr.txt``
>

## Chaining commands
- cmd1; cmd2 - call 1 after another
- cmd1 && cmd2 - the same as before but fails if some returns non-zero code
- cmd1 | cmd2 - piping stdout of cmd1 to stdin cmd2

### Example
 find smith :  ``ls | grep smth``


## C++ IO streams - #include <iostream>

 - ``std::cin`` - stdin
 - ``std::cout`` - stdout
 - ``std::cerr`` - stderr

> **Note**
>
> - ``>>``  in 
>
> - ``<<``  out

# C++ Libraries

#### Strings
- ``#include <string>`` to use ``std::string``
- concatenate with **``+``**
- check if empty using ``str.empty()``

examples: 
``  std::string hello = "Hello";
    std::cout << hello + "Bruno" << std:endl; 
``




### Arrays - fixed size
- ``#include <array>`` to use ``std::array``
- store collections of items of same type and fixed size: `` array<float3>
arr = {1.0f,2.0f,3.0f}
- arr.size(); arr.clear(); arr.front(); arr.back()


### Vectors -dynamic table, usefull when you don't know the size
- ``#include <vector>`` to use std::vector
- **use the same methods as array**
- ``vec.emplace_back(value)`` can be more efficient than ``vec.push_back(value)``
- to optimize vector resizing use ``reserve(n)``
- vec.insert(,) is available such and iterator()


### Scopes
- easy example `` float  some_float=13.3f;
        { // New inner scope
            auto another_float = some_float; // copy
        }//another_float dies
    ``
### References
- Use **&** to state that a variable is a reference
- ``float& ref = original_variable;`` ref has type float&
- use ``const`` references as a funtion argument type for non fundamental variables types


### C++ features 

#### For loop
- similar to ``foreach()`` in Java, here we ahve ``for(float num: vector)`` 

#### Function overloading
- `` string Fun(int n){return "int";}
    string Fun(const string& str){return "string";} ``

### More tips
    - use ``#pragama once`` at header files 

### Search for
    - CMAKE makefiles - create folders  ``build`` and ``src``; to execute CMAKE you need to give
    the CMakeLists.txt path. Follow the typical set of instructions for the project; ALl
    subdirectories that we added, another CMakeLists need to exists there and can be empty!
    ``${PROJECT_SOURCE_DIR}/`` is a system variable that is usefull to set a full path; At the
    end we need to add a executable at the CMakeLists at src folder : ``add_executable(main_bin
            main.cpp)`` ; Then we can use only ``make`` at build folder unless if we added new
    files. A new src folder will appear inside build folder with the executable file
    - arc dynamic/static libraries

