Norvig
======

Selected quotes, tips, and maxims from the master, [Peter Norvig](http://norvig.com).

* [CS212](https://www.udacity.com/course/cs212)

* [AIMA](http://aima.cs.berkeley.edu/)


## General Advice

To solve a problem, describe it, specify it in algorithmic terms, implement it, test it, debug and analyze it. Expect this to be an iterative process.

Practice exploratory programming, where the aim is to discover more about the problem area. 

Use the most natural notation available to solve a problem.

Familiarize yourself with the ~ 25 major data types.


## Patterns and Practices

Use the same data for several programs.

Use data-driven programming, where pattern/action pairs are stored in a table.

Whenever you develop a complex data structure, develop a corresponding consistency checker.

Translate inputs to a canonical form.

The iterative development process:

1. develop a minimal viable product for your problem 
2. test and instrument
3. optimize
4. iterate

The four general optimization techniques:

1. caching / memoization
2. compiling
3. delaying computation
4. indexing

The first two can yield 100-fold speed-ups.

The simplest compiler need not be much more complex than an interpreter.

Additional efficiency techniques:

* try to use declarations and the right data structures
* try to avoid generic functions and complex argument lists

The expert programmer eventually develops a good "efficiency model".

Search strategies:

The strategy you use to search for a sequence of good moves can be important.

You can compare two different strategies for a task by running repeated trials of the two. 


## Adaptive Systems

Architect systems in which ...

* programmers specify initial architecture, specs

* the system can improve from both implicit and explicit user feedback
  * let users vote/rank (reinforcement learning)
  * let users correct (supervised learning)

* the system can anticipate the user's context and goals

In other words, you want to architect systems that incorporate and are informed by performance feedback.


## Logic Programming

LP relies on three important ideas: 

* a uniform data base
* logic variables
* automatic backtracking

Logic programs have a simple way to express grammars.

Rule-based translation is a powerful idea, however sometimes you need more efficiency, and need to give up the simplicity of a rule-based system


## Design Patterns

Design patterns are ...

* descriptions of what experienced designers know

* hints/reminders for choosing classes and methods

* higher-order abstractions for program organization

* a vocabulary for deliberating design tradeoffs

* used to avoid limitations of implementation languages

Design patterns can be used informally, or can be abstracted into a formal function, macro, or data type (often involving higher-order functions).

From a Lisp perspective the various GOF patterns can be thought of as implementing first-class types (state, proxy), first-class functions (visitor, iterator), macros (interpreter), method combination (mediator, observer), multimethods (builder), and modules (facade).


## Lisp

There is a myth that Lisp is a "special prupose language, while a language like C is "general purpose".  The reverse is true.  C-like languages are designed for manipulating the registers and memory of a von Neumann-style computer.  The majority of their syntax is devoted to arithmetic and Boolean expressions, and while they provide some facilities for forming data structures, they have poor mechanisms for procedural abstraction or control abstraction. In addition, they are designed for the state-oriented style of programming: computing a result by changing the value of variable through assignment statements.

Lisp provides all you need for programming in general: defining data structures, functions, and the means for combining them.  It's flexible enought to support any programming style: imperative, declarative, or functional.

Lisp's flexibility allows it to adapt as programming styles change, but more importantly, Lisp can adapt to your particular programming problem. In other languages you fit your problem to the language; with Lisp you extend the language to fit your problem.

Lisp is ideal for exploratory programming.

[SICP](http://mitpress.mit.edu/sicp/) is probably the best introduction to computer science ever written.

The truly amazing, wonderful thing about [call/cc](http://en.wikipedia.org/wiki/Call-with-current-continuation) is the ability to return to a continuation point more than once.
