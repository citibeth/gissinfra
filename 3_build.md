# Build: The Achilles Heel

Building software is not sexy, but it is critical!
 * Increasingly required for ModelE
   - ModelE+Ice has dozens of dependencies, does not yet run on discover.

## Building on a Mac: MacPorts
 * Gets you the software you need
 * Can be run without Admin privileges:
   - https://github.com/citibeth/usermacports
   - But GISS needs to use it!
 * Can install many but not all Python modules
 * Builds python consistent with GCC toolchain
   - Necessary for our Python extensions.
 * **Macintosh only! :-(**

## Building on Posix: EasyBuild
 * Works on Mac and Linux
   - Build scripts are cross-platform
   - Needed for useful work between desktop Macs and discover
 * Requires some work to set up required GISS software
 * NCCS sysadmins will appreciate it?
   - Easier than building by hand.
   - Integrates with module system.

## Python Environment: Conda, PyPi
 * Better and more complete for Python stuff
 * Open question: how to combine EasyBuild + [Conda + PyPi](https://www.linkedin.com/pulse/20140107182855-25278008-using-pypi-packages-with-conda)?

