* How can you remove the first item in a Python list?
* StackOverflow discussion here, [http://stackoverflow.com/questions/4426663/how-do-i-remove-the-first-item-from-a-python-list](http://stackoverflow.com/questions/4426663/how-do-i-remove-the-first-item-from-a-python-list).
* Example.

```markdown
l = ["a", "b", "c", "d"]
l.pop(0)
```

* Another example is by creating subset and let the original list intact.

```markdown
x = [0,1,2,3,4]
x = x[1:]
```