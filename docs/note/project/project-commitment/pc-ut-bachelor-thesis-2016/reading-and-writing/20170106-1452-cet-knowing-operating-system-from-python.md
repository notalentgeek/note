* Example to check operating system from Python script.

```markdown
from sys import platform
if platform == "linux" or platform == "linux2":
    # Linux.
elif platform == "darwin":
    # OS X.
elif platform == "win32":
    # Windows.
elif platform == "cygwin":
    # Windows' Cygwin.
```

* I know this from here, [http://stackoverflow.com/questions/8220108/how-do-i-check-the-operating-system-in-python](http://stackoverflow.com/questions/8220108/how-do-i-check-the-operating-system-in-python.