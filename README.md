# VS Code `.csproj` Extension

This extension will prompt you to add files to the .csproj file used by Visual Studio. This is useful if you work in a team that uses both VS Code and Visual Studio.

When you switch to or save a file not in the nearest `.csproj` up the file system tree, you will prompted.

![Prompt](img/demo-prompt.png "Prompt")

Choosing "Not Now" will add an item to the status bar and stop asking you while you have the file open.

![StatusBar](img/demo-status-bar.png "Status Bar")

You can add a file to csproj via the command palette:

![Command](img/demo-command.png "Command Palette")

Or via the context menu in the file explorer:

![Context](img/demo-context-menu.png "Context Menu")

## Extension Settings

This extension contributes the following settings:

* `csproj.enable`: Enable/disable this extension.
* `csproj.itemType`: Type of XML element to put in the csproj file. Defaults to `"Content"`.
* `csproj.includeRegex`: Regular expression to match files you want to add to csproj.
* `csproj.excludeRegex`: Regular expression to exclude files you do not want to add to csproj.

If a file matches `includeRegex` *and* `excludeRegex`, it will be excluded.

The regular expressions will prevent this extension from prompting for action, but it intentionally will not
prevent you from adding via the command palette or a context menu.

## Release Notes

### 0.0.1

Initial release.

Features:

* Support adding to nearest csproj by walking up the file system tree from current file.
* Status bar item for items temporarily ignored from csproj.
* Persistent ignore list for items not to be added to csproj.
* Caching to prevent excessive csproj reads.

### 0.1.0

Features:

* Support enable/disable configuration.
* Support custom item types. (Global setting only)

### 0.1.1

Fixes:

* Fix a caching bug when using multiple csproj files.

### 0.1.2

Fixes:

* Fix configuration autocompletion in settings files.

### 0.2.0

Features:

* Context menu item in file explorer.
* `includeRegex` and `excludeRegex`.

### 0.2.1

Fixes:

* Fix configuration for editor context menu.
