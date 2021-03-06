# GNU Arm embedded toolchain for macOS

The GNU Embedded Toolchain for Arm is a ready-to-use, open source suite of tools
for C, C++ and Assembly programming targeting Arm Cortex-M and Cortex-R family 
of processors. It includes the GNU Compiler (GCC) and is available free of 
charge directly from Arm for embedded software development on Windows, Linux and
macOS operating systems.

<div>
<img src="https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/images/macOS.png" alt="macOS" width="24%">
<img src="https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/images/GNU.png" alt="GNU" width="24%">
<img src="https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/images/Cortex-M.png" alt="Cortex-M" width="24%">
<img src="https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/images/Cortex-R.png" alt="Cortex-R" width="24%">
</div>

This repository is the original macOS version of the GNU Compiler from Arm 
packaged for Visual Studio Code:
[GNU Arm embedded toolchain](https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads)

## Install
In Visual Studio Code goto extensions (shift+cmd+x), search for '*metalcode-eu*' 
and install the extension that is suited for your operating system. 

The extension has four paths for the toolchain. You can use them in the 
tasks.json.

- arm-none-eabi.bin
- arm-none-eabi.include
- arm-none-eabi.lib
- arm-none-eabi.libgcc
- openocd.bin
- openocd.scripts

Here is an example of tasks.json for GNU make. 
```javascript
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build firmware",
      "type": "shell",
      "command": "make test",
      "options": {
        "env": {
          "INCLUDE": "${config:arm-none-eabi.include}",
          "LIB": "${config:arm-none-eabi.lib}",
          "LIBGCC": "${config:arm-none-eabi.libgcc}/thumb/v6-m/libgcc.a",
        }
      },
      "osx": {
        "options": {
          "env": {
            "PATH": "${config:arm-none-eabi.bin}:${env:PATH}",
          }
        },
      },
      "linux": {
        "options": {
          "env": {
            "PATH": "${config:arm-none-eabi.bin}:${env:PATH}",
          }
        },
      },
      "windows": {
        "options": {
          "env": {
            "PATH": "${config:arm-none-eabi.bin};${env:PATH}",
          }
        },
      },
      "group": {
        "kind": "build",
        "isDefault": true,
      },
      "problemMatcher": "$gcc"
    }
  ]
}
```
With the following makefile:
```makefile
.PHONY: test

test:
	@echo $(PATH)
	@echo $(INCLUDE)
	@echo $(LIB)
	@echo $(GCCLIB)
```

## Release Notes

### Version 0.2.1
Version 9-2020-q2-update
Released: June 30, 2020

### Version 0.2.0
Open On-Chip Debugger version for PSoC6.

[Cypress Programmer (CYP) 2.1](https://raw.githubusercontent.com/metalcode-eu/darwin-arm-none-eabi/master/openocd-2.1/docs/Cypress_Programmer_2_1_CLI_User_Guide.pdf)

Run the shell script in the terminal to set symbolic links to the toolchain.  
```bash
./symlink.sh 
```

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