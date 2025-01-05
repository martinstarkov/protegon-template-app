# Modification

Inside of `CMakeLists.txt`, change `project(protegon-template-app)` to whatever you wish the executable to be called.

# Build Instructions

0. Clone this repository such that the [protegon engine repository](https://emscripten.org/) is cloned in the same repository, i.e:
- /Dev/protegon
- /Dev/your_project_name
1. `mkdir build` inside of this repository to create a build directory.
2. `cd build` to enter the created build directory.
3. Depending on your build system, follow the appropriate next steps:

# Microsoft Visual Studio

4. `cmake .. -G "Visual Studio 17 2022"` to generate build files.
5. Open the generated `<your_project_name>.sln` file.
6. Set `<your_project_name>` as the startup project.
7. Build and run.

# Ninja

4. `cmake .. -G Ninja` to generate build files.
5. `ninja` to build the project.
6. `./your_project_name.exe` to run your executable.

# Linux

4. `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` (Installs [Homebrew](https://brew.sh/) for Linux).
5. (required if brew not in PATH) `(echo; echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"') >> /home/<your_username>/.bashrc`
6. (required if brew not in PATH) `eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"`
7. `cmake .. -G "Unix Makefiles"` to generate build files.
8. `make` to build the project.
9. `./your_project_name` to run your application.

# Mac OS

4. `cmake ..` to generate build files.
5. `make` to build the project.
6. `./your_project_name` to run your application.

# Xcode

4. `cmake .. -G Xcode` to generate build files.
5. `make` to build the project.
6. `./your_project_name` to run your application.

# Emscripten (WebGL)

Additional Dependencies:
---
* [Emscripten SDK](https://emscripten.org/): Check that Emscripten is added to PATH by running ```emcc --version```
* [Ninja](https://ninja-build.org/) or [MinGW](https://www.mingw-w64.org/): Check that Ninja/MinGW is added to PATH by running ```ninja --version``` or ```gcc --version``` respectively
---
Emscripten Building
---
Navigate to the scripts directory:

```cd scripts```

Run any of the following script commands:

| Command    | Description |
| -------- | ------- |
| ```./build-emscripten.sh```  | Generates emscripten build files (index.html, etc) in the build directory |
| ```./run-emscripten.sh``` | Runs the generate build files locally using emrun |
| ```./build-run-emscripten.sh```    | Combines the two above scripts |
| ```./zip-for-itch.sh```    | Zips the generated build files and places the zip in the build directory |
| ```./build-itch.sh```    | Combines the above build and zip scripts |

---

# Misc Information

- If you get the error ```A required privilege is not held by the client``` when creating a symlink using ```create_resource_symlink``` on Windows, [turn on Developer mode](https://learn.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development).
