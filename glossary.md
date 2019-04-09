# Glossary
* **branch**: A variation of our repository's main code along with it's history. A single repostiory may have multiple branches. 
* **checkout**: Changing to a different branch. 
* **commit**: (n) A single point in Git history, i.e., a revision or version. (v) the process of saving a new snapshot of the code in the current branch. 
* **fetch**: Used to download data from a remote repository. Differs from "pull" in that fetching just downloads the data; it doesn't integrate this into your working files.  
* **fork**: Similar to branching, but it makses a clone on the server side (e.g., in GitHub or S:/WORK/Git). Best used when you want to create a potentially seperate project that may never merge back with the source.  
* **head**: A named reference to the commit at the tip of a branch.
* **HEAD**: The current branch. 
* **master**: The default development branch (an arbitrary name, but following convention helps when you are learning)
* **merge**: To bring the contents of an external branch into the current branch. 
* **origin**: An alias for a particular remote repository (e.g., the bare repos in S:/WORK/Git or GitHub) url or filepath. If you want to see the details, type "git remote show origin" in Git Bash. 
* **pull**: Used to download data from a remote repository. Differs from "fetch" in that the purpose is to update your branch with the latest changes (i.e., it is merged into your current branch.)
* **push**: Used to update another branch with commits in the current branch. 
* **repository**: A project or set of files, including their history, and the database needed to keep track of the history. 
* **staging**: A 'soft' save for changes to a file, telling Git that you want to include it in the next commit. 

# Commands
## Getting Set Up
### Set a default folder for Git Bash
	Find the shortcut for Git Bash, right click on it and enter the filepath you desire in the box next to "Start in:". 

	For example, mine points to: "C:\Users\dcolombara\OneDrive - King County\my_docs\code"

### Create a new repository in S:\WORK\Git
	*Follow Alastair's instructions in "S:\WORK\Git\Network drive Git repositories guide - 2018-09-17.docx"

### Clone to local machine
	git clone /filepath/to/bare/repo.git /filepath/to/your/local/copy

## MAKING CHANGES

### Staging all the files in the current directory
	git add --all

### Staging a single file
	git add "filename.ext"

### Resetting (i.e., unstaging) a single file
	git reset "filename.ext"

### List of all files that are new or have uncommited changes
	git status

### View differences that have not been staged
	git diff

### View differences that have been staged
	git diff --staged

### Rename file within Git
	git mv "old_file_name.txt" "new_file_name.txt" 

### Commit changes in a single file
	git commit "filename.txt" -m "Detailed and useful message to help your future self"

### Commit changes in all files in the current directory
 	git commit -a -m "Detailed and useful message to help your future self"

### Undo a commit (undo the last commit, but keep any changes since.)
	git reset --soft [commit]

### Undo a commit (undo the last commit, and delete any changes since.)
	git reset --hard [commit]

### Push all commits to the remote repo ['origin'] from your local repo ['master'] 
	git push origin master

## MORE COMPLEX WORK FLOWS
### List all branches in your repository (an asterisk will mark your current branch)
	git branch

### Create a new branch
	git branch new_branch_name

### Switch to a different branch
	git checkout new_branch_name

### Push a new local branch to the server
	git push origin new_branch_name

### Merge another branch into your current branch (assumes you are in master)
	git merge new_branch_name

### Delete a local branch
	git branch -d new_branch_name

### Delete a remote branch
	git push origin --delete the_remote_branch

### Pull newer code from the remote repo
	git pull 

### Pull / checkout a branch that is on the remote repo but not yet copied to your local repo
	git checkout --track origin/branch_on_remote


## USE THE BUILT IN GUI
### GUI to show the history of commits in an entire repository
	gitk --all 	

### GUI to show the history of commits for a specific file
	gitk --all "filename.txt"

### GUI to show the last 10 changes in the last 3 weeks
	gitk --max-count=10 --since="3 weeks ago"  --all "filename.txt"

