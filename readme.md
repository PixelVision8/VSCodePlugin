# PV8 VSCode Debugger

This project is based on the [MoonSharp VSCode Debugger](https://github.com/moonsharp-devs/moonsharp/tree/master/src/moonsharp-vscode-debug)

This is an extension to allow debugging of Lua scripts running inside Pixel Vision 8.

## Features supported

* Connect to the currently running game's Lua script
* Supports breakpoints, watches, local variables, `self` inspection
* Call stack, with visualization of current coroutine
* Watches can contain free formed expressions, as long they are side-effects free
* Inspection of values including internal ids and table contents
* Print statements are displayed in the debug console


## Features not supported

* Editing of values not supported
* No checks are made for file contents changes
* Due to how vscode works, token-based breakpoints are not supported


## How to use

1) Open Pixel Vision 8's Workspace Folder (located in your computer's User directory)

2) Create a new launch.json file in a `.VSCode` folder at the root of the Workspace directory with the following:

```
{
    "version": "0.2.0",
    "debugServer" : 41912,
    "configurations": [
        {
            "name": "PV8 Debugger Attach",
            "type": "pv8-debug",
            "request": "attach",
            "debugServer": 1985
        }
    ]
}
```

3) Hold down the shift key while a game loads to begin the countdown for connecting the debugger.

4) In VS Code, select Debug -> PV8 Debugger then switch back over to Pixel Vision 8

5) Once the debugger is connected, you should see a debug icon in the title bar

6) When the game loads up, you should be able to trigger break points to inspect the code that is currently running. By default, the debugger will break on Init().

7) Type !scripts to display all of the script files that are currently loaded
