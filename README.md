<h1 align="center">EzTest Template</h1>
<p align="center"><i>A template for C projects using <a href="https://github.com/havardt/EzTest">EzTest</a> as the main unit testing framework.</i></p>


## :mega: About
This repository provides a base project layout and defines a set of CMake files for managing the C project. The project is configured for building a library which is tested with EzTest.

### :construction: Project structure
```
├── build.sh
|
├── CMakeLists.txt
|
├── src
│   └── CMakeLists.txt
|
├── test
|   ├── CMakeLists.txt
|   └── eztest
|       └── README.md

```

##### :page_with_curl: /build.sh    
A convenience script for quickly building the project with CMake.

##### :page_with_curl: /CMakeLists.txt  
The top level CMakeLists.txt file.

##### :open_file_folder: /src    
This directory should contain all the source code for the library/program that you are creating. This should not include test code.

##### :page_with_curl: /src/CMakeLists.txt 
The CMakeLists.txt file for the source code. By default it is set up to build a static library. 

##### :open_file_folder: /test   
This directory should contain all the source code for your unit tests.

##### :page_with_curl: /test/CMakeLists.txt  
The CMakeLists.txt file for the test code. It is configured to build the EzTest runner.

##### :open_file_folder: /test/eztest     
This directory should contain the source code for EzTest. This is both the ```eztest.h``` header used for writing unit tests and the EzTest ```runner.c``` file for creating the program that runs the unit tests.


## :rocket: Getting Started
See ['creating a repository from a template'](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template) for how to use templates on Github.

#### :gear: Configure
After getting a copy of the template, there are a few things that you may want to change to fit your project. 

###### Project name
In the top level [CMakeLists.txt](CMakeLists.txt) file, you should change the project name from the default to the name of your project.

###### Source code
The [src](src) directory is, by default, set up to build a static library. In the [CMakeLists.txt](src/CMakeLists.txt) file you can change the name of the library. This change needs to be reflected in the [CMakeLists.txt](test/CMakeLists.txt) file of the [test](test) directory such that the tests can access the library.

The source code files for this library must be added to the [CMakeLists.txt](src/CMakeLists.txt) in the designated area (marked with a comment).

###### EzTest
To configure EzTest you must add the source files for EzTest in the [test/eztest](test/eztest) directory. See [EzTest releases](https://github.com/havardt/EzTest/releases).

###### Test code
Your test files must be added to the ```add_executable``` command of the [CMakeLists.txt](test/CMakeLists.txt) file within the [test](test) directory. A comment marks the location.

#### :hammer_and_wrench: Build
Once you have configured the project to your liking and written some code for your library or program and unit tests, you are ready to build. As this is a CMake project you can build it just like any other CMake project. This can be a bit tedious, so a [build script](build.sh) has been provided.

Building results in and ```out``` directory being made. Within this directory you will see that a ```lib``` directory has been created. This directory contains the built library from the ```src```. A ```test``` directory is also created. This directory contains the [EzTest runner](https://github.com/havardt/EzTest#runner). Executing this file runs the unit tests. The tests can also be run by executing ```ctest``` command within the ```out``` directory. This will, however, not display the output from EzTest as it is absorbed by ctest.

## :scroll: License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
