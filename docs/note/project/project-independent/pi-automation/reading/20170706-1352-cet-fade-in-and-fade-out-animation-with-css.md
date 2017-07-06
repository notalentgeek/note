* Example code snippet for fade in and fade out animation with CSS.

```
.anim_fadein{
  -webkit-animation:fadein 0.5s linear forwards;
  animation:fadein 0.5s linear forwards;
}
.anim_fadeout{
  -webkit-animation:fadeout 0.5s linear forwards;
  animation:fadeout 0.5s linear forwards;
}
@-webkit-keyframes fadein{ 100%{ opacity:1; } }
@-webkit-keyframes fadeout{ 100%{ opacity:0;  } }
@keyframes fadein{ 100%{ opacity:1;  }  }
@keyframes fadeout{ 100%{ opacity:0; } }
```

* Some reference I took from this StackOverflow discussion, [https://stackoverflow.com/questions/30125705/css-how-to-make-an-element-fade-in-and-then-fade-out](https://stackoverflow.com/questions/30125705/css-how-to-make-an-element-fade-in-and-then-fade-out).