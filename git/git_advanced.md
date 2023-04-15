# Index
- Git undoing
- git reset & revert
- git branch & merge
- git workflow

# Git Undoing
- git undoing
- git undoing can be classified into three stages
  - Working Directory
    - ```git restore``` : modified file is restored to prior state
  - Staging Area
    - ```git rm --cached; git restore --staged;``` : changes reflected in staging area restored to working directory
  - Repository
    - ```git commit --amend``` : commit completed files restored back to stagin area

## git restore


