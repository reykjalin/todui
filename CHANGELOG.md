# Changelog

Version scheme is `<year>.<month>.<patch>`, where the `<patch>` may be unused.
For example, the first release in a given month will usually be `<year>.<month>`, e.g. `2024.10`.
If another release is tagged in the same month I would add a patch number, such as `2024.10.1`.

## 2024.11

### Features

* Scrolling in the active and complete task list 🎉.
* An optional positional argument to control where tasks are stored. Use as `todui <path>`.

### Known issues and missing features

* Multiple selections are not a thing yet.
* The currently active filter is not displayed.
* You can't scroll by clicking and dragging the scroll bar, or clicking the scroll area.
* The scrollbar doesn't always scroll all the way down, sometimes there
  is a 1 cell gap between the scrollbar and the scroll down button.
* Selecting a task to view details or completing it after scrolling will
  select the wrong task.
* You can't select and copy text in the details view.


## 2024.10

### Features

* Create new tasks through whichever editor is defined in your `$EDITOR` environment variable.
    * This defaults to `nano` if there is no `$EDITOR` defined.
    * New tasks are stored in `$XDG_DATA_HOME/todo/`.
* Tasks can be completed.
    * Completed tasks are stored in `$XDG_DATA_HOME/todo/completed/`.
* Tasks can be edited with your `$EDITOR` of choice, defaults to `nano`.
* Filter tasks by tag. Filter input is currently free-form.
* Task details - title, tags, and details - can be viewed.
* Toggle the visibility of the tags column.
* Reorder tasks in the task list.
* View the tasks you've completed before, with the newest at the top.
* Full mouse support for most actions.

### Known issues and missing features

* Multiple selections are not a thing yet.
* Scrolling in long task lists has not been implemented.
* The currently active filter is not displayed.
