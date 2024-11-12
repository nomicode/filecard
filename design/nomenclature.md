# Nomenclature

*On the choice of "filecard"*

<!--
Temporary editorial notes:
- Use an empty newline before and after lists, code blocks, etc.
- Follow the CMoS when placing hyphens in an compound adjective-noun pair
- Use the `console` syntax for code blocks that show command-line examples
- Command-line examples should one code block per command
- Prefer the use of `&mdash;` instead of a hyphen
-->

This document explains the reasoning behind the choice of "filecard" and outlines how this choice reflects the tool's purpose and design philosophy.

## Introduction

The name "filecard" serves a dual purpose: it works as both the project name and a general-purpose term that communicates the core metaphor of this tool &mdash; an information card that neatly summarizes key information about a file, similar to an index card.

## Core Concept

A filecard is a list of properties about a file, including:

- Regular file system attributes
- Operating-system specific information (e.g., *xattrs* on macOS)
- Embedded metadata information (EXIF, IPTC, XMP, etc.)
- Other key information

Think of it as a neatly organized summary that's easy to read and understand.

The "card" metaphor has proven useful in technical domains &mdash; for instance, the machine learning community uses "model cards" to standardize model information. We apply this same concept to files, creating accessible summaries of file information.

## Design Considerations

### Command-Line Naming Conventions

The name `filecard` was inspired by the `file` command and fits naturally with existing UNIX-like naming conventions. In addition, using a singular uninflected noun lets us build an intuitive command-line interface.

For example, to get the filecard for `my_image.png`:

```console
filecard my_image.png
```

And to get the filetype:

```console
file my_image.png
```

This naming reinforces the concept of a *filecard* as a distinct entity &mdash; a conceptual "card" containing all accessible file data.

### Intuitive Understanding

The term *filecard* builds on familiar concepts from both traditional filing systems and computer science. This helps users quickly grasp the tool's purpose without needing extensive explanation.

### Default Behavior

Like the `file` command, `filecard` follows the principle that basic usage should provide immediately useful results:

- Without parameters: Shows basic file information (like flipping an index card)
- Additional options: Control output verbosity and formatting (e.g., pretty-printing for JSON)

### Subcommands

Treating "filecard" as a noun creates a natural foundation for subcommands.

For example, to get the property `foo`:

```console
filecard get foo my_image.png
```

To set `foo` to `bar`:

```console
filecard set foo bar my_image.png
```

And to delete (or clear) the property:

```console
filecard del foo my_image.png
```

Each subcommand should reinforce the mental model of working with a card that summarizes file information.
