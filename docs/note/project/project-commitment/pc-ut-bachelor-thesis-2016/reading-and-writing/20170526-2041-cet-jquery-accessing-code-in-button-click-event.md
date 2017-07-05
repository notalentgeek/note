* Example codes on how initiate button click from DOM event with JQuery, [http://stackoverflow.com/questions/7937441/jquery-target-button-with-enter-key-when-input-field-is-focused](http://stackoverflow.com/questions/7937441/jquery-target-button-with-enter-key-when-input-field-is-focused).

```markdown
$("#loginUserID").keypress(function(event){
  if(event.keyCode == 13){
    $("#loginBtn").click();
  }
});
```});
```