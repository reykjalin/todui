# Changelog

Version scheme is `<year>.<month>.<patch>`, where the `<patch>` may be unused.
For example, the first release in a given month will usually be `<year>.<month>`, e.g. `2024.10`.
If another release is tagged in the same month I would add a patch number, such as `2024.10.1`.

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

### Known issues and missing features

* Tasks cannot be reordered.
* You cannot view your completed tasks through the app.
* No mouse support.
* Multiple selections are not a thing yet.