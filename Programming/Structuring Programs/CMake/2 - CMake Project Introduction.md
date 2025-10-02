[[1 - What are CMake and Build Systems]] <- Back
[[3 - Libraries with CMake]] <- Next

---
## How to use CMake with Projects
All that is required is a txt file called CMakeLists.

The most basic, functional CMake file requires three functions.
- cmake_minimum_required()
- project()
- add_executeable()

NOTE: A CMake file should be treated as code as that is how it is used when building a project.


### cmake_minimum_required()
cmake_minimum_required() is a function, which is the very first function used in a CMakeLists.txt file, that specifies a minimum CMake version that can be used with this project.

```CMake
cmake_minimum_required(VERSION 3.15)
```
- VERSION is a reserved word, indicating the following value is the version value.

Setting a minimum required versions means that a CMake version, below the minimum, CANNOT be used to build the project.

cmake_minimum_required() can take a range of versions, with an upper and lower bound.

```CMake
cmake_minimum_required(VERSION 3.15...4.0)
```

### project()
After cmake_minimum_required() comes project().
- Should be called directly, or very soon, after cmake_minimum_required().
- This function call is REQUIRED for any CMake-built project.

project() can be used to...
- Give a name to a project.
- Give a version number to a project.
	- By giving a version number to the project, multiple built-in variables are assigned that value too.
- Give a description to a project.
- Specify the programming language used in the project.

```CMake
project(
	projectName
	VERSION x.y
	DESCRIPTION "projectDesc"
	LANGUAGES CXX
)
```

NOTE: CXX means C++. Cannot directly specify C++ due to special characters.

### add_executeable()
add_executeable() is a function which allows an executeable target to be BUILT from the source files listed in the project.
- This is what CMake compiles, resulting in the executable.

CMake has the following parameters...
```CMake
add_executeable(<name> <options>... <sources>...)
```
- name is a singular string literal parameter, specifying the name the executable will be given post compilation

- options can be a sequence of options which allow additional behaviour, such as setting target properties automatically.

- sources are the main file of the project, such as main.cxx (not cpp in CMake files).

## All together example
```CMake
cmake_minimum_required(VERSION 3.15)

project(
	SandCrawler
	VERSION 1.0
	DESCRIPTION "Software used for motion and motion planning"
	LANGUAGES C CXX
)

add_executeable(SandCrawler main.cpp)
```