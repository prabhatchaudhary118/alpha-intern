# alpha-intern

GROUP A
1. What problem does a Version Control System solve?
A Version Control System (VCS) helps manage changes to source code or files over time. It:
•	Tracks revisions and history of changes.
•	Allows multiple developers to collaborate.
•	Enables reverting to previous versions.
•	Helps resolve conflicts when changes are made simultaneously.

2. Differentiate between Centralized and Distributed VCS.
Feature	Centralized VCS (CVCS)          	        Distributed VCS (DVCS)
Repository Location	Single central server          	Each user has a full copy (local repo)
Dependency on Network Needs network to commit	    Can commit offline
Example Tools	SVN, CVS	                        Git, Mercurial
Failure Risk	Server crash = data loss risk	    Safer as every user has full history

3. What is Git and how is it different from GitHub?
•	Git is a distributed version control system that tracks code changes.
•	GitHub is a cloud-based platform that hosts Git repositories, offering collaboration features like pull requests, issues, and CI/CD.
In short: Git is the tool, GitHub is a hosting service built around Git.

4. What is a staging area in Git?
The staging area is a space where changes are listed before being committed.
•	It lets you prepare and review changes.
•	You add files to it using git add.
•	It acts as a buffer between your working directory and commit history.

5. What does the .git folder contain?
The .git folder is the heart of a Git repository, containing:
•	HEAD (current branch reference)
•	config (repo configuration)
•	objects/ (all commits, trees, blobs)
•	refs/ (branches, tags)
•	index (staging area)
•	Logs and other metadata

6. What is git branching and command to create/switch branches?
Git branching lets you diverge from the main code to work independently (e.g., features, fixes).
•	Create a new branch:
bash
git branch branch-name
•	Switch to another branch:
bash
git checkout branch-name
•	Or combine both (newer Git versions):
bash
git switch -c branch-name

7. What is the difference between git reset and git reset --hard?
•	git reset (default is --mixed):
Unstages changes but keeps them in working directory.
•	git reset --hard:
Discards all changes in staging and working directory. Cannot be recovered easily.
Example:
bash
git reset HEAD~1         # Undo last commit, keep files
git reset --hard HEAD~1  # Undo last commit, discard changes

8. What is a squash merge, and when would you use it?
A squash merge combines all commits from a branch into a single commit when merging.
Use it when:
•	You want a clean, simplified history.
•	Merging a feature branch with many WIP commits.
Command:
bash
git merge --squash feature-branch
git commit
_
9. Explain the use of git rebase with an example scenario.
git rebase moves your branch to a new base (usually to update with the latest changes from main or master).
Example Scenario:
•	You branched off main to develop feature-branch.
•	While working, main received updates.
•	You rebase to keep your branch updated cleanly.
bash
git checkout feature-branch
git rebase main
This replays your feature-branch commits on top of the updated main branch, creating a linear history.
