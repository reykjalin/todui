# Todui

> **Note**
>
> I consider Todui to be mostly feature complete at this point.
> Future development will be slow and mostly consist of minor quality-of-life improvements or fixing little annoyances and bugs that come up.

A filesystem based TUI app for managing todo lists.
The [`.todo` file specification](./SPECIFICATION.md) was created to fit this specific implementation.

The TUI is fully mouse aware so you can use both the keybindings listed below or the mouse to navigate the TUI.

![Todui task list at commit hash `2d2f133904a97292c5ac50917e7ed175fb71a569`](./screenshots/task-list-2d2f133904a97292c5ac50917e7ed175fb71a569.webp)


## Installation instructions

### Download binaries

The tags and releases have binaries available for macOS (arm64 and x86_64), Linux (arm64 and x86_64), and Windows (x86_64).
You can download a pre-built binary for your system from there.
The binaries are static so you can store them wherever you like and run them from there.

### Build from source

1. Clone this repository or download the source some other way.
2. Run `zig build -Doptimize=ReleaseSafe --prefix=~/.local` and the `todui` executable will be installed in `~/.local/bin/todui`.
    * If you build without the `--prefix=~/.local` parameter the binary will be in `./zig-out/bin/todui`. It's static so you can move it wherever you want.


## CLI Help

```sh
$ todui --help
Usage: todui [storage_folder]

Positional options:

  [storage_folder]  The path to where todui data should be stored.
                    Defaults to ~/.local/share/todo/ when no path is provided.

General options:

  -h, --help     Print todui help
  -v, --version  Print todui version
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


## Dev build instructions

This app is written in Zig and libvaxis and uses the Zig Build system.
To build, simply download Zig and run `zig build run`.
Dependencies will automatically be fetched and built for your system.

To make a release build run `zig build -Doptimize=ReleaseSafe`.
You'll find the built release executable in `./zig-out/bin/todui`.


## Screenshots

![Todui task list at commit hash `2d2f133904a97292c5ac50917e7ed175fb71a569`](./screenshots/task-list-2d2f133904a97292c5ac50917e7ed175fb71a569.webp)
![Todui completed tasks at commit hash `2d2f133904a97292c5ac50917e7ed175fb71a569`](./screenshots/completed-tasks-2d2f133904a97292c5ac50917e7ed175fb71a569.webp)
![Todui task details at commit hash `2d2f133904a97292c5ac50917e7ed175fb71a569`](./screenshots/task-details-2d2f133904a97292c5ac50917e7ed175fb71a569.webp)
