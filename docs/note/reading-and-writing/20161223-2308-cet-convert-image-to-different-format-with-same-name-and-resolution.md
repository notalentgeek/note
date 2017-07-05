* Here is how to convert multiple images using ImageMagick with same resolution and same file name within a folder.

```markdown
mogrify -format png all/jpg/in/this/absolute/path/will/be/png/*.jpg
```