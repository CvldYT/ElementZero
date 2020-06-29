<h1 align="center">
<img src="https://ipfs.io/ipfs/QmYiuQE7WUeawAMTvQf9RUC7wWXb2b1wCFddVBpt6U7e1S/logo.png" width="256px" height="256px" />
</h1>

<a href="https://github.com/Element-0/ElementZero/actions">![status](https://img.shields.io/github/workflow/status/Element-0/ElementZero/CI?style=for-the-badge)</a>
![platform](https://img.shields.io/badge/platform-win--x64%20%7C%20wine--linux--x64-green?style=for-the-badge)
<a href="https://t.me/ezloader">![Telegram](https://img.shields.io/badge/telegram-ezloader-%232CA5E0?style=for-the-badge&logo=Telegram)</a><br>
<a href="https://github.com/Element-0/ElementZero/releases/latest">![Latest Tag](https://img.shields.io/github/v/tag/Element-0/ElementZero?label=LATEST%20TAG&style=for-the-badge)![GitHub Releases (by Asset)](https://img.shields.io/github/downloads/Element-0/ElementZero/latest/total?style=for-the-badge)</a><br>

Run the windows version of BDS in linux with Mod support (Yes, this can also be run on windows)

## Installation and usage instructions :point_right: [Wiki](https://github.com/Element-0/ElementZero/wiki)

## Features

0. Compatiable with the official BDS
1. Supports behavior pack with custom item/recipes/scripts (* vanilla server *does* support them, but its disabled in code.)
2. Can be run in windows nativly as well as in linux (with wine)
3. Native modding support
4. /transferserver is back!

## FAQ

Q: Why not use a native linux version?<br>
A: The windows version has noticeable performance improvements, even when running under wine.

Q: Can the Windows version run directly under wine?<br>
A: No, because Microsoft uses Chakra.dll, which contains a lot of references to private dlls. (It also prevents you from running on systems prior to Windows 10.)

Q: How does it work?<br>
A: I created a dll that simply forwards all APIs to the open source version of Chakra engine i.e. ChakraCore. And this version can run directly under wine.


## [WIN] Easy Beta Install (Use latest Action) <-- Sorta like a beta
Betas can be buggy, but provide more features then standard releases.

0. Make a GitHub Account.
2. Download the action [here](https://github.com/Element-0/ElementZero/actions)
3. Click the newest action that is complete
4. Download DIST file (Just click it)
5. Download newest release of BDS Softwear from mojang [here](https://www.minecraft.net/en-us/download/server/bedrock/)
6. Run the BDS server at least once after extraction.
7. Copy DIST.ZIP file contents into the BDS folder (Where you extracted BDS Softwear to)
8. Run bedrock_server_mod.exe and enjoy!



## [WIN] Easy Release Install
Releases are stable, but lack the features present in the action or beta.

0. Download newest release of BDS Softwear from mojang [here](https://www.minecraft.net/en-us/download/server/bedrock/)
1. Download EZ Softwear (Clone, then download as ZIP)
2. Run the BDS server at least once after extraction.
3. Copy ElementZero-master.ZIP file contents into the BDS folder (Where you extracted BDS Softwear to)
4. Run bedrock_server_mod.exe and enjoy!

## Build and install (optional)

0. Download bedrock dedicated server binary
1. Generate bedrock_server_mod.lib (see below)
2. Install vcpkg and install dependencies (see below)
3. Build it with Visual Studio 2019 (or use CMake manually see .githubn/workflows/ci.yaml)
4. Copy Dist/* to bds folder (or use [symlink](https://blogs.windows.com/windowsdeveloper/2016/12/02/symlinks-windows-10/))
5. Run bedrock_server_mod.exe



## Visual Studio 2019 workloads and components

0. Microsoft.VisualStudio.Workload.NativeDesktop
1. Microsoft.VisualStudio.Workload.ManagedDesktop
2. Microsoft.VisualStudio.Component.VC.Tools.x86.x64
3. Microsoft.VisualStudio.Component.Windows10SDK.18362
4. Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Llvm.Clang



## How to use vcpkg

0. Install vcpkg in source tree `cd vcpkg && bootstrap-vcpkg.bat`
1. Install dependencies by `vcpkg\vcpkg.exe install @vcpkg.txt` (run in $(SolutionDir))



## How to get bedrock_server_mod.lib

0. Download and install [EatPdb](https://github.com/CodeHz/EatPdb)
1. Copy $(SolutionDir)\eatpdb.yaml to bds folder
2. Run `eatpdb exec eatpdb.yaml`
3. Open `x64 Native Tools Command Prompt for VS 2019`, then run `lib /def:bedrock_server_mod.def /machine:x64`
4. Copy bedrock_server_mod.lib, addition_symbols.db, bedrock_server_mod.exe to $(SolutionDir)Lib\

## LICENSE

GPLv3
