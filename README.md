# bartman_gcc_support

Support library for Bartman's Amiga GCC compiler.
Files copied from [BartmanAbyss/vscode-amiga-debug](https://github.com/BartmanAbyss/vscode-amiga-debug)'s sample project.

The "latest" tag will always point to newest stable version.

## Usage

As a submodule:

```cmake
add_subdirectory(deps/bartman_gcc_support bartman_gcc_support)
target_link_libraries(${TARGET_NAME} PUBLIC bartman_gcc_support)
```

Using CPM:

```cmake
include(cmake/CPM.cmake)
CPMAddPackage(
	NAME bartman_gcc_support
	GITHUB_REPOSITORY AmigaPorts/bartman_gcc_support
	GIT_TAG latest
)
target_link_libraries(${TARGET_NAME} PUBLIC bartman_gcc_support)
```

If used inside object library, you might need a bit of a workaround:

```cmake
# Workaround for nested OBJECT library - https://stackoverflow.com/questions/71040175
target_link_libraries(${TARGET_NAME} PUBLIC bartman_gcc_support "$<TARGET_OBJECTS:bartman_gcc_support>")
```