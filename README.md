## Binary to Header


### **Description:**

Converter for binary files to C/C++ headers.

***bin2header*** takes any file as an argument and converts its binary data into a source header file for use in C/C++
applications. The data is stored as a character array.


### **Licensing:**

[MIT](LICENSE.txt)

### **Downloads:**

- Latest release: [v0.2.0](https://github.com/AntumDeluge/bin2header/releases/tag/v0.2.0)
- Latest Python release: [v0.1.2](https://github.com/AntumDeluge/bin2header/releases/tag/v0.1.2)


### **Building:**

#### 'configure' script:

<blockquote style="padding-left:2em; font-family:monospace;">
<b>USAGE:</b> ./configure [--help] [--type=TYPE] [--static]<br><br>
Options:<br>
<span style="padding-left:2em; font-weight:bold; font-style:italic;">--help</span> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Show this help text<br>
<span style="padding-left:2em; font-weight:bold; font-style:italic;">--type=TYPE</span> &nbsp; Set to "b" (default) for binary executable "s" for Python script<br>
<span style="padding-left:2em; font-weight:bold; font-style:italic;">--static</span> &nbsp;&nbsp;&nbsp;&nbsp; Create statically linked executable (binary only)
</blockquote>

- To build native binary, run: `./configure && make`
- To build static native binary, run: `./configure --static && make`
- To build python version, run: `./configure --type=s && make`

#### CMake (native binary only):

To configure & build run `cmake <path_to_source> && cmake --build ./`.

Example of building from source root directory:

```sh
cmake ./ && cmake --build ./
```

Example of building from sub-directory in source root:

```sh
mkdir build
cd build
cmake ../ && cmake --build ./
```

After building is complete, files can be installed with:

```sh
cmake --install ./
```

To get a list of available CMake configuration options run `cmake -LA <path_to_source>`.

Notable CMake configuration options:

- `CMAKE_INSTALL_PREFIX`: target directory where files are installed with `cmake --install`
- `STATIC`: link to dependencies statically (default: OFF)
- `EMBED_ICON`: (Windows only) add icon resource to PE32 executable (default: OFF)

Example of building on Windows with MinGW:

```sh
mkdir build-win32 && cd build-win32
cmake -G "MinGW Makefiles" -DCMAKE_INSTALL_PREFIX="$(pwd)/install" -DSTATIC=ON -DEMBED_ICON=ON ../
cmake --build ./
cmake --install ./
```
