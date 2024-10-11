# Todo

A filesystem based TUI app for managing todo lists.
The [`.todo` file specification](./SPECIFICATION.md) was created to fit this specific implementation.

## Build instructions

This app is written in Zig and libvaxis and uses the Zig Build system.
To build, simply download Zig and run `zig build run`.
Dependencies will automatically be fetched and built for your system.

To make a release build run `zig build -Doptimize=ReleaseSafe`.
You'll find the built release executable in `./zig-out/bin/todo`.
