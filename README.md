# Loaf
Build your [Crumb](https://github.com/liam-ilan/crumb) programs as standalone binaries 🍞.

## What is this?
Loaf is a Crumb program, that compiles other Crumb programs into standalone binaries. This is done by injecting the the source of your crumb programs into the Crumb interpreter's source code, compiling your scripts with the Crumb runtime.

## Getting Started
> Crumb is built for POSIX compliant systems, and utilizes `ioctl.h` and `unistd.h`. To use Crumb on windows, either use WSL, or use a Linux container.

First, build crumb.
```bash
chmod +x build-crumb.sh && ./build-crumb.sh
```

You can now try to run Loaf on itself, bootstrapping it's own binary.
```bash
./crumb ./loaf.crumb ./loaf.crumb ./loaf
```

This will create a `loaf` binary you can invoke from anywhere, on any crumb program.
```bash
./loaf ENTRY_POINT.crumb OUTPUT_BINARY_PATH
```

Eg. to bootstrap Loaf again, you can run
```bash
./loaf ./loaf.crumb ./loaf2
```

You can also control the version of Crumb to use.
```bash
./loaf ENTRY_POINT.crumb OUTPUT_BINARY_PATH TAG
```

> Loaf will recursively traverse any directory it is run from, and make any file that ends with `.crumb` available to the `use` function.

## Crumb
Built for and with the Crumb Programming language: https://github.com/liam-ilan/crumb.

## Author
- Built by [Liam Ilan](https://www.liamilan.com/)