# Useful shell commands

## compress all dump files in parallel

LAMMPS-style files are often quite large and can take up a lot of space. To recursively compress all dump files in parallel, run:

```bash
find . -name "*.dump" -type f -exec pigz {} +
```

This will find all files with a `.dump` prefix in the current directory (including those in subdirectories) and compress it using `pigz`, which is, crudely, just a resource-aware `gzip`, i.e. it will run compression algorithms in parallel.

## DOS to Unix

Running into an error about some illegal character `^M`? This is likely an artifact from editing the file on Windows. There's a handy command for converting DOS (Windows's format) to Unix:

```bash
dos2unix file.txt
```