* Fixing import error, if local library in Python is not in the same root with the starter Python script, [http://stackoverflow.com/questions/4383571/importing-files-from-different-folder-in-python](http://stackoverflow.com/questions/4383571/importing-files-from-different-folder-in-python).
* Example codes.

```markdown
import sys
sys.path.insert(0, "/path/to/application/app/folder")

import file
```

* In that example `file.py` is located in `/path/to/application/app/folder`.
* Or you can use relative position from the root of the main Python script itself.
* For example `"/path/to/application/app/folder"`.
* For example changing `/path/to/application/app/folder` into `./folder`. Means the `file.py` is located in the folder named "folder" in the root of the executed Python script.