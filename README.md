Minimal reproduction example for VSCode CPP Tools issue #7221
=============================================================

[Issue link](https://github.com/microsoft/vscode-cpptools/issues/7221)

Prerequisites
-------------

- VSCode
- GCC
- Meson/Ninja build system
  - Installed using `pip install meson ninja`
- Microsoft VSCode CPP Tools extension

Steps to reproduce
------------------

1. Build project using include VSCode build task
2. Ensure it compiles successfully

   - If build succeeded, you should see something like this:

   ```text
        > Executing task: meson /usr/local/home/anatoly/vscode-cpp-test/../build/ <

        The Meson build system
        Version: 0.56.2
        Source dir: /usr/local/home/anatoly/vscode-cpp-test
        Build dir: /usr/local/home/anatoly/build
        Build type: native build
        Project name: vscode-cpp-test
        Project version: 1.0.0
        C compiler for the host machine: cc (gcc 9.3.0 "cc (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0")
        C linker for the host machine: cc ld.bfd 2.34
        C++ compiler for the host machine: c++ (gcc 9.3.0 "c++ (Ubuntu 9.3.0-17ubuntu1~20.04) 9.3.0")
        C++ linker for the host machine: c++ ld.bfd 2.34
        Host machine cpu family: x86_64
        Host machine cpu: x86_64
        Configuring config.h using configuration
        Build targets in project: 1

        Found ninja-1.10.0.git.kitware.jobserver-1 at /usr/local/bin/ninja

        Terminal will be reused by tasks, press any key to close it.

        > Executing task: ninja -C /usr/local/home/anatoly/vscode-cpp-test/../build/ <

        ninja: Entering directory `/usr/local/home/anatoly/vscode-cpp-test/../build/'
        [2/2] Linking target vscode-cpp-test

        Terminal will be reused by tasks, press any key to close it.
   ```

3. Open `test.c` file in the editor

   - The editor will have error squiggles around the include despite build succeeding
