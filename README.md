# Brainfuck++

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

## If statement
'?' operator follows with two labels:
```brfkpp
?<label_1><label_2>
```

