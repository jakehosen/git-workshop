---
marp: true
theme: default
paginate: true
header: 'Git Introduction'
style: |
  section {
    font-family: 'Helvetica', 'Arial', sans-serif;
  }
  h1 {
    color: #f05033;
  }
  h2 {
    color: #333;
    border-bottom: 2px solid #f05033;
    padding-bottom: 0.3em;
  }
  code {
    background: #f4f4f4;
    padding: 0.1em 0.3em;
    border-radius: 3px;
  }
  .lead {
    text-align: center;
  }
---

<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _header: '' -->

# Why Use Git?

## Track your work and collaborate efficiently
- Take snapshots, known as commits, of your work to track progress and easily rewind.
- Avoid file fragmentation.
- Collaborate efficiently.

```
analysis.R
analysis_v2.R
analysis_final.R
analysis_final_FINAL.R
analysis_final_FINAL_use_this_one.R
```

---
# Git and GitHub
- Git is the software, GitHub, now run by Microsoft, is one of many services for hosting online git repositories.
- Other Git hosts:


---
# Git Fundamentals (ADD SOME VISUALS AND BREAK UP THESE SLIDES)
- Repository: A folder where Git tracks your project and its history.
- Clone: Make a copy of a remote repository on your computer.
- Stage: Tell Git which changes you want to save next.
- Commit: Save a snapshot of your staged changes.
- Branch: Work on different versions or features at the same time.
- Merge: Combine changes from different branches.
- Pull: Get the latest changes from a remote repository.
- Push: Send your changes to a remote repository.

---
# Git Local Respostiory
- There is a hidden directory ```.git``` in the main directory of a git repository.
- The ```.git``` directory holds all the git files, including changes that you have staged.
---
# Git Workflow
- Basic git workflow for a *commit* is as follows:
    - Select files to be added to a commit with ```git add```.
    - Add those files to the staging area with ```git commit```
    - Send those files to the cloud with ```git push```.
    - Get changes made by others with ```git pull```.
![graphic displaying how git add and git commit are applied to a working directory](images/git-staging.png)
