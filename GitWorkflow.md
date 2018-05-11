# New Feature
1. git checkout -t origin/master -b FEA-NewStuff (create feature branch 'FEA-NewStuf')
2. Make feature changes ...
3. git add -A   (stage the change for the current branch)
4. git commit -m 'Changes for NewStuff' (commit changes to current branch)
5. --- take care of company Change Request ---

# Second Feature before first is Complete
1. get checkout master (go to master branch, no changes)
2. git checkout -b FEA-SecondOne
3. Make featurs changes ...
4. git add -A
5. git commit -m 'Changes for Second Feature ...'

# Handle Company Change Request (CR)
1. git checkout FEA-ZZZ-Branch-Name
2. git pull --rebase origin/master (Makes your branch up to date with master)
3. CR this is where your code is reviewed, it might result in changes ...
4. foreach round of suggested CR changes do:
  1. Make suggested change(s)
  2. git add -A
  3. git commit --amend Sqaush all your latest changes into same commit
  4. Update the CR and wait for review changes
5. <After recieve a Ship it on CR>
6. get checkout master (go back to the local master branch, still in unchanged state)
7. git pull (check the remote repository to pull any changes that anyone else has made, get local master up-to-date)
8. git merge FEA-ZZZ-Branch-Name (merges/update local master to branch changes)
9. git mergetool (resolve any merge conflicts)
10. git push (Push changes to remote repository)
11. get branch -D FEA-ZZZ-Branch-Name (cleanup feature by deleting it, unless you need it)

# Update with Latest remote changes, daily!
Goto whichever branch your are working with to get latest changes:

1. git checkout FEA-ZZZ
2. git pull --rebase origin/master (update with latest master changes)
3. Quite out of vim :q

# Other helpful Commands
Sometimes you need a little more:

1. git reset --soft HEAD~1 # undo last commit
