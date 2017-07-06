* In CSS, if you want to make position to be absolute but only to its parent (not to all pages). The parent need to mention `position:relative` and then the children need to mention `position:absolute;`.
* Example codes.

```
<div style="position:relative;">
    <div style="position:absolute;">
    </div>
</div>
```

* I have this reference from this StackOverflow discussion, [https://stackoverflow.com/questions/10487292/position-absolute-but-relative-to-parent](https://stackoverflow.com/questions/10487292/position-absolute-but-relative-to-parent).