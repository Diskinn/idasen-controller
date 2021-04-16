# Recipes

## Linux

### Albert Launcher

You can use the [albert](https://github.com/albertlauncher/albert) launcher along with two `.desktop` files to allow you to trigger this script from the launcher. An example of a desktop file for this is:

```
[Desktop Entry]
Name=Desk - Sit
Exec=/path/to/idasen-controller --sit
Icon=/home/user/idasen-controller/sit-icon.png
Type=Application
Comment=Lower desk to sitting height.

```

(You can find the `idasen-controller` path with `where idasen-controller`)

## Windows

### Autohotkey

A AutoHotkey script from @aienabled to drive the desk to stand and sit mode by pressing Ctrl+Alt+Shift+Up or Down arrow respectively:

```
;Idasen Desk - Stand
^!+Up::Run "C:\Users\...\Desk - Stand.lnk"

;Idasen Desk - Sit
^!+Down::Run "C:\Users\...\Desk - Sit.lnk"
```

These are shortcut files on the desktop but it's not necessary and could be simple python calls.

### VBScript

A VBScript to drive the desk to stand and sit mode by running shortcuts:

```
Set WshShell = CreateObject("WScript.Shell")
command = "cmd /c idasen-controller --sit"
ReturnCode = WshShell.Run(command, 0, True)
```
Set WshShell = CreateObject("WScript.Shell")
command = "cmd /c idasen-controller --stand"
ReturnCode = WshShell.Run(command, 0, True)
```
