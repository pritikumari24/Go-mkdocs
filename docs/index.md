

# Git-like Version Control System Documentation

Welcome to the documentation for the **Git-like Version Control System** built in Go! This system emulates the core functionalities of Git, allowing you to manage file changes, create commits, track history, and perform various version control tasks. Below is a comprehensive guide to all the available features, objects, and commands in this system, with links to detailed explanations for each component.

### Table of Contents

1. **[Setup](setup.md)**
   - **Purpose**: Instructions on how to set up and install the Git-like version control system on your local machine.
   - **What You’ll Learn**: Prerequisites, installation steps, and how to initialize a new repository.

2. **[Object Structure](object_structure.md)**
   - **Purpose**: Provides an overview of the fundamental objects (blobs, trees, commits, and tags) used in this system.
   - **What You’ll Learn**: How objects are stored, referenced, and their structure within the system.

3. **[Tree Objects](trees.md)**
   - **Purpose**: Explains the role of tree objects in organizing the directory structure.
   - **What You’ll Learn**: How tree objects represent directories and link to files (blobs) and other subdirectories (trees).

4. **[Blobs](blobs.md)**
   - **Purpose**: Describes blob objects, which store the contents of files.
   - **What You’ll Learn**: How blobs are created from file contents and how they are hashed and stored.

5. **[Commits](commits.md)**
   - **Purpose**: Detailed explanation of commit objects and their role in storing history and metadata about changes.
   - **What You’ll Learn**: How commit objects link to tree objects and contain metadata like timestamps and author information.

6. **[Add](add.md)**
   - **Purpose**: Explains the `add` command used to stage changes for committing.
   - **What You’ll Learn**: How to add files and directories to the staging area before committing them to the repository.

7. **[Cat File](cat_file.md)**
   - **Purpose**: Details the `cat_file` command that allows you to view the contents of any object (blobs, trees, commits).
   - **What You’ll Learn**: How to access and view the raw content of stored objects in the repository using their hashes.

8. **[Checkout](checkout.md)**
   - **Purpose**: Describes how to use the `checkout` command to switch between commits or versions of files.
   - **What You’ll Learn**: How to navigate between different commit histories and restore specific files or directories.

9. **[Commit](commit.md)**
   - **Purpose**: Explains the process of creating a new commit and the structure of commit objects.
   - **What You’ll Learn**: How to save changes, link them to a commit history, and store commit metadata (author, date, commit message).

10. **[Hash Object](hash_object.md)**
    - **Purpose**: Describes the `hash_object` command that computes and returns the hash of an object.
    - **What You’ll Learn**: How objects are hashed to ensure uniqueness and how this process is integral to version control.

11. **[Init](init.md)**
    - **Purpose**: Explains the `init` command that initializes a new repository.
    - **What You’ll Learn**: How to set up a new version control repository, including the creation of necessary configuration files and directories.

12. **[Log](log.md)**
    - **Purpose**: Details how to view the commit history of the repository using the `log` command.
    - **What You’ll Learn**: How to navigate through commit logs, view past changes, and analyze project history.

13. **[LS Tree](ls_tree.md)**
    - **Purpose**: Describes the `ls_tree` command that lists the contents of a tree object.
    - **What You’ll Learn**: How to display the contents of directories (tree objects) at specific points in history.

14. **[Status](status.md)**
    - **Purpose**: Explains the `status` command, which shows the current state of the repository, including staged and unstaged changes.
    - **What You’ll Learn**: How to check for modified, deleted, or new files and understand their status in relation to the repository.

---

### Getting Started

1. **[Setup](setup.md)**: Before you begin using the system, ensure you have completed the installation process outlined in the Setup guide. This section provides all the prerequisites, such as the Go runtime and setting up a Git-like repository.
   
2. Once you have your repository initialized, you can explore key functionality, such as:
   - **[Adding Files](add.md)**: Stage files for commit.
   - **[Committing Changes](commit.md)**: Save your changes to the repository with commit history.
   - **[Viewing Status](status.md)**: Track changes in your working directory and staging area.

---

### Core Features

- **Version Control**: Track changes made to files and directories over time, supporting operations like commit, revert, and branch management.
- **Object Management**: Learn how different objects (blobs, trees, commits) interact with each other to represent files, directories, and changes.
- **Commit History**: View your project’s commit history and understand how past changes relate to the current state of the repository.
- **File Operations**: Add files to the staging area, check out different versions, and commit changes to track project evolution.

### Advanced Features

- **Log and History Tracking**: The **[Log](log.md)** command helps you analyze and explore the commit history.
- **Tree Management**: Explore and manage directory structures using tree objects, which are explained in the **[Tree Objects](trees.md)** and **[LS Tree](ls_tree.md)** documents.

---

This **index.md** serves as a central hub to navigate the documentation for your Git-like version control system project. By following the links, you can gain in-depth insights into each command, object type, and how they function within the system. Whether you're adding files, committing changes, or managing the object structure, this documentation will help guide you through every step.

