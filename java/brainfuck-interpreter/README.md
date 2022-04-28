### Java - Brainfuck interpreter

#### About

[Brainfuck](https://en.wikipedia.org/wiki/Brainfuck) is an esoteric programming language comprised of 8 single-letter commands; this class is an interpreter for Brainfuck that implements all 8 commands.

#### CLI
###### Arguments
- `"<brainfuck>" "[input]"`

###### Input
Input is taken from STDIN (`System.in`) if no input is provided.

#### API
- `exec()` - No input provided. Throws `IllegalArgumentException` if code recieves input.
- `exec(String input)` - Takes input from the provided `String`. Throws `NoSuchElementException` if input is not sufficient.
- `exec(InputStream inputSource)` - Takes input from the provided `InputStream`.

#### Limitations

- Memory is limited to 256 cells to store the pointer within a single byte.
- Nested loops are limited to 256 loops. This can be increased or removed if necessary.

#### Sample code

###### Hello World
```brainfuck
++++++++[>+++++++++>++++++++++++>++++++++++++++>++++>+++++++++++<<<<<-]>.>+++++.>----..+++.>.>-.<<.+++.------.<-.>>+.
```

###### Dice Roll Guess game
Minified version of [`bf/dice-roll-guess`](/bf/dice-roll-guess/):
```brainfuck
++++++++[>++++++++>++++++++++++++>++++++++++++>++++++++++++++>++++++++++++++>++++>++++>++++>+++++>++++++>+++++>++++++>+++++>++++>++++++++>+++++++++++++++>++++>++++++++++>+++++++++++++>++++++++++++>++++++++++++++>+++++++++++>++++++++>++++++++++++++>+++++++++++++++>+++++++>++++++>++++++<<<<<<<<<<<<<<<<<<<<<<<<<<<<-]>+++++++>+++++>+++++>+++>+++>>+++>>>+>+++++>++++++>+>>++>+>>++++>>+>++++>+++++++>+++++++>+++++>+>+>+++++++>+++++++[<]>[.>]>+>>++++++++[>++++++>>+>++++++++>++++++++++++++>++++++++++++>++++++++++++++>++++++++++++++>+++++++>++++>>++++++++>+++++++++>+++++++++++++>++++++++++++>>+++++++++++++>++++++++++++++>++++++++++++++>++++++++++++>++++++++++++>++++++++++++++<<<<<<<<<<<<<<<<<<<<<<-]+>++++>>++>+++++++>+++++>+++++>+++>+++>++>>>+++>+>++++++>+++>>+++++++>++>++>+++++>+++>++++[<]<[<]<[<]<<<<[>>>>>[.>]<[<]<<<,>>[>+<-]>[<<<->>+>-]<<<[[-]>->>>.[>]>>[.>]>[.>]<[<]<[<]<[<]<<<]>[>>>.[>]>.[>]>[.>]<[<]<[<]<[<]<<<<->]+<<]
```

#### Todo

- Remove loop restrictions
- Make memory dynamic

#### Notes

Thanks to Anurag for helping with receiving input and Shinra for inspiring me to make this, both on the [Java Community Discord](https://discord.gg/java).
This project is a continuation of [`bf/dice-roll-guess`](/bf/dice-roll-guess/).