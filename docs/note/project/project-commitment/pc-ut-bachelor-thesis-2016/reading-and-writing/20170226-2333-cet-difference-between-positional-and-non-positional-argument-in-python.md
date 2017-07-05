* This function's parameters will represent positional argument `args` in Python, `def function_name(_variable_1:str, _variable_2): pass`.
* This function's parameters will represent non - position argumentin `kwargs` in Python, `def function_name(_variable_1:str="", _variable_2=None): pass`.
	* You then can enter the function by `function_name(_variable_1="hello world", _variable_2=any_object)` or `function_name(_variable_2=any_object, _variable_1="hello world")` because the position does not matter anymore.
* `kwargs` usually returns `dict` dictionary object.