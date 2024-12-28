Blobs
In a version control system like Git, a blob (binary large object) is used to store the contents of files. Unlike regular files, blobs in a version control system are stored in a compressed format with no metadata (such as filenames or timestamps) associated with them. The blob’s primary purpose is to represent the file's content at a specific point in time.

In this Git-like version control system, blobs are used to store the actual content of files, which can then be tracked across commits and versions. The blob's contents are immutable, meaning once a file’s content is stored in a blob, it cannot be changed. Any modification to the file will result in the creation of a new blob.

What is a Blob?
A blob is a data object that represents the contents of a file. The main characteristics of a blob are:

Content: The blob stores the raw content of a file, such as text, images, or binary data.
Hash: Each blob is associated with a unique hash, typically generated using a hash function (like SHA-1 or SHA-256). This hash serves as the identifier for the blob and allows the version control system to efficiently track changes to the file's contents.
No Metadata: Unlike files on a file system, blobs do not store any metadata (e.g., filenames, timestamps, permissions). Their only role is to hold the file content.
Blob Structure in the Repository
Blobs are stored in the repository’s object database. In Git-like systems, this is usually located in the .git/objects/ directory. The object ID for each blob is the hash of the file's content.

Blob Object: The object is created by hashing the contents of the file, then storing this hash in the object database.
Filename Mapping: The blob does not store the filename. Instead, the filename is mapped to the blob object through other structures like trees (which represent directories).
How Blobs Work
Creating a Blob: When a file is added to the version control system, the contents of the file are hashed, and the resulting hash is used to create a new blob object. This blob object is stored in the object database.

Modifying a Blob: If the content of the file changes, the version control system will create a new blob with the new content and a new hash. The old blob remains in the object database, but the new blob is tracked for the new version of the file.

Referencing Blobs: Blobs are referenced by other objects in the system, such as tree objects (which represent directories) and commit objects (which represent commits). The commit object stores references to tree objects, which in turn reference blobs.

Storing and Retrieving Blobs
Storing: The hash_object command is responsible for creating a blob from a file. This command hashes the file’s content and stores it in the .git/objects/ directory using the generated hash as the filename (with the first two characters as the directory name and the remaining characters as the filename).

Retrieving: When a file is checked out or displayed using commands like cat_file, the system retrieves the corresponding blob from the object database using the hash.