---

layout: default

---

# Atoms, Auras, and Simple Cell Types

Like most modern high-level programming languages, Hoon has a type system. Because Hoon is a functional programming language, its type system differs somewhat from those of non-functional languages. In the next few lessons we'll go over Hoon's type system and point out some of its distinctive features. Certain advanced topics (e.g. type polymorphism) won't be addressed until a later chapter.

A type is ordinarily understood to be a set of values. Examples: the set of all atoms is a type, the set of all cells is a type, and so on.

Type systems provide type safety, in part by making sure functions produce values of the correct type. When you write a function whose product is intended to be an atom, it would be nice to know that the function is guaranteed to produce an atom. Hoon's type system provides such guarantees with type checking and type inference.

## Brief Overview of the Next Few Lessons

In order to have a solid foundational knowledge of Hoon's type system, you must understand: (1) precisely what kind of information is tracked by Hoon's type system, (2) what a type check is and where they occur, (3) what type inference is and how it works, and (4) how to build your own custom types.

In this lesson we'll cover (1)-(4) as they pertain to atoms and simple cell types. In the next lesson (2) and (3) will be addressed as they pertain to complex expressions of Hoon. In the lesson after that you'll learn more about (4), for building more complex types.

### Atoms and Auras

In lesson 1.2 we defined what an atom is: any unsigned integer. In this lesson we'll expand on that discussion, going over how Hoon's type system implements auras.

In the most straightforward sense, atoms simply are unsigned integers. But they can also be interpreted as representing signed integers, ASCII symbols, floating-point values, dates, binary numbers, hexadecimal numbers, and more. Every atom is, in and of itself, just an unsigned integer; but Hoon keeps track of type information about each atom, and this info tells Hoon how to interpret the atom in question.

The piece of type information that determines how Hoon interprets an atom is called an aura. The set of all atoms is indicated with the symbol @. An aura is indicated with @ followed by some letters, e.g., @ud~11.29.18 ~ridlur-figbud for unsigned decimal. Accordingly, the Hoon type system does more than track sets of values. It also tracks certain other relevant metadata about how those values are to be interpreted.

#### Just another title chilling out

How is aura information generated so that it can be tracked? One way involves type inference. In certain cases Hoon's type system can infer the type of an expression using syntactic clues. In the most straightforward case of type inference, the expression is simply data as a literal. Hoon recognizes the aura literal syntax and infers that the data in question is an atom with the aura associated with that syntax.

To see the inferred type of a literal expression in the dojo, use the ? operator. (Note: this operator isn't part of the Hoon programming language; it's a dojo-only tool. It's a very useful tool for learning about types in Hoon, however.)

## Continuing with this stuff

### Down one level of hierarchy, I love it !

In order to have a solid foundational knowledge of Hoon's type system, you must understand: (1) precisely what kind of information is tracked by Hoon's type system, (2) what a type check is and where they occur, (3) what type inference is and how it works, and (4) how to build your own custom types.

#### Perhaps we might use a title like this?

In this lesson we'll cover (1)-(4) as they pertain to atoms and simple cell types. In the next lesson (2) and (3) will be addressed as they pertain to complex expressions of Hoon. In the lesson after that you'll learn more about (4), for building more complex types.

#### And another, not very far apart like so

In this lesson we'll cover (1)-(4) as they pertain to atoms and simple cell types. In the next lesson (2) and (3) will be addressed as they pertain to complex expressions of Hoon. In the lesson after that you'll learn more about (4), for building more complex types.

### Atoms and Auras

In lesson 1.2 we defined what an atom is: any unsigned integer. In this lesson we'll expand on that discussion, going over how Hoon's type system implements auras.

In the most straightforward sense, atoms simply are unsigned integers. But they can also be interpreted as representing signed integers, ASCII symbols, floating-point values, dates, binary numbers, hexadecimal numbers, and more. Every atom is, in and of itself, just an unsigned integer; but Hoon keeps track of type information about each atom, and this info tells Hoon how to interpret the atom in question.

The piece of type information that determines how Hoon interprets an atom is called an aura. The set of all atoms is indicated with the symbol @. An aura is indicated with @ followed by some letters, e.g., @ud~11.29.18 ~ridlur-figbud for unsigned decimal. Accordingly, the Hoon type system does more than track sets of values. It also tracks certain other relevant metadata about how those values are to be interpreted.

#### Just another title chilling out

How is aura information generated so that it can be tracked? One way involves type inference. In certain cases Hoon's type system can infer the type of an expression using syntactic clues. In the most straightforward case of type inference, the expression is simply data as a literal. Hoon recognizes the aura literal syntax and infers that the data in question is an atom with the aura associated with that syntax.

To see the inferred type of a literal expression in the dojo, use the ? operator. (Note: this operator isn't part of the Hoon programming language; it's a dojo-only tool. It's a very useful tool for learning about types in Hoon, however.)