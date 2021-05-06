---
layout: post
title:  CSV CLI Installation
date:   2021-04-30 12:26:08 +0100
categories: cli
permalink: /cli-instructions/
---
## Installation

This project uses Docker to isolate the user's system from the program's requirements and to ensure a consistent container with the correct libraries and configurations is available for running the program and reproducing results.

- Get Docker and launch it:
  <!-- - If you don't want to create an account to download the program you can login with the uvoids username and password, but please log out afterwards. -->
  - Download the relevant Docker installer for your particular operating system:
    - [get docker](https://docs.docker.com/get-docker/){:target="_blank" rel="noopener"}
  - Launch Docker and wait for it to finish starting (check the whale in the OS status or menu bar).
- Get the uvoids image:
  - Launch a new terminal console (terminal on Mac, cmd on Windows).
  <!-- - Login to the private uvoids dockerhub. Run `docker login -u username` (use the docker password provided). -->
  - Pull the image: `docker pull uvoids/uvoids:0.1.0`
  <!-- - Logout so that others can login: `docker logout` -->
- Build the container and bind it to your data folder:
  - MacOS / Linux: `docker run -i -t -v ~/uvoids:/home/app/uvoids --name uvoids uvoids/uvoids:0.1.0`
  - Windows: `docker run -i -t -v Users\<USERNAME>\uvoids:\home\app\uvoids --name uvoids uvoids/uvoids:0.1.0`/
- You are now in the linux virtual machine. Type `exit` inside the vm to leave. The installation is finished

## Usage

- Make sure docker is running.
- Launch a new terminal console.
  - Press `cmd + space` and type terminal in MacOS.
  - Press `Windows + R` and type cmd in Windows.
  - Press `Alt + F2` and type terminal in Ubuntu.
- Launch the uvoids docker: `docker start -a -i uvoids`
- You are now in the virtual machine. Run uvoids:
  - There is only one command, `uvoids`.
  - Run `uvoids --help` to get the help screen.
  - Run `uvoids -a` to run all calculations with variables reflecting those used in the last summer school in Lisbon.
  - Read the help screen for specifics on setting variables or running specific commands.
- The program will deliver the results in the uvoids/data/output folder you created earlier.

The first time you launch uvoids it will create a uvoids data folder on your home folder. You should copy you input shapefiles there.

Naming conventions for input files and folders are available in the command line help. The default input folder is **~/uvoids/data/input/**. The default input filenames are: **horizontal_limits.shp**, **planar_limits.shp**, **volumetric_limits.shp**. These can be changed with command line arguments. The default output folder is **~/uvoids/data/output/**.

Please note: The script will do a CRS check on your input files and use whichever CRS your file is in throughout the calculations. If it can't find one, it will assume the file is in ~~EPSG:3857 (WGS84 Web Mercator)~~ (we are using EPSG:4326 at the moment while testing to emulate the qgis plugin behaviour with default qgis installs). If it finds files with different CRS values, it will stop and ask you to fix it. In the future, we will give an option to choose one of the values and let it transform the other files.

If you want to play with different options or use only parts of the script then check the help and run `uvoids` with your chosen arguments and options, i.e.:

- You only want to calculate urban limits and topology:

```bash
uvoids -e --calculate_limits --calculate_topology
```

- You want to change the factor of vertex significance in the calculations:

```bash
uvoids --vpp_vertex_significance=1
```

- You want to change the tolerance values:

```bash
uvoids --tolerance=0.0001
```

- There are other options and arguments you can mix and match. Please check the help screen in the terminal, or the help page [here]({{site.baseurl}}{% post_url 2021-04-30-cli-instructions %})

## Issues

If you run into any issues please create an issue on the [issues report page](https://github.com/joaoponceleao/dcg_uvoids/issues/new/choose){:target="_blank" rel="noopener"} so we can follow it and either, fix it, or suggest alternatives. Please check for any open or closed issues first in the [issues list page](https://github.com/joaoponceleao/dcg_uvoids/issues?q=is%3Aissue){:target="_blank" rel="noopener"}.

## Contributing and Branches

Source code access is currently by invitation only. If you wish to participate please get in touch through our [main website](http://solidvoids.fa.ulisboa.pt){:target="_blank" rel="noopener"}.

The repository follows the following branch organisation:

- `master` Contains the CLI code. We will try to move most common code here.
- `test_*` Test branches for specific issues or experiments.
- `qgis2` Contains the existing QGIS 2 plugin code.
- `qgis3` Contains the QGIS 3 code (currently under development).

There are three main branches at the moment.

The `qgis2` branch houses the original code for QGIS 2. The `qgis3` branch is a quick port of the QGIS 2 plugin to Python 3 and the QGIS 3 plugin system. The `master` branch at the moment houses the cli code and should be platform-agnostic branch. Other branches may crop up (gui, server, etc). Ideally other branches would only contain code relevant to running the master branch code in their respective platforms (i.e. for the cli version this would be the `__main__.py` file currently in the master branch and nothing else).

Any other branches, i.e. `test_*`,  are simply development branches and can be ignored. You may want to create your own development branch if you are going to make a lot of structural changes.

Eventually we will want to create a rhino branch, a frontend branch, and a backend branch.

When making changes and pushing back into the repository please make sure you have checked out the relevant local branch and are pushing to the correct remote branch.
Further instructions and prerequisites are available in the source code repository.
