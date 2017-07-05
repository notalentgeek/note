* Example of horizontally and vertically center element in `<div>`.
* In this example I tried to center my `<video>` from its `<div>` parent.
* Here are the codes.

```markdown
<div id="video_container" style="align-items:center;display:flex;height:100%;justify-content:center;margin-bottom:0px;margin-left:0px;margin-right:0px;margin-top:2.5px;overflow:hidden;">
  <video id="video" width="50%" autoplay loop muted preload></video>
</div>
```

* The main solution is `style="align-items:center;display:flex;justify-content:center;"`.
* Need to make sure that every other nested parents needs to have their `height` and `width` specified.
* For general CSS, sometimes trying to bind another `<div>` to the thing you want to center is the solution.he solution.