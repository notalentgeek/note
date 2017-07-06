* Usually when I want to write something to a new file that I have just generated using Python I can just use this codes.

```markdown
with open("file.txt", "w") as fileTxt:
    file.write(stringVariable)
```

* However, I only want to append (meaning that I only want to add lines in the into the bottom the file) instead of writing. I use these codes instead.

```markdown
with open("file.txt", "a") as fileTxt:
    fileTxt.write(stringVariable)
```

* As `a` means to append instead of `w` to write/overwrite the file.