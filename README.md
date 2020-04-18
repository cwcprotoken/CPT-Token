# CPT-Token
CPT Token

### Building from source

#### Get the source code

Git and GitHub are used to maintain the source code. Clone the repository by:

shell
git clone --recursive https://github.com/cwcpro/aleth.git
cd aleth


The --recursive option is important. It orders git to clone additional
submodules to build the project.
If you missed --recursive option, you are able to correct your mistake with command
git submodule update --init.

#### Install CMake

CMake is used to control the build configuration of the project. Latest version of CMake is required
(at the time of writing [3.9.3 is the minimum](CMakeLists.txt#L5)).
We strongly recommend you to install CMake by downloading and unpacking the binary
distribution  of the latest version available on the
[**CMake download page**](https://cmake.org/download/).

The CMake package available in your operating system can also be installed
and used if it meets the minimum version requirement.

> Alternative method
>
> The repository contains the
[scripts/install_cmake.sh](scripts/install_cmake.sh) script that downloads
> a fixed version of CMake and unpacks it to the given directory prefix.
> Example usage: scripts/install_cmake.sh --prefix /usr/local.

#### Build

Configure the project build with the following command to create the
build directory with the configuration.

shell
mkdir build; cd build  # Create a build directory.
cmake ..               # Configure the project.
cmake --build .        # Build all default targets.


On Windows we support Visual Studio 2017, and 2019. You should generate a Visual Studio solution file (.sln) for the 64-bit architecture via the following command:

* Visual Studio 2017: cmake .. -G "Visual Studio 15 2017 Win64"
* Visual Studio 2019: cmake .. -G "Visual Studio 16 2019" -A x64

After the necessary dependencies have been downloaded and built and the solution has been generated, aleth.sln can be found in the
build directory.

#### Common Issues Building on Windows
##### LINK : fatal error LNK1158: cannot run 'rc.exe'
Rc.exe is the [Microsoft Resource Compiler](https://docs.microsoft.com/en-us/windows/desktop/menurc/resource-compiler). It's distributed with the [Windows SDK](https://developer.microsoft.com/en-US/windows/downloads/windows-10-sdk) and is required for generating the Visual Studio solution file. It can be found in the following directory:
%ProgramFiles(x86)%\Windows Kits\<OS major version>\bin\<OS full version>\<arch>\

If you hit this error, adding the directory to your path (and launching a new command prompt) should fix the issue.

## Contribute
