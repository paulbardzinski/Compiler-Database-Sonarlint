# Generate Compile Commands For SonarLint (C, C++)
If you use MingW for C++ compilation, you can use this script to generate the compile_commands.json file.


## Usage:
``.\compileCommandsSetup.ps1 <FILE NAME> <EXTRA PATH>``

## Example:
1. Place the `compileCommandsSetup.ps1` file in the root folder:

```
Root Folder/
├── .vscode/
│   ├── settings.json
├── src/
│   ├── myCppFileMain.h
│   ├── myCppFileMain.cpp
│   ├── otherCppFiles.cpp
├── **compileCommandsSetup.ps1**
```

<br />

2. Open PowerShell in the root folder and run it:

``.\compileCommandsSetup.ps1 main src/``

- `myCppFileMain` - this is the name of your cpp file, without the cpp file extension
- `src/` -this is another parameter added to the project root path, in this example we need to add `src/` because our cpp file is there.

<br />

3. Now check the root folder!

```
Root Folder/
├── .vscode/
│   ├── settings.json
├── src/
│   ├── myCppFileMain.h
│   ├── myCppFileMain.cpp
│   ├── otherCppFiles.cpp
├── **compile_commands.json**
├── compileCommandsSetup.ps1
```

4. After opening the Visual Studio code, open the command palette using `CTRL+SHIFT+P` and enter the run command `SonarLint: Configure the compilation database for C and C++ analysis`

![image](https://github.com/user-attachments/assets/de36a046-1624-4a28-ad25-ffd96a12f42a)


You can check the official documentation on [how to create a compilation database](https://github.com/SonarSource/sonarlint-vscode/wiki/C-and-CPP-Analysis#generate-a-compilation-database).
