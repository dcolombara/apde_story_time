# APDE Story Time Tutorial

## Install Git Bash
1) Install Git Bash following the directions provided in `<S:\Transfer\DannyColombara\git_training\git_installation_instructions.docx>`
2) After installing Git bash you're welcome to download [GitHub Desktop](https://desktop.github.com). However, we will only use Git Bash for our tutorial. 

## Clone this repository to your laptop
1) Open Git Bash
2) Go the directory where you want to place a copy of this repo. 
     * If you installed Git following the instructions above, you should automatically be in the correct folder
     * Check that you're in the right directory by typing `<pwd>`
     * If you're in the wrong place, type `<cd /c/Users/YOUR_USERNAME/code/>`
3) Type `<git clone https://github.com/dcolombara/apde_story_time.git>`. This will copy the repository as a folder to your computer.
4) Switch to the newly created directory to be sure it exists
     * `<cd apde_story_time>` changes the directory 
5) Check the contents of the new directory (a.k.a., local repository)
     * `<ls>` lists the contents
     
## View the file that you will be editing
Open `apde_story_time_example.txt` in your apde_story_time directory. There are three ways to do this:
1) The 'normal' way. 
    * Use Windows explorer, find the file, and double click it to open in with your default text editor
2) Using Git Bash
    * Just type `<start apde_story_time_example.txt>`. This should open it in your default text editor.
3) View it in Git Bash
   * I don't recommend this, but ... 
    * `cat apde_story_time_example.txt` ... quickly view smaller files
    * `less apde_story_time_example.txt` ... better for larger files
    
When you are done, be sure to close the file.
     
## Explore the branches
1) Git allows you to have multiple branches. One basic workflow that shows the utility would be maintaining a functional **production** branch that always runs while working on a **development** branch to create version 2.0. Branches are also often used to create small stand alone functions with these branches often called **feature** branches. 
     * For this tutorial, we will only have a **master** branch and a **danny** branch. 
     * Note that the branch names are up to the creator and so they could be anything he or she wants.
2) Check for available branches and identify the branch that you are on by typing `<git branch>`. 
     * The branch that you are currently on will be makred with an asterisk (*). 
3) Practice switching back and forth between the **master** and **danny** branches by typing `<git checkout master>` and `git checkout danny>`.
     * View the `apde_story_time_example.txt` while you are in a given branch. Then close the file and view it while you are in another branch. How are they different?
4) When you're finished exploring the branches, ensure you are on the **master** branch. 

## Edit the the example
1) Open `apde_story_time_example.txt`
2) Select one paragraph to edit and be sure to coordinate. If two people edit the same paragraph, we may end up with [merge conflicts](https://help.github.com/en/articles/resolving-a-merge-conflict-using-the-command-line), which is never fun.
3) Fix the typos in your paragraph.
4) Save the file.

## Check your status
1) `<git status>` shows you the state of your working directory as well as the 'staging area.' The staging area is basically a loading dock where you park your changes prior to commiting (saving) them to Git. 
2) Type `<git status>` in your Bash window. You should get something like the following:
    > On branch master  
    > Your branch is up to date with 'origin/master'.
    > 
    > Changes not staged for commit:  
    > (use "git add <file>..." to update what will be committed)  
    > (use "git checkout -- <file>..." to discard changes in working directory)
    >
    >        modified:   apde_story_time_example.txt
    > 
    > no changes added to commit (use "git add" and/or "git commit -a")
     * The first part tells you which branch you are on and whether or not you are up to date. 
        * origin/master is referring to the master branch on the origin (i.e, the remote repository, a.k.a., GitHub repo)
     * The second part tells you which files have been modified but are not yet staged.
     * Note that the second part also informs you that you can stage (pseudo-save) what you've done so far (`<git add <file>>`) or you can drop the modifications to go back to the most recent commit (`<git checkout -- <file>>`).
 
## Identify your changes
1) `<git diff>` will show you the changes that you've made since the last stage or commit (definitions below). 
2) Tip! Sometimes, when you have many changes, git diff goes on for multiple screens. Hit the space bar to continue to scroll down. To escape at the end, type `<q>`.
3) Try `<git diff>` to see your changes
    
## Stage your changes
1) Saving files in Git is often done in two steps: staging and commiting. 
2) To stage a file means to prepare it for a commit. You can think of it like a loading dock where your files are waiting for the final command to send them to your Git history. You can stage files multiple times but the changes will only be recorded in the permanent history once you commit them. (So perhaps staging is like engagement and commiting is like marriage? You only produce a paper trail for the latter.) 
3) `<git add>` is the command for staging your files.
4) `<git add .>` will stage all of the files that have been modified, but are not yet staged. 
5) `<git add apde_story_time_example.txt>` will only stage the specific file that you modified.
6) Stage the file with your modifications. Then **check your status**. How has your status changed?

## Commit your changes
1) `<git commit>` can be thought of as saving your changes to your local repository's Git history. 
2) `<git commit -m "your meaningful description here"> will commit your staged modifications and tag them with your descriptive message.
3) `<git commit <file> -m "your meaningful description here:>` is preferred if you've staged multiple files but only want to commit one or want to give it a specific commit message.
4) **Tip!** `<git commit -a -m "your meaningful description here">` will commit all modified or deleted files without needing to stage them first. However, it will not commit any newly created files. New files always need to be staged. 
5) Commit your changes to Git Then **check your status**. How has your status changed?

## Fetching / Pulling changes from the remote repository
While you were working on your edits, others may have saved changes to the code on the remote repository. There are two ways to get updated code from the remote:
1) **Fetching**: Fetching downloads new / updated code, but makes no attempt to integrate it with your local version. This means it is 100% safe. It will never change your code and cannot lead to merge conflicts. The command is `<git fetch>`
2) **Pulling**: Pulling downloads new / updated code **AND** integrates it with your code. It brings your repository up to date and is essence a `<git fetch>` and `<git merge>` combination. This sometimes leads to merge conflicts where two people edited the same portion of the code and Git cannot figure out which code chunk to use. In that case it will spit out an error and you will have to identy the portions that you want to keep manually. 

## Push your changes to the remote repository
1) Commited changes live in your local Git repository (e.g., `C:\Users\dcolombara\code\apde_story_time`).
2) Your changes need to be "pushed" to the remote repository (i.e., the GitHub repository) in order for other people to use them.
3) `<git push origin master>` means "push the commits in my **local branch named master** to the **remote named origin**.
4) Since we have all been editing different sections of the 'code', there should be no chance of merge conflicts. 
5) The first one of you who pushes your commit will have it easiest since what is on the remote is exactly what is in your copy, with the exception of your own changes. However, the second person who tries to push will get an error message saying something like "failed to push some refs to `'https://github.com/dcolombara/apde_story_time.git'`." Luckily the error message also provides you with a useful hint, `"You may want to first integrate the remote changes (e.g., 'git pull ...') before pushing again."`
6) If you received an error message:
     * Type `<git pull>` 
     * Enter a commit message for the merge
     * Type `<git pull origin master>`. Hopefully it worked perfectly this time!

## Merging branches
1) When you looked in the **danny** branch above, you saw that there was an additional paragraph and a citation, as compared to the **master** branch. Here we will want to merge the **danny** branch into the the **master** branch.
2) Be sure you are in your local copy of the **master** branch: `<git checkout master>`.
3) Then type `<git merge danny>`.
4) Check the contents of `apde_story_time_example.txt`. Is this what you expected?

## Creating & deleting branches
1) Create a new local branch by typing `<git checkout -b <local-branch-name>>`. 
     * This is a short cut combining two commmands: `<git branch <local-branch-name>>` and `<git checkout <local-branch-name>>`.
2) If/when you want to push your branch to the remote, type `<git push <remote-name> <local-branch-name>:<remote-branch-name>>`. For example I pushed the danny branch to the remote using `<git push origin danny:danny>`. 
    * You may have to identify tracking information for the new branch by typing `<git branch --set-upstream-to=origin/<remote-branch-name> <local-branch-name>>`, e.g., `<git branch --set-upstream-to=origin/danny danny>`.
3) Delete a local branch by typing `<git branch -d <local-branch>>`.
4) Delte a remote branch by typing `<git push <remote-name> --delete <remote-branch>`. For example, `<git push origin --delete danny>`.
5) Try it!     

## Finding & adding remote branches
What should you do if you know another person started a branch with some code that you wanted to examine?
1) `<git branch -r>` ... shows you the branches on the remote
2) `<git checkout -b <local-branch-name> <remote-name>/<remote-branch-name>>` ... copies the remote branch to your local repository
