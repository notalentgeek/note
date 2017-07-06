* Example of using multiple exception in 1 `try` - `except` statement.
* I know this from this discussion in StackOverflow, [http://stackoverflow.com/questions/6470428/catch-multiple-exceptions-in-one-line-except-block](http://stackoverflow.com/questions/6470428/catch-multiple-exceptions-in-one-line-except-block).

```markdown
except(thisException, anotherException) as error:
    print(error)
    pass
```