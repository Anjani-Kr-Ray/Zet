# Introduction to Package Manager

On Windows OS we generally visit the software download page we want to install and then click on the download button present there. It downloads an .exe file which we can run and it will install the software on our Computer. On Linux tough this method is possible, however it is not the best way to do it.

### How to install software on Linux?
* We mostly install apps on Linux with package manager tools.
* Before getting into package manager lets us know what is a software package.

### Software Package
* A compressed archive, containing all required files
* Apps usually have dependencies that are not packaged into the compressed archive. These dependencies also need to be installed

### Package Manager
* download, installs and updates existing software from a repository
* ensures integrity and authenticity of the package
* manages and resolves all required dependencies
* knows where to put all the files in the Linux File System
* easy upgrading of the software

__Where to find Package Manager?__
* Package Manager is already installed in every `Linux Distribution`
* In `Ubuntu`, we have `APT`(Advance Package Tools) Package Manager available

### Manage Software with APT
* __sudo apt search <package_name>__ : seach for a given package
* __sudo apt install <package_name>__ : install a given package
* __sudo apt install <package_name1> <package_name1>__ : install multiple package using one command
* __sudo apt remove <package_name>__ : remove a installed package

### Difference between APT and APT-GET
* `APT` is more user friendly, like progress bar
* `APT` has fewer, but sufficient command options in a more organized way
* `APT-GET` doesn't have a **search** command

### Where do these packages come from?
Linux uses repositories to store thousands of software packages. These repositories are mainly hosted online. Package Manager fetches the packages from these repositories.

> __Note:__ Always update the package index before upgrading or installing new packages. Use `sudo apt update` which updates the package index.

> __Why Updating Package Index__?
> * pulls the latest changes from the APT repositories
> * the APT package is basically a database
> * holding records of available packages form the repositories

### Alternative ways to install software
Sometimes, it may be possible that the required software is not available on repository hosted by that distribution. Then we can use of the ways to install that software

1. Snap Package Manager
	* intial release in 2014 with name __snappy__
	* Snap is a software packaging and deployment system for OS using Linux Kernel
	* snap is a bundle of an app and its dependencies
	* Snap Store: provides a place to upload snaps, and for users to browse and install the software
	* Snapcraft: is the command and framework used to build and publish snaps

 * __Difference between Snap and APT:__

	|       | Snap | APT |
	| :---: | :----: | :---: |
	| 1. | Self-contained - dependencies in the package | dependencies are shared |
	| 2. | Supports universal Linux packages (package type .snap) | only for specific Linux distributions(package type .deb)
	| 3. | Automatic updates | Manual updates |
	| 4. | Large Installation Size | Smaller Installation Size |
	| 5. | Use when necessary | Recommended |

2. Ubuntu Software Store : User interface of snap tool (only available on Ubuntu OS)
3. Add Repository to official list of Repository :
	* add repository to APT sources (into */etc/apt/sources.list*) - *`sudo add-apt-repository <link to repo>`*
	* install package as usual
	* PPA : Personal Package Archive
		* PPA's are provided by the community
		* anybody can create this PPA - private repo to distribute the software
		* usually used by developers to provide updates more quickly than in the official Ubuntu OS
		* Be aware of possible risks before adding a PPA:
			* no guarantee of quality or security
			* like any other unofficial software package it can cause difficulties e.g. when upgrading to a new Ubuntu release

> __Note:__ 
> There are two types of Linux Distributions available in market.
> 1. __Debian Based__ - like Ubuntu, Debian, Mint which uses APT or APT-GET package manager
> 2. __Red Hat Based__ - like RHEL, CentOS, Fedora which uses YUM package manager





