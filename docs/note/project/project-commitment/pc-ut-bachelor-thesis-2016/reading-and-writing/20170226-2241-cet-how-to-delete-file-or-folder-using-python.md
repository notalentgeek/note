* This information is taken from this StackOverflow discussion, [http://stackoverflow.com/questions/6996603/delete-a-file-or-folder-in-python](http://stackoverflow.com/questions/6996603/delete-a-file-or-folder-in-python).
* Basically if I want to delete file or folder, I can just use this Python script.
	* `os.remove(absolute_path)` to delete file.
	* `os.rmdir(absolute_path)` to delete empty folder.
* `shutil.rmtree(absolute_path)` to delete folder..