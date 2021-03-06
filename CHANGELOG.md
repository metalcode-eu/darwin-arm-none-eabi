### Version 0.2.1
Version 9-2020-q2-update
Released: June 30, 2020

### Version 0.2.0
Open On-Chip Debugger version for PSoC6.

[Cypress Programmer (CYP) 2.1](https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/openocd-2.1/docs/Cypress_Programmer_2_1_CLI_User_Guide.pdf)

### Version 0.1.9
Version 8-2019-q3-update
Released: July 10, 2019


### Version 0.1.7
Added Open On-Chip Debugger 0.10.0+dev-1.0.0.226 (2018-11-09-17:51) 

### Version 0.1.6 
Version 8-2018-q4-major for macOS 
Released: December 20, 2018

### Version 0.1.3 
Modified atomclip to metalcode-eu.

### Version 0.1.2
Fixed typo in path to repository causing a wrong link in the marketplace.

Added a path to the libgcc files. 
- arm-none-eabi.libgcc

When you do bare metal development, you often exclude all standard libraries 
but you still need libgcc.a for integer division etc. The path to this file 
contains a version number that changes with every release of the toolchain. 
Using this variable you do not need to update your makefiles with every new 
release of the toolchain. 

### Version 0.1.0
Version 7-2018-q2-update for macOS
Added ./symlink.sh to create symlinks in /usr/local/bin.

### Version 0.0.5
Operating system specific PATH environment variable. 

### Version 0.0.2
Changed default paths, added GNU Make 3.81.

### Version 0.0.1
Version 7-2017-q4-major for macOS
Released: December 18, 2017