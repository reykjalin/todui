# Todo plain text specification

The `.todo` file format defined by this project is extremely simple.
There are 3 fields in each file: a `title`, `tags`, and `details`.

The `title` is always the first line in the `.todo` file.
A title must contain only 1 line.

The `tags` are always on the second line in the `.todo` file.
The tags must contain only 1 line.
Multiple tags must be separated with a `,`.
Tags must not contain any `,`.

The third line must be empty.
This is to make it easier to read the file without using an application that implements this specification.

The `details` start on the fourth line and extend to the end of the file.
The task details can contain any plain-text formatted text, including markup such as HTML, Markdown, or other.
It is up to the implementation to decide how the details should be saved and rendered.


## Storage

`.todo` files for incomplete tasks should be stored in `$XDG_DATA_HOME/todo` on macOS and Linux and `` on Windows.

The name of the `.todo` file should indicate the way the todo items are ordered on display.
The details on how this is accomplished is left to the implementation.
The reference implementation uses ascending numbers.
The todo at the top of the list is called `1.todo`, the next item might be called `2.todo` (or any other number higher than `1`), and so on.
The only limitations set by the specification is that the file system should be left to sort the items, not the implementation.

`.todo` files for completed tasks should be stored in `$XDG_DATA_HOME/todo/completed`.
Once a task is completed it should be moved to `$XDG_DATA_HOME/todo/completed` and renamed such that it is prefixed by the date it was completed.
A suffix should be added to make sure the `.todo` file name is unique.
The unique suffix is left to the implementation to decide, but should be able to support completing multiple tasks at the exact same time.

If a task is ever "uncompleted" it should be moved back to `$XDG_DATA_HOME/todo` and follow the naming convention outlined in this specification.


