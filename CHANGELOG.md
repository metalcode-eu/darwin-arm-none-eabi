### Version 0.0.6
Replaced toolchain with Version 7-2018-q2-update for macOS.
Added a script symlink.sh to create symlinks to toolchain.

### Version 0.0.5
The path separator punctiantion is a *colon :* in macOS and Linux and a 
*semicolon ;* in Windows. To handle these operating system specific differences 
I updated the tasks.json and added a simple makefile to test. You can use this 
tasks.json and makefile to check your paths. 

### Version 0.0.2
Using the tilde in the paths had some problems during linking:

~/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.1/bin

~/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.1/arm-none-eabi/include

~/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.1/lib

Changed default paths:

${env:HOME}/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.2/bin

${env:HOME}/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.2/arm-none-eabi/include

${env:HOME}/.vscode/extensions/atomclip.darwin-arm-none-eabi-0.0.2/lib

Added GNU Make 3.81 to bin directory.