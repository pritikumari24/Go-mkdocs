log Command
The log command displays the commit history of the current branch in a Git-like version control system. It provides information about past commits, such as the commit hash, author, date, and commit message, helping users track changes made in the repository over time.

Purpose of log
The main goal of the log function is to:

Display a list of commits for the current branch.
Provide details about each commit, including the commit hash, author, date, and commit message.
Help users review the history of changes in the repository.
How It Works
Read the HEAD File: The log function first reads the HEAD file to determine the current branch. This file contains a reference to the current branch, such as refs/heads/main.

Read the Current Branch Reference: Once the current branch is determined, the function looks in the .git/refs/heads/ directory to find the latest commit for the branch. This file contains the hash of the latest commit in that branch.

Traverse Commit History: The function starts from the latest commit and follows the parent commit references to traverse the commit history. Each commit points to its parent commit(s), and the function retrieves information about each commit.

Display Commit Information: For each commit, the function displays the following details:

Commit Hash: The unique identifier of the commit.
Author: The name and email of the author.
Date: The timestamp when the commit was created.
Commit Message: The message provided by the user when creating the commit.
Stop at the Root Commit: The process continues until a commit with no parent is found (the root commit), at which point the function stops.

Function Signature
go
Copy code
func log() error
Parameters
The log function does not take any parameters. It works by reading the commit history of the current branch as indicated by the HEAD and refs/heads/<branch> files.

Returns
error: Returns an error if there are issues accessing the repository or reading commit data. If the operation is successful, it returns nil.
Steps in the Implementation
Read the HEAD File: The function first reads the .git/HEAD file to determine which branch is currently checked out.

Read the Current Branch Reference: Using the branch reference, it reads the corresponding commit hash from the .git/refs/heads/ directory.

Read the Commit Object: The function retrieves the commit object from the object database using the commit hash.

Traverse the Commit History: For each commit, the function retrieves the parent commit hash and displays the commit details (hash, author, date, and message). It continues until it reaches the root commit.

Display Commit Details: The function formats and prints each commit's details.