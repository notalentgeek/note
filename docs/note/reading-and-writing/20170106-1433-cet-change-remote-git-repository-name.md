* How to change repository name in GitHub, [http://stackoverflow.com/questions/5751585/how-do-i-rename-a-repository-on-github](http://stackoverflow.com/questions/5751585/how-do-i-rename-a-repository-on-github).
* Change repository name is just basically just to pin point the correct location of the new repository in case the URL of the new repository is different than the URL of old repository.
* You can change repository name in GitHub at its Setting pages.
* After that you need to adjust repository that still in local.
* First, you need to check which remote repository your local connected into, `git remote -v`.

* For example above codes will return these.

```markdown
origin  https://github.com/notalentgeek/pysoc.git (fetch)
origin  https://github.com/notalentgeek/pysoc.git (push)
```

* Now, you know that the repository you want to remove is listed as `origin`.
* Remove `origin`, `git remote rm origin`.
* Do this to change into new repository, `git remote add origin https://github.com/notalentgeek/new-pysoc.git`.
* I got this reference from here, [http://stackoverflow.com/questions/5751585/how-do-i-rename-a-repository-on-github](http://stackoverflow.com/questions/5751585/how-do-i-rename-a-repository-on-github).