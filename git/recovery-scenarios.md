# Recovery scenarios (calm Git)

These scenarios are here because real work includes mistakes. The goal is reversibility without drama.

## Scenario 1: You committed to the wrong branch (local)
You meant to commit on a feature branch but committed on `main`.

bash
git log --oneline -n 3  

'# identify the commit hash, for example abc1234
git checkout -b feature/move-commit  
git checkout main  
git reset --hard HEAD~1  
git checkout feature/move-commit  
'#This is safe only if you have not pushed the bad commit to a shared branch.
## Scenario 2: You pushed something you should not have (shared branch)
Do not rewrite shared history. Revert.  
git log --oneline  
git revert <commit-hash>  
git push  
Revert creates an explicit undo with a durable audit trail.  
## Scenario 3: You need to recover a lost commit
If you reset or rebase and think you lost work, use reflog.  
git reflog  
'# find the lost commit hash
git checkout -b recovery/<something>  
git cherry-pick <lost-commit-hash>  
## Scenario 4: You pulled and now have conflicts
First, see what is conflicted.  
git status  
Resolve conflicts in files, then:  
git add <file>  
git commit  
If you are rebasing and want to continue:  
git rebase --continue  
If you need to stop and back out:  
git rebase --abort  
