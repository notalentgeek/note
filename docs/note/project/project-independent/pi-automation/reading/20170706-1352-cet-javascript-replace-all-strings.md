* JavaScript `string.replace("a", "b")` only replaces the first occurrence of "a" with "b".
* This is contrary to Python's `string.replace("a", "b")` which replaces all occurrence of "a" with "b".
* This thread in StackOverflow, [https://stackoverflow.com/questions/1392413/calculating-a-directory-size-using-python](https://stackoverflow.com/questions/1392413/calculating-a-directory-size-using-python), have the solution.
* The JavaScript codes for replacing all occurrence of strings are these.

```
str.replace(/a/g, "b");
```

* The codes will replace all "a" with "b".
* The first parameter is a regular expression (regex).