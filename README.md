# File Management System

A simple file management system implemented in C that allows you to create, manage, and store files on a simulated disk. This project showcases the basic principles of a file system, including file creation, allocation, and management.

## Overview

A file system is a collection of files and directories organized in a hierarchical structure. This file management system is designed with the following constraints:

- Supports up to 100 files.
- Maximum file size is 10 KB, spanning up to ten blocks.
- Maximum filename length is 100 characters.
- Each data block is 4 KB (4096 bytes).
- Supports a single directory structure (only files, no subdirectories).

## Features

- File creation and allocation of data blocks.
- Tracking of used and free data blocks.
- Basic file management: create, read, update, delete.

## Structures

### `struct file`

- Provides information about a specific file.
- Contains the filename, data blocks, and usage information.

### `struct superBlock`

- Stores metadata about the disk and its blocks.
- Manages the bitmap of free and used blocks.

### `struct directory`

- Manages the file allocation table (File Table).
- Sets limits on file sizes and number of files.

### `struct dataBlock`

- Contains the actual data for filled blocks.


## System Calls and Description

### 1. File system module initialization (mount function)

- **Prototype:** `void mount();`
- **Function Description:**
  - This function initializes the data structures and resources used by the file system.
  - If the disk is already formatted, it mounts the disk (`FileSystem.data`).
  - The choice to format or use the existing disk is given to the user.

### 2. Create a file

- **Prototype:** `void createFile();`
- **Function Description:**
  - Finds space in the file allocation table for the new file.
  - Checks if the given file name already exists.
  - Initializes the block list for the new file.
  - Takes user input for file data and updates block usage and structures.
  
### 3. Read a file

- **Prototype:** `void readFile();`
- **Function Description:**
  - Takes a file name as user input.
  - Searches for the file and prints filled blocks' data.

### 4. Edit a file

- **Prototype:** `void editFile();`
- **Function Description:**
  - Takes a file name as user input.
  - Searches for the file and provides editing options.
  - Allows editing or removing blocks.
  - Updates free blocks, filled blocks, and structures.

### 5. Delete a file

- **Prototype:** `void deleteFile();`
- **Function Description:**
  - Takes a file name as user input.
  - Searches for the file and deletes it.
  - Updates free blocks, data blocks, and structures.

## Getting Started

To use this file management system, follow these steps:

1. Clone this repository.
2. Compile the source code using a C compiler.
3. Run the compiled executable.
4. Follow the on-screen instructions to create, manage, and access files.
---

We hope this README helps you get started with understanding and using our simple file management system.
