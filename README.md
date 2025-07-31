A guide on how to compile [SourceMod](https://www.sourcemod.net/about.php) plugins.

SourceMod plugins are custom scripts or addons created to enhance and modify the functionality of game servers that run on the Source engine.

The programming language associated with SourceMod plugin's source code is [SourcePawn](https://github.com/alliedmodders/sourcepawn). The file extension for SourcePawn is `sp`.

Compiling SourceMod plugins is quite easy and will be explained below.

[**View Guide On TMC (Recommended Due To Better Formatting)**](https://blog.moddingcommunity.com/how-to-compile-sourcemod-plugins/)

## Table Of Contents
* [Downloading SourceMod](#downloading-sourcemod)
* [Compiling SourceMod Plugins](#compiling-sourcemod-plugins)
  * [Windows](#windows)
    * [Windows File Explorer](#windows-file-explorer)
    * [Command Line](#command-line)
  * [Linux](#linux)
* [Additional Command Line Options](#additional-command-line-options)
* [Include Files](#include-files)
* [Conclusion](#conclusion)

## Downloading SourceMod
Refer to the following guide on how to download and extract SourceMod. You do **not** need to install SourceMod onto your server to build plugins.

https://blog.moddingcommunity.com/how-to-install-update-sourcemod-metamod/

After extracting the SourceMod files, go to the `addons/sourcemod/scripting` directory on Linux (or `addons\sourcemod\scripting` folder on Windows).

## Compiling SourceMod Plugins
Compiling SourceMod plugins is usually quite easy, especially on Windows.

### Windows
#### Windows File Explorer
If you want to quickly compile plugins, you can drag and drop the plugin's source code file into the `compile.exe` executable located in the `scripting` folder. A Command Prompt window will open and you'll see the output of the build. If the build was successful, you'll see the built plugins inside of the `compiled` folder. Built SourceMod plugins typically have the `smx` file extension.

![Drag And Drop GIF](https://github.com/modcommunity/how-to-compile-sourcemod-plugins/raw/main/images/gui-dnd.gif)

While this method is quick and easy, the command line method explained below includes **more options** you can set.

#### Command Line
If you want to compile plugins using through the command line using Command Prompt or PowerShell, you will first need to launch a terminal and change to the scripting folder.

Next, you'll want to use the `spcomp.exe` or `spcomp64.exe` (for 64-bit support) executables to compile the plugins.

Here is a basic command that compiles a plugin.

```powershell
.\spcomp.exe <Plugin File Name With Extension>
```

For example, if we want to compile the included `basechat` plugin, we'd use the following command.

```powershell
.\spcomp.exe basechat.sp
```

## Linux
To compile SourceMod plugins through a Linux terminal, you may use a similar process to the command line method on Windows explained above. You will need to either use the `spcomp` or `spcomp64` (for 64-bit support) executables to compile the plugins.

Here is a basic command that compiles a plugin.

```bash
./spcomp <Plugin File Name With Extension>
```

For example, if we want to compile the included `basechat` plugin, we'd use the following command.

```bash
./spcomp basechat.sp
```

If the build was successful, you'll see the new built plugin file in the same directory as the source code (`scripting/`).

## Additional Command Line Options
As stated above, compiling plugins through the command line allows you to set additional options. Here is the help menu output which provides a list of flags and arguments you may set.

```
SourcePawn Compiler 1.11.0.6969
Copyright (c) 1997-2006 ITB CompuPhase
Copyright (c) 2004-2021 AlliedModders LLC

Usage: ./spcomp [options] <filename> [filename...]

optional arguments:
  --show-stats              Show compiler statistics on exit.
  -D                        Active directory path
  --active-dir=ACTIVE_DIR
  -e                        Error file path
  --error-file=ERROR_FILE
  -E, --warnings-as-errors  Treat warnings as errors
  -h, --show-includes       Show included file paths
  -z
  --compress-level=COMPRESS_LEVEL
                            Compression level, default 9 (0=none, 1=worst,
                            9=best)
  -t, --tabsize=TABSIZE     TAB indent size (in character positions,
                            default=8)
  -v, --verbose=VERBOSE     Verbosity level; 0=quiet, 1=normal, 2=verbose
  -p, --prefix=PREFIX       Set name of "prefix" file
  -o, --output=OUTPUT       Set base name of (P-code) output file
  -O, --opt-level=OPT_LEVEL
                            Deprecated; has no effect
  -i, --include=INCLUDE     Path for include files
  -w, --warning=WARNING     Disable a specific warning by its number.
  -;, --require-semicolons  Require a semicolon to end each statement.
  --syntax-only             Perform a dry-run (No file output) on the input
  --use-stderr              Use stderr instead of stdout for error messages.
  --no-verify               Disable opcode verification (for debugging).
  sym=val                   Define constant "sym" with value "val".
  sym=                      Define constant "sym" with value 0.
```

For example, on Linux, if want the successfully built `basechat` plugin to go inside the `compiled/` directory, we'd use the following command(s).

```bash
# Make sure compiled directory is made.
mkdir -p compiled

# Output: compiled/basechat.smx
./spcomp -o compiled/basechat basechat.sp
```

## Include Files
There are many published SourceMod plugins that contain include files with the `inc` file extension. These files need to go into the `include/` directory/folder. Otherwise, the plugins will likely fail to compile.

Additionally, you can use the `-i` flag when compiling through the command line to include directories and folders outside of the default `include` directory and folder.

## Conclusion
That's all! You should now know how all methods on **compiling** SourceMod plugins.

If you have any questions or feedback regarding this guide, please reply to its forum topic [here](https://forum.moddingcommunity.com/t/how-to-compile-sourcemod-plugins/502)! This guide will be worked and improved on over time.

Join our [Discord server](https://discord.moddingcommunity.com)!