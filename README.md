[Untitled Fractal Project] Proposal
=============

*September 30, 2015*

Team
-------------
- **Manager** Anne Zhang, az2350
- **Language Guru** Calvin Li, ctl2124
- **Systems Architect** Justin Chiang, jc4127
- **Tester** Kunal Kamath, kak2211

Description
-------------
Our language enables the user to generate fractals in the Graphics Interchange Format, commonly abbreviated as GIF. Specifically, the user should be able to program a fractal using a formal grammar.

We define our fractal-generating grammars as:
```
    G = (init, rules)
```
where

- **init**: a string that defines the initial state of the system
- **rules**: a set of rules that defines the way variables are replaced with combinations of variables and movements during the recursion. Each rule has two halves to it, separated by an arrow (→). There are two types of rules: recursive rules, which point to a string, and terminal rules, which point to a move() function.

Syntax
-------------
### Declaration/Assignment
Variables are declared and assigned in the same syntax as C.
```
    int a;
    a = 0;
    int b = 1;
```

### Data Types
- **int**: an integer of 32 bits
- **double**: a floating point number of 64 bits
- **bool**: a true or false value
- **string**: a collection of characters/symbols
- **rule**: a standard object composed of 2 fields
 - a *predecessor* string and
 - a *successor* string or move() function
- **gram**: a standard object composed of three fields
 - an *init* string
 - a second set called *rules*

e.g. Consider the following grammar declaration for constructing a fractal:

```
    gram G {
        init: ‘X’,
        rules: { ‘X’ → ‘X up X down X’,
                 ‘up’ → move(90, 1),
                 ‘down’ → move(-90, 1),
                 ‘X’→ move(0, 1)
        }
    }
```

### Structures
**primitive**: fundamentally built into the language
**object**: Javascript-like object with (key, value)
**set**: unordered collection of objects or other data types

### Operators
Mathematical and logical operators are the same as in C (e.g. + - * /, && ||, < > ==).

### Control Flow
If/else statements, while loops, and for loops are the same as in Java.

### Functions
Functions have return values and parameters. They are defined with the keyword “func”, followed by the function name, parameters in parentheses, and brackets.
```
    func add(a, b) {
        return a + b;
    }
```

### Built-in Functions
- **move** (int theta, int len) - draws a line of length len at an angle of theta
- **draw** (lsys L) - generates a static fractal image
- **grow** (lsys L) - generates a gif of the fractal being created
- **zoom** (lsys L) - generates a (seemingly infinite) zooming gif of the fractal

### Comments
Just like in Java, // for single line and /* */ for multi line comments.

Proposed Applications
-------------
Mathematicians and curious math students who wish to visualize fractals and interesting iterative shapes can do so with minimal programming experience with our language. The GIFs created by our language can be shared easily, so that the wonder of fractals can spread!

Sample Programs
-------------

### Recursive Fibonacci algorithm
```
    func fib(int n) {
        if(n == 0 || n == 1) {
            return n;
        }
        return fib(n-1) + fib(n-2);
    }
```
