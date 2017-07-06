* Example of vertical centering with `display:flex;`, [https://philipwalton.github.io/solved-by-flexbox/demos/vertical-centering/](https://philipwalton.github.io/solved-by-flexbox/demos/vertical-centering/).
* HTML codes.

```markdown
<div class="Aligner">
  <div class="Aligner-item Aligner-item--top">…</div>
  <div class="Aligner-item">…</div>
  <div class="Aligner-item Aligner-item--bottom">…</div>
</div>
```

* CSS codes.

```markdown
.Aligner {
  display: flex;
  align-items: center;
  justify-content: center;
}

.Aligner-item {
  max-width: 50%;
}

.Aligner-item--top {
  align-self: flex-start;
}

.Aligner-item--bottom {
  align-self: flex-end;
}
```

* I had this problem with horizontal aligning of `<video>`. The solution was actually at the `align-items: center;` part. the `align-items: center;` part.