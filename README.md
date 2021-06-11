# aur-RagingCub

PKGBUILD repository for AUR and personal packages

## using makepkg

Change to the directory where the `PKGBUILD` is saved and run the following command to build the package:

```bash
makepkg
```

If required dependencies ar missing, _makepkg_ will issue a warning before failing.
To build the package and install needed dependencies, add the flag `-s/--syncdeps`:

```bash
makepkg -s
```

Adding the `-r/--rmdeps` flag causes _makepkg_ to remove the make dependencies later.

Once all dependencies are satisfied and the package builds successfully, a package file will be created in the working directory.
To install, use `-i/--install`:

```bash
makepkg -i
```

To clean up leftover files and folders, such as files extracted to the `$srcdir`, add the option `-c/--clean`.
This is useful for multiple builds of the same package or updating the package version, while using the same build folder.
It prevents obsolete and remnant files from carrying over to the new builds:

```bash
makepkg -c
```

All together to build:

```bash
makepkg -src
```

and to install:

```bash
makepkg -i
```

## Generate new checksums

Install `pacman-contrib` and run the following command in the same directory as the PKGBUILD file to generate new checksums:

```bash
updpkgsums
```
