# Brainfuck++
There is no reason to ignore `Brainfuck` language as a phenomen. It is a bright example of a minimalistic approach in terms of interpret creation. But, why we're not able to improve `Brainfuck` in the same way how `C++` has improved `C`? </br>
I mean, this language almost ideal, but to make it perfect, in my opinion, we need to add something like `functions` or/and `labels`.

# Why?
This is an interesting task to implement some changes in `Brainfuck` with respect to the source syntax and the source idea of language and the interpreter.

# New 'syntax'
The list of new items is below:
- `^` - jump operator.
- `&` - call operator.
- `$` - call return value load.
- `!` - terminate operator.
- `#` - argument load operator.
- `*` - reset operator.
- `/` - comment symbol.

## Labels
To create a label, put in the code any 'non' registered alphabet symbol. For example:
```brfkpp
++++++++^gf[>+++++++>++++++++++>+++>+<<<<-]g^f>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>>+.>.
```

You can use jump to labels with the `^` command.
```brfkpp
^<label_char>
```

Note: Label can be presented before and after the jump instruction.

## Functions
Any label can be called as a function. The difference - Function argument scope. Functions can use arguments stack thru `#` operators. For example:
```brfkpp
/ To load the first argument in the function 
  to the current cell /
#0

/ To load the current cell value to the 
  first argument /
+++++0
```

Now, to call a function, we must use the `&` operator:
```brfkpp
/ Function to print a character.
  Params:
  - [0] Character number.
   /
^q
w
  #0            / load the base offset      /
  >++++++++     / In the second cell set 8  /
  [
      <++++++++ / + 8 to the base offset    /
      >-
  ]
  <.            / stdout                    /
!               / return                    /
q

*++0   / B       /
&w     / w('B'); /
```

Note: In comparison with the label, a function must have the `!` operator. This operator returns us to the place, where a function was invoked. </br>
Note 2: Functions have their own tape and tape position. That means, you can't use the same tape in different functions. THe one way to send values between functions and the main process is the `#` arg load operator and the `$` call return load operator. </br>
The `$` operator works in the next way: If it called after a function call, it loads the return value into the current cell. </br>
Note 3: The return value of a function is a value from the current cell in function at the moment before the `!` encounter. 

## Reset operator
Reset operator merely sets the current tape value to zero.
