Installing
==========


## 1. Prerequisites 
* A C++ compiler
* [CMake](http://www.cmake.org/)
* [mrpt](http://www.mrpt.org/)
* Python CLI ([Windows download](https://www.python.org/download/windows)) with the modules:
  * YAML ([Windows download](http://pyyaml.org/wiki/PyYAML))

In Ubuntu, run: 

```bash
sudo apt-get install build-essential cmake python python-yaml libmrpt-dev
```
    
In Windows: 

 * Remember to add Git, CMake and Python to the system PATH env var.

## 2. Download and build `mora-base`
Create an empty directory for OpenMORA packages:

```bash
mkdir openmora && cd openmora
```

Get a copy of the `mora-base` pkg (note the `--recursive`, required to init the external submodules):

```bash
git clone --recursive https://github.com/OpenMORA/mora-base.git
```

Compile with CMake:

```bash
mkdir build && cd build 
cmake ..
make
```

## 3. Setting up environment
In Linux, add this line to ~./bashrc

```bash
source [path to mora-base]/scripts/mora-setup.sh
```
    
In Windows, set these environment vars:

  * `MORA_PATH`: List of directories containing OpenMORA pkgs. Separator is ";" in Windows, ":" in unices. Must point to the *parent* directory of MORA pkgs, such that  `$MORA_PATH/mora-base/` exists.
  * `MORA_CMAKE_GENERATOR`: Must be set in Windows to the desired CMake generator, e.g. "Visual Studio 10 Win64"
  * Manually add `[MORA-BASE_PATH]/scripts/` to the `PATH` env var.
  * `MORA_EXECUTABLE_OUTPUT`: (Optional) If defined, will override CMake's default `EXECUTABLE_OUTPUT_PATH`. Can be used to put all executables into one single directory.
    

## 4. Download & build the rest of pkgs
Note that the following commands work on both *Windows* and *Linux*.

To download all publicly listed pkgs, simply run: 

```bash
mora-pull --all
```

Build by calling CMake for each directory, or do it automatically with:

```bash
mora-build            # Builds pkg at current dir
mora-build ual*-pkg   # Builds specific pkgs
```
    
Move into the directory of some module with `mora-cd`

```bash
mora-cd mora-base 
```


