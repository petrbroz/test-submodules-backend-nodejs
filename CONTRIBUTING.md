## Updating the Frontend Submodule

```bash
cd public
git checkout master
git pull
cd ..
```

## Removing the Frontend Submodule

If you want to remove the git submodule, and start tracking its files
as part of this repository:

```bash
git rm --cached public
git rm .gitmodules
rm -rf public/.git
git add public
```
