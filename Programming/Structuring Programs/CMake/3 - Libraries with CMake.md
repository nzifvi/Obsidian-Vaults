[[2 - CMake Project Introduction]] <- Back

---
## Libraries with CMake
CMake can be used to add libraries to a project, handling...
- Linking header files.
- Linking implementation files.
To the project during compilation.


Without CMake, all source files would need to be placed within the same directory for them to be includeable in a project.

With CMake, a project can be organised into multiple subdirectories to logically structure the project.

## Creating Libraries

## Using Libraries

### Specifying Library Header file path.
To use a library, the header files of the library must be included into the project. The CMake function which handles this is called...
```
target_include_directories(
	<projectName>
	<accessSpecifier>
	<.../headerFileName>...
	<.../implementationFileName>...
)
```

NOTE: target_include_directories() should be called AFTER add_executeable()

Using this approach means that EVERY absolute file path for EVERY header and implementation file must be specified.
- There is a faster way which means that not every file path for all header files and implementation files have to be specified.
- uses file() function, which must be called BEFORE add_executeable().

### file()
file() will be covered later in more depth, as it has a LOT more uses than just this.
- To know for now: file() is a file manipulation function.

With this method, target_include_directories STILL handles linking header files whilst implementation files being found are now handled by file() and merged into one variable referring to ALL found implementation files.

file() has the following parameters...
```CMake
file(<option> <variableName>
	<filePath>...
)
```

option will be by default GLOB. 
- another option, GLOB_RECURSE, traverses ALL subdirectories of the specified directory and includes them within the results list as long as they meet the filePath criteria.

- variableName is a name assigned to refer to ALL of the files included in the result of the file manipulation.

- filePath should be the list of all directories to include. append /\*\.cpp to the end of EACH directory file path.
	- Results in ALL files with a file extension of cpp to be added by file() in result list.

##### EXAMPLE:
````CMake
file(GLOB_RECURSE SOURCES
	"Engines/Implementations/*.cpp"
	"Utilities/Implementations/*.cpp"
	"main.cpp"
)

add_executeable(){
	RobotUtilities ${SOURCES}
}

target_include_directories(RobotUtilities PRIVATE
	${CMAKE_SOURCE_DIR}/Engines/Headers
	${CMAKE_SOURCE_DIR}/Utilities/Headers
)
```