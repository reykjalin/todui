# Todui

A filesystem based TUI app for managing todo lists.
The [`.todo` file specification](./SPECIFICATION.md) was created to fit this specific implementation.

The TUI is fully mouse aware so you can use both the keybindings listed below or the mouse to navigate the TUI.

![Todui task list at commit hash `a54d31b889781325677de1901731cd6b5e6b9aed`](./screenshots/task-list-a54d31b889781325677de1901731cd6b5e6b9aed.webp)

## CLI Help

```sh
$ todui --help
Usage: todui [storage_folder]

Positional options:

  [storage_folder]  The path to where todui data should be stored.
                    Defaults to ~/.local/share/todo/ when no path is provided.

General options:

  -h, --help     Print fn help
  -v, --version  Print fn help
```

The `storage_folder` positional argument can be used to change where tasks are stored.
The default path is `~/.local/share/` and tasks will be saved in `~/.local/share/todo/`.
If you'd like to, for example, have the tasks stored in `~/.config` you can run `todui ~/.config`.
If you do, tasks will be saved in `~/.config/todo/`.

This is very helpful for testing, but also if you'd like to maintain distinct lists for different
purposes.
For example, a complete separation between work and personal lists.
You could do the same with tags, but in that case the storage is the same for both.


## Keybindings

### Task List

| Key | Action |
|:---:|:---:|
| <kbd>j</kbd> / <kbd>down</kbd> | Move selection down |
| <kbd>k</kbd> / <kbd>up</kbd> | Move selection up|
| <kbd>g</kbd> | Move selection to top |
| <kbd>G</kbd> | Move selection to bottom |
| <kbd>J</kbd> / <kbd>shift+down</kbd> | Move selected task down |
| <kbd>K</kbd> / <kbd>shift+up</kbd> | Move selected task up |
| <kbd>l</kbd> / <kbd>enter</kbd> | Open task details view for the selected task |
| <kbd>A</kbd> | Create new task, appended to the bottom of the list |
| <kbd>e</kbd> | Edit selected task |
| <kbd>c</kbd> | Complete selected task |
| <kbd>r</kbd> | Reload task list |
| <kbd>f</kbd> | Open filter view |
| <kbd>H</kbd> | Hide the tags column |
| <kbd>tab</kbd> | Open completed task list view |

### Completed Task List

| Key | Action |
|:---:|:---:|
| <kbd>j</kbd> / <kbd>down</kbd> | Move selection down |
| <kbd>k</kbd> / <kbd>up</kbd> | Move selection up|
| <kbd>g</kbd> | Move selection to top |
| <kbd>G</kbd> | Move selection to bottom |
| <kbd>l</kbd> / <kbd>enter</kbd> | Open task details view for the selected task |
| <kbd>r</kbd> | Reload task list |
| <kbd>f</kbd> | Open filter view |
| <kbd>H</kbd> | Hide the tags column |
| <kbd>tab</kbd> | Open task list view |

### Task Details

| Key | Action |
|:---:|:---:|
| <kbd>h</kbd> / <kbd>esc</kbd> | Go back to previous view |
| <kbd>e</kbd> | Edit task |
| <kbd>c</kbd> | Complete task |

### Task Filter

| Key | Action |
|:---:|:---:|
| <kbd>enter</kbd> | Save filter. Empty filter results in no filtering being applied |


## Build instructions

This app is written in Zig and libvaxis and uses the Zig Build system.
To build, simply download Zig and run `zig build run`.
Dependencies will automatically be fetched and built for your system.

To make a release build run `zig build -Doptimize=ReleaseSafe`.
You'll find the built release executable in `./zig-out/bin/todui`.

## Screenshots

![Todui task list at commit hash `a54d31b889781325677de1901731cd6b5e6b9aed`](./screenshots/task-list-a54d31b889781325677de1901731cd6b5e6b9aed.webp)
![Todui completed tasks at commit hash `a54d31b889781325677de1901731cd6b5e6b9aed`](./screenshots/completed-tasks-a54d31b889781325677de1901731cd6b5e6b9aed.webp)
![Todui task details at commit hash `a54d31b889781325677de1901731cd6b5e6b9aed`](./screenshots/task-details-a54d31b889781325677de1901731cd6b5e6b9aed.webp)
