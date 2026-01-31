# Mini Git – Rust Implementation

This project is a simplified implementation of some internal Git commands, written in Rust as part of a learning exercise.

## Implemented Features

The following commands are supported:

- `hash-object -w <file>`  
  Creates a blob object from a file and writes it to `.git/objects`.

- `ls-tree --name-only <tree_sha>`  
  Lists the entries of a Git tree object (names only).

- `write-tree`  
  Recursively creates a tree object from the contents of the current working directory (ignoring `.git`).

- `commit-tree <tree_sha> -p <parent_sha> -m <message>`  
  Creates a commit object from a tree, with a parent commit and a message.

## Project Structure

- All logic is contained in a single `main.rs` file
- Git objects (blob, tree, commit) are written to `.git/objects` using the official Git formats
- Tree entries are sorted alphabetically, matching Git’s behavior

## Assumptions and Simplifications

- All files in the working directory are considered staged
- Only one parent commit is supported
- Author name, email, and timestamp are hardcoded
- Commit messages are limited to a single line

## Build and Run

```bash
cargo build
cargo run -- <command>
