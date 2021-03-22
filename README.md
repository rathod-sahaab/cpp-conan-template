# CPP conan template

A template repo to quickly start cpp projects using [conan package manager](https://conan.io) and CMake.

_Inspired by [ForgottenUmbrella's gist](https://gist.github.com/ForgottenUmbrella/0f32f6446b2948a3a5a99687b264910d)_

## Configure

1. Change project name in `CMakeList.txt`.
2. Update dependencies in `conanfile.txt`.

## Setup

Run

```sh
./setup.sh
```

or

```sh
mkdir build && cd build
conan install ..
cmake .. -DCMAKE_EXPORT_COMPILE_COMMANDS=1 # generates compile_commands.json

ln -s compile_commands.json ../compile_commands.json # link compile_commands.json to home dir
```

**Note:** Omit `ln -s ...` for windows manually copy compile_commands (AFAIK ln is not supported on windows).

## Compile

#### After file changes

```sh
cd build
make -jX
```

_**X**: number of CPU threads on your machine_

#### After dependencies changes

```sh
cd build
conan install ..
cmake .. -DCMAKE_EXPORT_COMPILE_COMMANDS=1
```

## Binary

Binary/app can be found in `build/bin/` which will be same as your project name.
