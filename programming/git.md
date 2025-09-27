# git

This file shares tips and tricks with git.

## How to make a file executable in git, but from windows machine?
Do it on Windows via Git attributes

Windows users can force Git to set execute bit in the index, even if the filesystem doesn’t:

```shell
git update-index --chmod=+x myscript.sh
```

and commit the change
```shell
git commit -m "Mark myscript.sh as executable"
```


Alternatively, you could make the file executable on mac and commit it.
```shell
chmod +x myscript.sh
```

## Restore squashed commit

Use `git reflog` command.
```shell
PS C:\Dev\workspaces\projects\my-wiki> git reflog
d7a8843 (HEAD -> master, origin/master) HEAD@{0}: commit: Add image demo
890ec86 HEAD@{1}: commit: Add ollama wiki
111dd5d HEAD@{2}: pull: Fast-forward
c42b604 HEAD@{3}: reset: moving to c42b604eede6de4ec04bbe2ff898f37d9d468b13
4f24f09 HEAD@{4}: reset: moving to HEAD
4f24f09 HEAD@{5}: commit: Add ollama wiki
c42b604 HEAD@{6}: commit: Update folder structure
5df6846 HEAD@{7}: reset: moving to 5df68463e0e6e49431239c1d9f5a2c1180c4ce84
89c5b72 HEAD@{8}: pull: Fast-forward
```

Identify the commit

Find the SHA (4f24f09) of the commit you want to restore.

Restore it

Two options:

Cherry-pick it back into your branch:
```shell
git cherry-pick 4f24f09
```
or 
Create a new branch from it:
```shell
git checkout -b restore-commit 4f24f09
```


Push if needed
```shell
git push origin HEAD -u
```


If reflog is already gone

If it’s not in git reflog, and you didn’t push those commits to any remote, then they may be lost after GC.
In that case, recovery is nearly impossible unless you have a backup or clone elsewhere.

✅ So: run git reflog, find the SHA, cherry-pick or branch from it.


## Clear git garbage

> Warning, after GC is pruned, the `reflog` command may not help you.

```shell
 git gc --prune
```