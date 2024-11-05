Table of content:
- [Getting Started - What is Git?](https://github.com/shyam2k23/repo2024/blob/main/Git.md#getting-started---what-is-git)
- Getting Started - Basics
- 2.1 Getting a Git Repository
- 2.2 Recording Changes to the Repository 
- 2.3 Viewing the Commit History
- 2.4 Undoing Things
- 2.5 Working with Remotes
- 2.6 Tagging
- 2.7 Git Aliases
- 2.8 Summary
- Git Branch Vs Tag
- Git Tag
- Git Branch
- Git Log
  
# Getting Started - What is Git?
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Git is easy to learn and has a tiny footprint with lightning fast performance. It outclasses SCM tools like Subversion, CVS, Perforce, and ClearCase with features like cheap local branching, convenient staging areas, and multiple workflows.  
https://git-scm.com/  
https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F#what_is_git_section

# Getting Started - Basics
## 2. Git Basics  
### 2.1 Getting a Git Repository
  
#### a) Initializing a Repository in an Existing Directory
   - $ cd C:/Users/user/my_project
   - $ git init
   - $ git add *.c
   - $ git add LICENSE
   - $ git commit -m 'Initial project version'  
  
#### b) Cloning an Existing Repository
   - git clone https://github.com/libgit2/libgit2
  
### 2.2 Recording Changes to the Repository  
  
#### a) Checking the Status of Your Files
  - $ git status
  - $ echo 'My Project' > README
  - $ git status

#### b) Tracking New Files
  - $ git add README
  - $ git status
  
#### c) Staging Modified Files
  - $ git status
  - $ git add CONTRIBUTING.md
  - $ git status
  - $ vim CONTRIBUTING.md
  - $ git status
  - $ git add CONTRIBUTING.md
  - $ git status
  - $ git status -s
  
#### d) Ignoring Files
  - $ cat .gitignore
  - *.[oa]
  - *~
  
#### e) Viewing Your Staged and Unstaged Changes
  - $ git status
  - $ git diff
  - $ git diff --staged
  - git diff --cached to see what you’ve staged so far (--staged and --cached are synonyms):
  - $ git diff --cached
  
#### f) Committing Your Changes
  - $ git commit
  - enter message for commit
  - $ git commit -m "Story 182: fix benchmarks for speed"
  
#### g) Skipping the Staging Area
  - $ git commit -a -m 'Add new benchmarks'
  -  Adding the -a option to the git commit command makes Git automatically stage every file that is already tracked before doing the commit, letting you skip the git add part
  
#### h) Removing Files
  -  $ rm PROJECTS.md
  -  $ git status
  -  $ git rm PROJECTS.md
  -  $ git status
  -  Another useful thing you may want to do is to keep the file in your working tree but remove it from your staging area.
  -  $ git rm --cached README
  
#### i) Moving Files
  -  If you want to rename a file in Git, you can run something like
  -  $ git mv file_from file_to
  -  $ git mv README.md README
  -  $ git status
    
### 2.3 Viewing the Commit History  
### 2.4 Undoing Things  
### 2.5 Working with Remotes  
### 2.6 Tagging  
### 2.7 Git Aliases  
### 2.8 Summary  

https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository

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
- By default, the git push command doesn’t transfer tags to remote servers. You will have to explicitly push tags to a shared server after you have created them. This process is just like sharing remote branches — you can run git push origin <tagname>.
- git push origin v1.5
- git checkout v2.0.0 : Checkout a tag
  
https://git-scm.com/book/en/v2/Git-Basics-Tagging

## Git Branch
Branching means you diverge from the main line of development and continue to do work without messing with that main line.

![image](https://github.com/user-attachments/assets/01138945-9d6c-4007-b491-42ad6d954115)

# Git Log
Shows the commit logs.
- git log
- git log --pretty=oneline
- git log --pretty=format:"%h - %an, %ar : %s"
-     
https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History
