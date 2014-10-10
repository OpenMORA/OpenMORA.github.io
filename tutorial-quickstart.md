OpenMORA 101
=============

Introduction
--------------

* **OpenMORA** is an open-source framework for distributed applications. It is based on:
  * **[MOOS](https://sites.google.com/site/moossoftware/)** ([GitHub](https://github.com/themoos)) for communications and app managing.
  * **[MRPT](http://www.mrpt.org)** ([GitHub](https://github.com/jlblancoc/mrpt)) for sensor interfacing, robotics algorithms and data marshalling.

* Together, MOOS and MRPT have a small footprint and allow modules to be written in C++ and run in a number of platforms and operative systems (Windows, OSX, GNU/Linux, GNU/kFreeBSD). 

* **Scripts** are provided to automate the process of updating and (re-)compilation from sources.

* **MOOS** is a middleware based on the publish-subscribe (pub/sub) pattern. It comprises a core C++ library and a set of tools for managing and monitoring communities of distributed *modules*. There exists a central hub called *MOOSDB*.

* **Repositories** or **packages**: Git repositories published by partner institutions. Each repository may contain one or several *modules*.

* **Modules**: The smallest elements in OpenMORA. They are executable programs capable of publishing to or subscribing to *topics*. 

* **Topics** are *named, shared variables* that represent the unique kind of interaction between modules. 

* **MOOS-only modules** can interact with topics of only two types: `double` and `string`/`binary`. 

* **MOOS+MRPT modules** can exchange more complex messages in the form of convenient C++ classes, e.g. laser scans, occupancy grid maps, etc.

Note: It is **strictly mandatory** to study how MOOS works before getting deeper into OpenMORA. Study [these MOOS tutorials](https://sites.google.com/site/moossoftware/home/documentation/documentation).


Online organization
--------------------

The [OpenMORA GitHub organization](https://github.com/OpenMORA) contains these repositories:

* **`mora-base`**: The core of OpenMORA: core tools and common libraries: core-moos, essential-moos and OpenMORA scripts (`mora-build`, etc.).
  * [`mora-base/distro/openmora-pkgs.yaml`](https://github.com/OpenMORA/mora-base/blob/master/distro/openmora-pkgs.yaml): List of all "official" OpenMORA repositories. 

* [`dataset-tools-pkg`](https://github.com/OpenMORA/dataset-tools-pkg): Modules for grabbing datasets in MRPT [RawLog format](http://www.mrpt.org/Rawlog_Format) and playing them back.

* Many other repositories. Browse [their documentation](mooxygen.md) or [directly on GitHub](https://github.com/OpenMORA).



Working directory structure
-----------------------------

After [installing](tutorial-install.md), this is the recommended directory layout: 

* `OPENMORA_DIR`: The root or **workspace** directory, located anywhere in the system.
  * `OPENMORA_DIR/bin`: Executables built from all the modules.
  * `OPENMORA_DIR/mora-base`: Core components
  * `OPENMORA_DIR/*-pkg`: Other OpenMORA packages
    * `OPENMORA_DIR/*-pkg/build`: Temporary build and CMake files for each package.


