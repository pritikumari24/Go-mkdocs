ls_tree Command
The ls_tree command displays the contents of a commit as a hierarchical list, showing files and directories at a specific commit or tree object. It allows users to see the structure of the repository at a particular point in time, displaying the tree of files, directories, and their respective object types (blob or tree).

Purpose of ls_tree
The main goal of the ls_tree function is to:

Display the contents of a specific commit or tree object.
Provide a structured view of files and directories in a commit.
Help users navigate and inspect the content at a particular point in the repository's history.
How It Works
Read the Tree Object: Each commit in a Git repository points to a tree object, which represents the file structure at that point in time. The ls_tree function reads the tree object from the object database using the commit hash or tree hash provided.

Parse the Tree Object: A tree object contains entries that point to other tree objects (subdirectories) or blob objects (files). The function parses these entries to build the directory structure.

Display Tree Structure: The function recursively traverses the tree object, displaying each file and directory in the format:

tree <hash> for directories.
blob <hash> for files.
Handle Nested Directories: If a directory contains subdirectories or files, the function recursively lists the contents, building a tree-like structure.

Support for Specific Commit: The function can display the tree structure for any commit. If no commit is specified, it shows the tree for the current commit (the latest commit in the current branch).

Function Signature
go
Copy code
func lsTree(commitHash string) error
Parameters
commitHash: The hash of the commit or tree object to list the contents of. If empty, it defaults to the latest commit in the current branch.
Returns
error: Returns an error if there are issues accessing the tree object, parsing it, or displaying the contents. If the operation is successful, it returns nil.
Steps in the Implementation
Read the Commit Object: The function first retrieves the commit object corresponding to the provided commitHash. This commit object contains a reference to the tree object.

Get the Tree Hash: The commit object includes the tree hash, which points to the tree object that represents the file structure at that commit.

Retrieve the Tree Object: Using the tree hash, the function fetches the tree object from the object database.

Parse and Display the Tree: The tree object is parsed to extract its entries, which may be files (blobs) or directories (other tree objects). The function recursively lists these entries, showing the hierarchical structure of files and directories.