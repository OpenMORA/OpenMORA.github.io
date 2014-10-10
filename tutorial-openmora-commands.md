OpenMORA comamnd-line reference
==================================


`mora-cd`
-------------------

**Purpose:** cd (change dir) into the given module. Default workspace is the parent dir of `mora-base` path.

**Usage:** 

```bash
mora-cd                 # go to default modules workspace directory
mora-cd [MODULE_NAME]   # go to module dir
```


`mora-pull`
-------------------

**Purpose:** Download all MORA modules and/or pull the most recent changes from their repositories. 
Default workspace is the parent dir of mora-base path.

**Usage:**

```bash
mora-pull --all  # Use on bootstrap: download all known pkgs in the distro file
mora-pull        # Synch (update/pull) changes of all pkgs in the workspace
```

`mora-build`
-------------------

**Purpose:** Build the MORA module at CWD, or at the paths passed as argument. 

This implies:

* Creating `$DIR/build`
* Running `cmake`
* Running `make` (Linux) or `msbuild` (Windows)


**Usage:**

```
mora-build [-h] [--rebuild] [--all] [PKGDIR [PKGDIR ...]]

Builds one or more MORA modules.

positional arguments:
  PKGDIR      names of packages to build

optional arguments:
  -h, --help  show this help message and exit
  --rebuild   forces a rebuild
  --all       builds all packages in the repository
```



