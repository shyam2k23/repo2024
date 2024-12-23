# Git Internals - Behind the scene

git log --oneline

git show -s --prety=raw <commit_id>

git ls-tree <tree_id>

git show <blob_id>

https://medium.com/swlh/working-of-git-behind-the-scene-4112c6feb559

git hash-object

https://git-scm.com/book/en/v2/Git-Internals-Git-Objects
https://www.youtube.com/watch?v=0SJCYPsef54

. Compute the object ID without storing it:

# git hash-object /path/to/file
2. Compute the object ID and store it in the Git database:

# git hash-object -w /path/to/file
3. Compute the object ID specifying the object type:

# git hash-object -t [blob|commit|tag|tree] /path/to/file
4. Compute the object ID from stdin:

# cat /path/to/file | git hash-object --stdin

https://www.thegeekdiary.com/git-hash-object-computes-the-unique-hash-key-of-content-and-optionally-creates-an-object-with-specified-type/


https://www.freecodecamp.org/news/git-internals-objects-branches-create-repo/
