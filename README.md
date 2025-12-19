# Monkey Interpreter in Go

A Go implementation of the Monkey programming language interpreter.

## About

This project implements an interpreter for the Monkey programming language, following the principles from "Writing An Interpreter In Go" by Thorsten Ball. Monkey is a simple, C-like programming language designed for learning about interpreters and language implementation.

## Features

### Currently Implemented

- **Lexer**: Tokenizes Monkey source code into a stream of tokens
- **REPL**: Interactive Read-Eval-Print Loop for experimenting with the language
- **Token Support**: Recognizes identifiers, integers, operators, keywords, and delimiters

### Supported Tokens

**Operators**: `=`, `+`, `-`, `!`, `*`, `/`, `<`, `>`, `==`, `!=`

**Delimiters**: `,`, `;`, `(`, `)`, `{`, `}`

**Keywords**: `fn`, `let`, `true`, `false`, `if`, `else`, `return`

**Literals**: Integers, identifiers

## Installation

Ensure you have Go 1.25.0 or later installed.

```bash
# Clone the repository
git clone https://github.com/jordanglean/MonkeyInterpreterGo.git
cd MonkeyInterpreterGo

# Build the project
go build

# Run the REPL
./MonkeyInterpreterGo
```

## Usage

### REPL

Run the interpreter to start the REPL:

```bash
go run main.go
```

You'll be greeted with a prompt where you can type Monkey code:

```
Hello <username>! This is the Monkey programming language!
Feel free to type in commands
>>
```

Currently, the REPL outputs tokens for the code you type:

```
>> let x = 5;
{Type:LET Literal:let}
{Type:IDENT Literal:x}
{Type:= Literal:=}
{Type:INT Literal:5}
{Type:; Literal:;}
```

## Project Structure

```
.
├── main.go           # Entry point and REPL startup
├── token/            # Token type definitions
│   └── token.go
├── lexer/            # Lexical analysis
│   ├── lexer.go
│   └── lexer_test.go
└── repl/             # Read-Eval-Print Loop
    └── repl.go
```

## Testing

Run the tests:

```bash
go test ./...
```

## Roadmap

This interpreter is a work in progress. Future implementations may include:

- Parser for building Abstract Syntax Trees (AST)
- Evaluator for executing Monkey code
- Support for more complex data types (strings, arrays, hash maps)
- First-class functions and closures
- Built-in functions

## Example Monkey Code

While parsing and evaluation aren't yet implemented, here's what Monkey code looks like:

```monkey
let age = 1;
let name = "Monkey";
let result = 10 * (20 / 2);

let myArray = [1, 2, 3, 4, 5];
let myHash = {"name": "Monkey", "age": 0};

let add = fn(a, b) { return a + b; };

if (age > 0) {
    return true;
} else {
    return false;
}
```

## License

This is a learning project.

## Acknowledgments

This implementation is based on the book "Writing An Interpreter In Go" by Thorsten Ball.
