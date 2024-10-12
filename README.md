# Todo

A filesystem based TUI app for managing todo lists.
The [`.todo` file specification](./SPECIFICATION.md) was created to fit this specific implementation.

![Todo TUI at commit hash `f685a6b9eb66224b8308db12948638819a1a56f8`](./screenshots/task-list-f685a6b9eb66224b8308db12948638819a1a56f8.webp)


## Keybindings

### Task List

| Key | Action |
|:---:|:---:|
| <kbd>j</kbd> / <kbd>down</kbd> | Move selection down |
| <kbd>k</kbd> / <kbd>up</kbd> | Move selection up|
| <kbd>g</kbd> | Move selection to top |
| <kbd>G</kbd> | Move selection to bottom |
| <kbd>l</kbd> / <kbd>enter</kbd> | Open task details view for the selected task |
| <kbd>A</kbd> | Create new task, appended to the bottom of the list |
| <kbd>e</kbd> | Edit selected task |
| <kbd>c</kbd> | Complete selected task |
| <kbd>r</kbd> | Reload task list |
| <kbd>f</kbd> | Open filter view |

### Task Details

| Key | Action |
|:---:|:---:|
| <kbd>h</kbd> / <kbd>esc</kbd> | Go back to task list view |
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
You'll find the built release executable in `./zig-out/bin/todo`.
