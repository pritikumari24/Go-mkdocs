hash_object Function
The hash_object function is responsible for calculating the hash of a given object (such as a file or a directory) in the Git-like version control system. The hash is used to uniquely identify objects in the object database, ensuring that objects can be retrieved and referenced consistently throughout the system.

Purpose of hash_object
The main goal of the hash_object function is to:

Compute a SHA-1 hash of the content of an object (file or directory).
Store the object’s content in the object database.
Ensure that the same content results in the same hash, enabling version control and integrity checking.
How It Works
Object Types: The function is designed to handle different types of objects, including:

Blob Objects: Represent the content of a file.
Tree Objects: Represent directories and the files within them.
Commit Objects: Represent commit information, including parent commit references, tree object hashes, and commit metadata.
Input Content: The function accepts content, either from a file or a directory, and prepares it for hashing. For files, this involves reading the file content. For directories, the function creates a representation of the directory’s structure.

Object Formatting: Before calculating the hash, the content is formatted according to Git’s object model. This includes adding a header with the object type and size, followed by the raw object content.

SHA-1 Hashing: The formatted object content is passed through the SHA-1 hashing algorithm to generate a 40-character hash.

Storing the Object: The object (if new) is stored in the object database, using its hash as the filename.

Function Signature
go
Copy code
func hashObject(objectType string, content []byte) (string, error)
Parameters
objectType (string): The type of the object being hashed. Common types include "blob" for file content, "tree" for directories, and "commit" for commit data.
content ([]byte): The raw content of the object to be hashed. This could be the contents of a file, directory, or commit information.
Returns
string: The 40-character SHA-1 hash of the object.
error: Returns an error if the object type is invalid or if there is an issue with the hashing process.
Steps in the Implementation
Validate Object Type: The function checks if the provided objectType is valid (either "blob", "tree", or "commit").

Prepare the Content:

For a blob, the content is simply the raw file content.
For a tree, the content includes the file names and their corresponding object hashes.
For a commit, the content includes the commit message, author, timestamp, parent commit, and the tree object hash.
Format the Content: The content is prefixed with the object type and size in bytes, following Git’s object format. For example, a blob object would be formatted as "blob <size>\0<content>".

Compute the SHA-1 Hash: The formatted content is passed through the SHA-1 hashing algorithm to generate the object hash.

Store the Object (if new): If the object is new, it is written to the object database. The file is named using the computed SHA-1 hash.