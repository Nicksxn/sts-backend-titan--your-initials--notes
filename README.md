                       # GIT
Git is a distributed revision control and source code management system with an emphasis on 
speed. Git was initially designed and developed by Linus Torvalds for Linux kernel development.

# Working Directory and Staging Area or Index 

The working directory is the place where files are checked out. In other CVCS, developers . But Git uses a 
different strategy. Git doesn’t track each and every modified file. Whenever you do commit an 
operation, Git looks for the files present in the staging area. Only those files present in the 
staging area are considered for commit and not all the modified files. 

# Let us see the basic workflow of Git. 

Step 1 − you modify a file from the working directory. 
Step 2 − you add these files to the staging area. 
Step 3 − you perform commit operation that moves the files from the staging area. After push 
operation, it stores the changes permanently to the Git repository.

# Blobs 

Blob stands for Binary Large Object. Each version of a file is represented by blob. A blob holds 
the file data but doesn’t contain any metadata about the file. It is a binary file, and in Git 
database, it is named as SHA1 hash of that file. In Git, files are not addressed by names. 
Everything is content-addressed. 

# Trees 

Tree is an object, which represents a directory. It holds blobs as well as other sub-directories. A 
tree is a binary file that stores references to blobs and trees which are also named as SHA1 hash 
of the tree object. 

# Commits 

Commit holds the current state of the repository. A commit is also named by SHA1 hash. You 
can consider a commit object as a node of the linked list. Every commit object has a pointer to
the parent commit object. From a given commit, you can traverse back by looking at the parent 
pointer to view the history of the commit. If a commit has multiple parent commits, then that 
particular commit has been created by merging two branches. 

# Branches 

Branches are used to create another line of development. By default, Git has a master branch, 
which is same as trunk in Subversion. Usually, a branch is created to work on a new feature. 
Once the feature is completed, it is merged back with the master branch and we delete the 
branch. Every branch is referenced by HEAD, which points to the latest commit in the branch. 
Whenever you make a commit, HEAD is updated with the latest commit. 

# Tags 

Tag assigns a meaningful name with a specific version in the repository. Tags are very similar to 
branches, but the difference is that tags are immutable. It means, tag is a branch, which nobody 
intends to modify. Once a tag is created for a particular commit, even if you create a new 
commit, it will not be updated. Usually, developers create tags for product releases. 

# Clone 

Clone operation creates the instance of the repository. Clone operation not only checks out the 
working copy, but it also mirrors the complete repository. Users can perform many operations 
with this local repository. The only time networking gets involved is when the repository 
instances are being synchronized. 

# Pull 

Pull operation copies the changes from a remote repository instance to a local one. The pull 
operation is used for synchronization between two repository instances. This is same as the 
update operation in Subversion. 

# Push 

Push operation copies changes from a local repository instance to a remote one. This is used to 
store the changes permanently into the Git repository. This is same as the commit operation in 
Subversion. 

# HEAD 

HEAD is a pointer, which always points to the latest commit in the branch. Whenever you make 
a commit, HEAD is updated with the latest commit. The heads of the branches are stored in 
.git/refs/heads/ directory. 

[CentOS]$ ls -1 .git/refs/heads/ 
master

# Revision 

Revision represents the version of the source code. Revisions in Git are represented by commits. 
These commits are identified by SHA1 secure hashes. 

# URL 

URL represents the location of the Git repository. Git URL is stored in config file. 

[root@CentOS tom_repo]$ pwd 
/home/tom/tom_repo


# Git - Life Cycle 

General workflow is as follows − 
You clone the Git repository as a working copy. 
You modify the working copy by adding/editing files. 
If necessary, you also update the working copy by taking other developer's changes. 
You review the changes before commit. 
You commit changes. If everything is fine, then you push the changes to the repository. 
fter committing, if you realize something is wrong, then you correct the last commit 
and push the changes to the repository. 
