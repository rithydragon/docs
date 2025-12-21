Remove Git history but keep your files (most common)

This deletes the old repo metadata and re-initializes Git.

# from the project root
```
rm -rf .git
git init
git add .
git commit -m "Initial commit"
```

If you want to connect it to a (new or existing) remote repo:
```
git branch -M main
git remote add origin <REMOTE_URL>
git push -u origin main
```
Option 2: Completely delete the repo (files + history)

⚠️ This deletes everything.

rm -rf your-project-folder


Then recreate it:

mkdir your-project-folder
cd your-project-folder
git init

Option 3: Reset repo to a clean state (keep repo, wipe commits)

If you want to keep the repo but start fresh from scratch:
```
git checkout --orphan new-main
git add .
git commit -m "Fresh start"
git branch -D main
git branch -m main
git push -f origin main
```

(Only do this if you’re sure—this rewrites history.)

Option 4: Disconnect from the old remote only
```
git remote -v        # see current remotes
git remote remove origin
git remote add origin <NEW_REMOTE_URL>
```

### Force git push
Run exactly what Git suggests:
```
git push --set-upstream origin main
```
### Overwrite the remote repo history(Old repo). 
```
git push --set-upstream origin main --force
```
