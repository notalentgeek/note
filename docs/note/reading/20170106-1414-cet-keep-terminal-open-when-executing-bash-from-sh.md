* Here is an example codes on how to run script from an .sh file without closing the terminal.

```markdown
#!/bin/bash

echo "hello world"

$SHELL
```

* The `$SHELL` is important because it prevent the terminal to be closed after the operation ends. This command keeps the opened terminal open.
* I got this information from, [http://askubuntu.com/questions/20330/how-to-run-a-script-without-closing-the-terminal](http://askubuntu.com/questions/20330/how-to-run-a-script-without-closing-the-terminal).