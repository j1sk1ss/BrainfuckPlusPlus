# Brainfuck++
There is no reason to ignore `Brainfuck` language as a phenomen. It is a bright example of a minimalistic approach in terms of interpret creation. But, why we can't to improve `Brainfuck` in the same way how `C++` has improved `C`? I mean, this language almost ideal, but to make it perfect, in my opinion, we need to add something like `functions`, `labels` and `if` statements.

# Why?
This is an interesting task to implement some changes in `Brainfuck` with respect to the source syntax and the source idea of language and the interpreter.

# New 'syntax'
The list of new items is below:
- `^` - jump operator.
- `?` - condition operator.
- `&` - call operator.
- `!` - terminate operator.

## Labels
To create a label, put in the code any 'non' registered symbol. For example, use an alphabet character:
```brfkpp
++++++++^gf[>+++++++>++++++++++>+++>+<<<<-]g^f>++.>+.+++++++..+++.>++.<<+++++++++++++++.>.+++.------.--------.>>+.>.
```

You can use jump to labels with the `^` command.
```brfkpp
^<label_char>
```

Note: Label can be presented before and after the jump instruction.

## 'If' statement
'?' operator follows with two labels:
```brfkpp
?<label_1><label_2>
```
