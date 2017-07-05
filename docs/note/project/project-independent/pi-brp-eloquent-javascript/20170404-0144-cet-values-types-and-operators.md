![./20170404-0144-cet-values-types-and-operators-1.png](./20170404-0144-cet-values-types-and-operators-1.png)

* I was looking for this quotation.
* However, the book seems to be not exists.

![./20170404-0144-cet-values-types-and-operators-2.png](./20170404-0144-cet-values-types-and-operators-2.png)

* Example of writing 13 with binary number.

![./20170404-0144-cet-values-types-and-operators-3.png](./20170404-0144-cet-values-types-and-operators-3.png)

* Volatile memory is RAM (Random Access Memory).
* Non - volatile memory is hard disk.
* Modern computer has more than 30 billion bits in volatile data storage. I think this means RAM, right?

![./20170404-0144-cet-values-types-and-operators-4.png](./20170404-0144-cet-values-types-and-operators-4.png)

* Every set of bits has a role.
* This role is what it is data type in higher level programming language.
* In JavaScript there are these 6 types of basic values.
    * Function.
    * Number.
    * Object.
    * String.
    * Undefined value.
        * Undefined.
        * Null.

![./20170404-0144-cet-values-types-and-operators-5.png](./20170404-0144-cet-values-types-and-operators-5.png)
* To create value, in JavaScript, you can just invoke its name.

![./20170404-0144-cet-values-types-and-operators-6.png](./20170404-0144-cet-values-types-and-operators-6.png)

* JavaScript engine usually has its own memory allocation algorithm.
* Nevertheless, the only problem would be if you need __all__ variables to be exists at the same time.
* In case not, variable's memory block will be "rotated" accordingly as it is in the memory allocation algorithm.

![./20170404-0144-cet-values-types-and-operators-7.png](./20170404-0144-cet-values-types-and-operators-7.png)

* There used to be a problem with accidentally overflowing the value of a variable.
* Especially in 8 bits or 16 bits computer.
* Today computer is at least 32 bits to 64 bits.
* There should be no problem on dealing larger variable's value.

![./20170404-0144-cet-values-types-and-operators-8.png](./20170404-0144-cet-values-types-and-operators-8.png)

* The positivity of a number (whether it is positive or negative number) as well as decimal point are stored on another block of memory.
* Hence, float and negative float number need more memory blocks.
* The maximum number of decimal points can be stored with JavaScript (this paragraph does mention whether this is meant for computer or JavaScript in general) is 9 quadrillion (15 trailing zeros), which is still good for most program written in JavaScript.

![./20170404-0144-cet-values-types-and-operators-9.png](./20170404-0144-cet-values-types-and-operators-9.png)

* Here is an example of exponent notation.
* For example, `2.999e8` means `2.999*10^8`.
* For example, `2.999e-8` means `2.999*10^-8`.

![./20170404-0144-cet-values-types-and-operators-10.png](./20170404-0144-cet-values-types-and-operators-10.png)

![./20170404-0144-cet-values-types-and-operators-11.png](./20170404-0144-cet-values-types-and-operators-11.png)

* For number with infinite amount of trailing numbers behind comma, like for example pi.
* The ideal case would be an approximation.
* So, programmers need to be careful when dealing with decimal numbers. The best is to make an approximation of those numbers.

![./20170404-0144-cet-values-types-and-operators-12.png](./20170404-0144-cet-values-types-and-operators-12.png)

* Operators are most of the time is a symbol.
* Mathematics operator like `+`, `-`, ....
* There are these kinds of operator.

![./20170404-0144-cet-values-types-and-operators-13.png](./20170404-0144-cet-values-types-and-operators-13.png)

* Each operators in any programming language has its own order of magnitude.
* The larger the more priority it has over the lower ones.
* If there are operators with same priority the left will be executed first.
* These all means the basic mathematics equation on which one should be calculated first addition or multiplication.

![./20170404-0144-cet-values-types-and-operators-14.png](./20170404-0144-cet-values-types-and-operators-14.png)

* So when designing a statement you need to make sure the order of the operators you would like to happen first.
* Then, assign bracket appropriately.
* Actually, just try to put everything in bracket for you to make sure that the operator will happen after the others.

![./20170404-0144-cet-values-types-and-operators-15.png](./20170404-0144-cet-values-types-and-operators-15.png)

* There is `infinity` and `-infinity` to represent positive and negative infinity.
* Anything happen to `infinity` will still be `infinity`, perhaps the negative or the positive change. There are these examples.
    * `infinity + 1` is still `infinity`.
    * `infinity - 1` is still `infinity`.
    * However, I am still not sure on what will be for `infinity/-infinity`. Will this be `-1`?
* These numbers are not mathematically solid.
* Do not use this, if possible.
* There are little to no use for the programmer to use this, but if this comes from a result of a calculation.

![./20170404-0144-cet-values-types-and-operators-16.png](./20170404-0144-cet-values-types-and-operators-16.png)

![./20170404-0144-cet-values-types-and-operators-17.png](./20170404-0144-cet-values-types-and-operators-17.png)

* `NaN` is stand for "not a number".
* `NaN` is used to represent a result that is not meaningful.
* These are an example of operations those will return null.
    * `0/0` will return `NaN`.
    * `Infinity - Infinity` will return `NaN`.
* Any operation that is not meaningful will return as a `NaN` in JavaScript.
    * In other programming language this could be a Math error.
    * This is actually the thing that I do not like from JavaScript.
    * `NaN` does not return error. So, sometimes it is hard to debug a mathematical based animation.

![./20170404-0144-cet-values-types-and-operators-18.png](./20170404-0144-cet-values-types-and-operators-18.png)

* Newlines is what it is when you press Enter key in your keyboard while typing something.
* String (or text) in JavaScript should be put in a line.
* You cannot put a line break in a string directly by pressing Enter.
* Instead you should use `\n` to imply line break to the JavaScript interpreter.

![./20170404-0144-cet-values-types-and-operators-19.png](./20170404-0144-cet-values-types-and-operators-19.png)

* Escaping character is a character that will not be included in the quoted text (string).
* In JavaScript or any general programming language (Python included) the escaping character is `\`.

![./20170404-0144-cet-values-types-and-operators-20.png](./20170404-0144-cet-values-types-and-operators-20.png)

* Above are examples of escaping character to incites line break as well as string operation.
* There is only one operator that can be used to do string operator which is `+`.
* `+` if there are at least one parameter is a string. Then type coercion will happen. This, will make the whole operation to be string concatenation.

![./20170404-0144-cet-values-types-and-operators-21.png](./20170404-0144-cet-values-types-and-operators-21.png)

![./20170404-0144-cet-values-types-and-operators-22.png](./20170404-0144-cet-values-types-and-operators-22.png)

![./20170404-0144-cet-values-types-and-operators-23.png](./20170404-0144-cet-values-types-and-operators-23.png)

![./20170404-0144-cet-values-types-and-operators-24.png](./20170404-0144-cet-values-types-and-operators-24.png)

* Unary operation is an operation that take one parameter.
* Usually unary operation takes the right side of th operator to be its parameter.
* Whereas binary operation takes what it is in the left and the right of the operator.
    * For example, `1 + 2` is a binary operator.
    * That operation will take `1` and `2` as its parameter.
* An example of unary operation is `typeof` which to return a string of the parameter's type data.
* Another example of unary operation is `-` and `!`. These are use to inverse numbers and boolean respectively.

![./20170404-0144-cet-values-types-and-operators-25.png](./20170404-0144-cet-values-types-and-operators-25.png)

![./20170404-0144-cet-values-types-and-operators-26.png](./20170404-0144-cet-values-types-and-operators-26.png)

* Here are another example of binary operator.
* This time this is a operator for comparison.
* Comparison operator will return a boolean value (whether it is `true` or `false`).

![./20170404-0144-cet-values-types-and-operators-27.png](./20170404-0144-cet-values-types-and-operators-27.png)

![./20170404-0144-cet-values-types-and-operators-28.png](./20170404-0144-cet-values-types-and-operators-28.png)

![./20170404-0144-cet-values-types-and-operators-29.png](./20170404-0144-cet-values-types-and-operators-29.png)

* From the above paragraph, I know that string can also be compared.
* Every character has its own Unicode and string comparison will compare between these Unicode.
* Good thing to mention is that lower case is larger than upper case.
* For example, `a > Z` will return `true`.
* The Unicode standard applied to any symbol you see in your computer.
* These includes Arabic, Chinese, Cyrillic, Japanese, ....
* When comparing string, JavaScript goes from the left to right and go step - by - step in increasing index.

![./20170404-0144-cet-values-types-and-operators-30.png](./20170404-0144-cet-values-types-and-operators-30.png)

* `NaN == Nan` will be false, although both value is the same.
* `NaN` is the only value in JavaScript that will return `false` when compared to itself.

![./20170404-0144-cet-values-types-and-operators-31.png](./20170404-0144-cet-values-types-and-operators-31.png)

* `NaN`, in JavaScript, is used to determine the result of nonsensical computation.
* And as such it does not equal to other nonsensical results.

![./20170404-0144-cet-values-types-and-operators-32.png](./20170404-0144-cet-values-types-and-operators-32.png)

* Unary operation `!` or not, is used to flip the value of boolean.
* For example, `!false` will be `true`.

![./20170404-0144-cet-values-types-and-operators-33.png](./20170404-0144-cet-values-types-and-operators-33.png)

* Knowing all the operation.
* The most important thing when programmer tries to make a statement is to take care which one is more operators has more priority then the other.
* For example this below is a valid JavaScript operation.

```markdown
1 + 1 == 2 && 10 * 10 > 50
```

* The programmer needs to define which operators will happen first.
* Otherwise, to make sure and for safety you can also bind the operators and the parameters in a brackets of `()`.

![./20170404-0144-cet-values-types-and-operators-34.png](./20170404-0144-cet-values-types-and-operators-34.png)

* So, based on above paragraph.
* Mathematical operations will happen first.
    * So these means all of those, `%`, `*`, `+`, `-`, `/`.
        * But each has its own priority that otherwise will be taken from left to right.
        * For example `*` will happen first, then `-`.
    * The next priority is those comparison operator: `>`, `<`, `>=`, `<=`, `==`, `!=`, `===`, `!==`.
    * Then "and" operation `&&`.
    * Then "or" operation `||`.

![./20170404-0144-cet-values-types-and-operators-35.png](./20170404-0144-cet-values-types-and-operators-35.png)

* There is only one ternary operation in JavaScript which is used for conditional value assignment.
* Ternary operation is operation that takes 3 parameters.
* These are the examples.

```markdown
console.log(true ? "hello" : "world") // Will print "hello" in the console.
console.log(false ? "hello" : "world") // Will print "world" in the console.
```

![./20170404-0144-cet-values-types-and-operators-36.png](./20170404-0144-cet-values-types-and-operators-36.png)

* The previous point is a conditional operation.
* The value on the left of the question mark will assign a boolean comparison.
* The value on the left of ":" will be assigned if the boolean comparison is `true`.
* The value on the right of ":" will be assigned if the boolean comparison is `false`.

![./20170404-0144-cet-values-types-and-operators-37.png](./20170404-0144-cet-values-types-and-operators-37.png)

![./20170404-0144-cet-values-types-and-operators-38.png](./20170404-0144-cet-values-types-and-operators-38.png)

* Many operation in JavaScript do not produce meaningful value.
* In JavaScript this will be shown as `null` or `undefined`.

![./20170404-0144-cet-values-types-and-operators-39.png](./20170404-0144-cet-values-types-and-operators-39.png)

![./20170404-0144-cet-values-types-and-operators-40.png](./20170404-0144-cet-values-types-and-operators-40.png)

* `null` and `undefined` are an accident during the JavaScript development.
* __In most of the time these values do not matter.__
* But for me, I define `undefined` as if I have a variable but I have not yet to put a value in it.
* `null` will be used to define an "empty" variable that used to have value.

![./20170404-0144-cet-values-types-and-operators-41.png](./20170404-0144-cet-values-types-and-operators-41.png)

* I you have concern on the operator's priority, then it is the best solution to have each operations within a bracket. Thus, you can assign the priority properly.

![./20170404-0144-cet-values-types-and-operators-42.png](./20170404-0144-cet-values-types-and-operators-42.png)

![./20170404-0144-cet-values-types-and-operators-43.png](./20170404-0144-cet-values-types-and-operators-43.png)

* Example of automatic type conversion in JavaScript.
* This is what it means to be programming/scripting language with type coercion.

![./20170404-0144-cet-values-types-and-operators-44.png](./20170404-0144-cet-values-types-and-operators-44.png)

* When something does not mapped properly to a number or a boolean in an obvious way, a `NaN` will be the result.
* For example, `"five" - "four"` will be `NaN` (I think, I have not yet try this, in any cases I hope you get my point).

![./20170404-0144-cet-values-types-and-operators-45.png](./20170404-0144-cet-values-types-and-operators-45.png)

* So overall, in case JavaScript programmer find a `NaN` bug, they need to see on potential type coercion.
* Usually `NaN` happen because of division by 0 or unwanted type coercion.

![./20170404-0144-cet-values-types-and-operators-46.png](./20170404-0144-cet-values-types-and-operators-46.png)

![./20170404-0144-cet-values-types-and-operators-47.png](./20170404-0144-cet-values-types-and-operators-47.png)

![./20170404-0144-cet-values-types-and-operators-48.png](./20170404-0144-cet-values-types-and-operators-48.png)

![./20170404-0144-cet-values-types-and-operators-49.png](./20170404-0144-cet-values-types-and-operators-49.png)

![./20170404-0144-cet-values-types-and-operators-50.png](./20170404-0144-cet-values-types-and-operators-50.png)

![./20170404-0144-cet-values-types-and-operators-51.png](./20170404-0144-cet-values-types-and-operators-51.png)

* Type coercion exists when comparing values.
* Example of valid type coercion within comparison operator.
    * `"" == false` will return `true`.
    * `0 == false` will return `true`.
    * `NaN == false` will return `true`.
    * `null == 0` will return `true`.
    * `null == undefined` will return `true`.
* You can use comparison to know if your data is valid.
* For example, you can use `"" == false` to check the validity of string.

![./20170404-0144-cet-values-types-and-operators-52.png](./20170404-0144-cet-values-types-and-operators-52.png)

![./20170404-0144-cet-values-types-and-operators-53.png](./20170404-0144-cet-values-types-and-operators-53.png)

![./20170404-0144-cet-values-types-and-operators-54.png](./20170404-0144-cet-values-types-and-operators-54.png)

* In order to prevent type coercion when comparing value, in JavaScript you can use `===` or `!==`.
* Both operators are binary operator.
* Both operators mean as a strict comparison operator.

![./20170404-0144-cet-values-types-and-operators-55.png](./20170404-0144-cet-values-types-and-operators-55.png)

* It is recommended in JavaScript to have all comparison to be in strict comparison.
* So you are sure that both type and the value are the same (or not).

![./20170404-0144-cet-values-types-and-operators-56.png](./20170404-0144-cet-values-types-and-operators-56.png)

* Be careful, in JavaScript there are comparison operator that can act as a value validator.
* These operators are `||` and `&&`.
* The `||` is used to take the left parameter if the left parameter is valid and take the right parameter if the left parameter is invalid.
* I would call the `||` as a left valid checker.

![./20170404-0144-cet-values-types-and-operators-57.png](./20170404-0144-cet-values-types-and-operators-57.png)

* This technique is called "short - circuiting logical operator".

![./20170404-0144-cet-values-types-and-operators-58.png](./20170404-0144-cet-values-types-and-operators-58.png)

* The `&&` is a left invalid checker.
* The `&&` will check left parameter is invalid then return that value.
* For both `||` and `&&` will try to return the left value if the left value satisfy the condition.

![./20170404-0144-cet-values-types-and-operators-59.png](./20170404-0144-cet-values-types-and-operators-59.png)

* If the condition is satisfied already, then there will be no check on the right parameter.

![./20170404-0144-cet-values-types-and-operators-60.png](./20170404-0144-cet-values-types-and-operators-60.png)

* The conditional operator (the only ternary operation JavaScript has) works in similar way.
* The first value is checked if it it true than the operation end without checking another value.

![./20170404-0144-cet-values-types-and-operators-61.png](./20170404-0144-cet-values-types-and-operators-61.png)

* Value in JavaScript is inferred by typing its name directly.
* For example, `true`, `null` or the arbitrary values, like `13` or `"abc"`.
* You can combine or transform value with operator.
* Learning what operators are available is a crucial part when learning a programming/scripting language.

![./20170404-0144-cet-values-types-and-operators-62.png](./20170404-0144-cet-values-types-and-operators-62.png)

![./20170404-0144-cet-values-types-and-operators-63.png](./20170404-0144-cet-values-types-and-operators-63.png)

* The conclusion for this chapter.