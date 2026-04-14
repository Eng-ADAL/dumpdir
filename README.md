# dumpdir

A small Linux and macOS command-line tool for exporting a directory tree and file contents in a controlled way.

It is designed for situations where you want to share project context without handing over the whole filesystem.

## Why it exists

When working with AI tools, support requests, or remote debugging, it is often useful to export:

- the directory structure
- the file list
- selected file contents
- machine-readable snapshots

`dumpdir` aims to do that in a safe and predictable way.

## Current idea

The tool starts as a Bash implementation and will grow over time.

## Behaviour

The default output is intended to be useful both for humans and for tools.

Example:

```bash
dumpdir
```

This prints the directory tree first, then dumps text files with clear separators.

Examples of pipe usage:

```bash
dumpdir | less
dumpdir | clipcopy
dumpdir > dump.txt
```

## Safety goals

`dumpdir` is being built with a few rules in mind:

* do not dump private keys or obvious secrets
* skip common build and cache directories
* ignore binary files
* keep output deterministic
* keep the interface simple enough for automation

The aim is to provide a controlled export layer for AI tools, not raw filesystem access.

## Repository layout

```text
dumpdir/
├── bin/
│   └── dumpdir
├── install.sh
├── LICENSE
└── README.md
```

## Development status

This project is under active development.

The first goal is a working Bash version that can be used safely and extended later.

## Licence

GPLv3
