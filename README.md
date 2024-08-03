Add raylib binaries into your vscode C++ project in `5 minutes`
---
# Steps
### Clone repository
Open any folder and open cmd/powershell
```git
git clone https://github.com/kallesi/raylib-vscode-template.git
```
### Configure compiler
- Requires mingw64 gcc/g++ compiler on your system
- I recommend using the method described in [this video](https://youtu.be/oC69vlWofJQ?si=SHjvfVYhuTKK9KMV) or follow the instructions from [VSCode Documentation](https://code.visualstudio.com/docs/cpp/config-mingw)
- Add the compiler `/bin` directory to PATH
- VSCode should now "see" your compiler.
### Configure `.vscode` folder
- Change any references to the compiler path to your own installation directories.
- For C++, you should point to your `g++.exe` and `gdb.exe` installations, both should be under a `bin` folder.
### See if your projects compile
- The default config files should work out of the box, but if you want to change your project strucutre to something other than the '/lib' '/include' folder configuration, please update the flags in the config files accordingly.

# Building your own Raylib Binaries
With mingw64 you can also build your own raylib libraries from source, as this repo may not be maintained in the future. More detailed instructions on Raylib [wiki](https://github.com/raysan5/raylib/wiki/Working-on-Windows/_edit) or this great [YouTube video](https://www.youtube.com/watch?v=HPDLTQ4J_zQ)
### Clone repository
- Clone repository anywhere
```git
git clone https://github.com/raysan5/raylib.git
```
### Build binaries
Using MinGW make tool, navigate from command line to `raylib/src/` folder and type:
> You must have mingw installed and added to PATH
```powershell
mingw32-make PLATFORM=PLATFORM_DESKTOP
```
### Include header and binaries
- After building the binaries, the `raylib.h` header file and `libraylib.a` binary file are all you need for adding raylib to your project.
- You can find them both in the same `raylib/src/` folder
- Copy them to the project. On this repo they are under their respective `include` and `lib` folders
- This method is portable and you don't have to mess with configurations. Just add these to whichever project you need raylib for and you are good to go. 

