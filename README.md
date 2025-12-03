1. Cloned repo:
```
mkdir L100 && cd L100
git init
# Optionally create a README
echo "# L100" > README.md
git add README.md
git commit -m "Initial commit: README"
# Add remote and push
git remote add origin https://github.com/<your-username>/L100.git
git branch -M main
git push -u origin main
```
2. Created files, staged, and committed:
```
echo "Exercise 1" > ex1.txt
git add ex1.txt
git commit -m "Adding exercise1"
git status
```


## Branching and merging
- Created branch `feature/notes`,'feature/output_screenshot', committed, merged into `main`:
```
git checkout -b feature/notes
# edits...
git commit -m "Add Notes"
git checkout main
git merge feature/notes
```
git log --graph --oneline --all` output

## Synchronization
- Pushed changes:
```
git push origin main
```
- On another clone:
```
git fetch origin
git merge origin/main
```

## Internals inspected
- Blob hash for `ex1.txt`: `<paste-hash>`  
- Commit object:
```
git cat-file -p <commit-hash>
```
(Include full commit output and explanation)

## Diff, staged vs unstaged
1. Create a few commits for testing
echo "one" > a.txt; git add a.txt; git commit -m "one"
2. Work on a file
echo "changed" >> a.txt

3. Unstaged changes
git diff a.txt        # working dir vs index

4. Staged changes
git add a.txt
git diff --cached     # index vs HEAD

5. All changes vs HEAD
git diff HEAD

## To look for past History of changes
git blame README.md

## Tags
Created annotated tag `v1.0`:
```
git tag -a v1.0 -m "Release 1.0"
git push origin v1.0