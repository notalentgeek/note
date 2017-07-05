* For CSS. This codes mainly to hide unecessary table of content in the left side of the screen.

```markdown
div.bs-sidebar.hidden-print.affix.well{ display: none; }
```

* For JS (do not forget to also put JQuery). This JavaScript codes is to re - adjust the layout after the table of content panel is removed.

```markdown
$("div.col-md-3").remove();
$("div.col-md-9").attr("class", "class-md-12");
```