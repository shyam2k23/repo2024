# Git Branch Vs Tag

## Git Tag
Git has the ability to tag specific points in a repository’s history as being important.  
Typically, people use this functionality to mark release points (v1.0, v2.0 and so on).  
Git supports two types of tags: lightweight and annotated. A lightweight tag is very much like a branch that doesn't change — it's just a pointer to a specific commit. Annotated tags, however, are stored as full objects in the Git database.
- git tag : List all tag
- git tag v1.0.0 : Create a lightweight tag, To create a lightweight tag, don’t supply any of the -a, -s, or -m options, just provide a tag name
- git tag -a v1.4 -m "my version 1.4" : Create a annotated tag, -m message, -a annotat
- git tag -l "v1.8.5*" : Search for specific pattern
- git tag -v v1.0.0 : Verify a tag
- git tag -d v1.0.0 : Delete a tag
- git show v1.0.0 : Show tag data along with commit

## Git Branch
Branching means you diverge from the main line of development and continue to do work without messing with that main line.

![image](https://github.com/user-attachments/assets/01138945-9d6c-4007-b491-42ad6d954115)
