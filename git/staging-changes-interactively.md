# Staging Changes Interactively

To interactively add files in commit we can use `--patch` flag in `git add`

It can be used for a single file

```bash
git add --patch README.md
```

or can operate on the entire repository

```bash
git add --patch
git add -p
```