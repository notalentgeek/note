* Example of using PyInstaller with local lib.

```markdown
pyinstaller --onefile --paths="./path/local/lib" --paths="./you/can/use/multiple/of/paths" the_python_main_file.py
```

* I know this from here, [http://stackoverflow.com/questions/4110100/libraries-not-imported-when-creating-a-python-executable-with-pyinstaller](http://stackoverflow.com/questions/4110100/libraries-not-imported-when-creating-a-python-executable-with-pyinstaller).