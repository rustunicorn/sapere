# Fixup Commits

Given

```bash
feat: first commit
fix: second commit
```

suppose you want to add more changes to the first commit. Then you can use `git
commit --fixup HEAD~2` or `git commit --fixup <hash>`. This creates a fixup
commit:

```bash
feat: first commit
fix: second commit
fixup! feat: first commit
```

Now you can squash them into the original commit: `git rebase -i --autosquash
<hash>^` or `git rebase -i --autosquash HEAD~3`.

