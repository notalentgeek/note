* There are `os.makedirs()` and `os.mkdir()` in Python.
* Both are used to make directory.
* However, `os.makedirs()` can be used to make a nested directory if it is not yet exist.
* For example.

```markdown
os.makedirs("/path/to/directory/i/want/to/make")
```

* While `os.mkdir()` cannot do this. Hence, just use `os.makedirs()`.