---
lang: en
title: The Daily PL - Programming Paradigms
viewport: width=device-width, initial-scale=1.0
---

<div class="show-content user_content clearfix enhanced">

# The Daily PL - Programming Paradigms

### What's News

The pragmatic programmers Paradigmalandia have declared independence
from their academic backers. The leaders of the programming language
research refuse to accept defeat and are planning to wage a war of
reunification. Both sides share a battle cry: "Remember the OO!" Read on
for more.

### Programming Paradigms

1.  A *paradigm* is a pattern or model. A *programming paradigm* is a
    pattern of problem-solving thought that underlies a particular genre
    of programs and languages. Traditionally, computer scientists have
    classified programming languages (according to their *syntax*,
    *names and types*, and *semantics*) into one of four categories:
    imperative (aka, procedural), object oriented, functional and logic
    (alias *declarative*). More and more, however, computer scientists
    believe that it is a fools errand to try to classify modern
    programming languages because these languages take the best of all
    four paradigms. More on that later.

#### Imperative/Procedural

Imperative languages were the first programming languages to be
designed. They came about in an age where hardware cost much more than
programmers. In other words, the goal of these programming languages was
to make it possible to harness as much power from the computer as
possible. Therefore, the programming languages' constructs for
describing algorithms were just a thin wrapper over the underlying
hardware architecture. Remember that the hardware, then *and* now, was
built using the von Neumann model. You can see this by mapping the
central semantic elements of an imperative programming language to
corresponding elements of the hardware:

1.  The assignment statement/expression is akin to the pipeline between
    the processor and the memory;
2.  Variables are simply thin abstractions over the memory; and
3.  Sequences of instructions (interrupted with conditionals, etc) are a
    close approximation of the Fetch, Decode, Execute cycle that the CPU
    repeats ad infinitum.

The assignment statement/expression is tightly related to another
hallmark of programs written in imperative/procedural programs:
imperative/procedural programs have *state*: The contents of the memory
at a particular point during execution. An assignment
statement/expression changes the state of the program. Think about how
state makes it difficult (if not impossible) to completely enclose (for
lack of a better word) functionality in one self-contained unit.

Imperative languages use conditionals, sequences, loops and functions as
their *combining forms*. A combining form is just a phrase that
describes how more than one of a language's basic semantic elements can
be grouped together with others to build code that performs an action
that cannot be completed by one of those single elements.

As a token gift to the programmer to make their life easier,
imperative/procedural programs offer *process abstraction* in the form
of functions/procedures.

The most famous purely imperative/procedural programming languages are
Fortan, Cobol, C and Pascal.

#### Object Oriented

Once hardware costs began to drop, the dominant cost of writing software
shifted from the hardware to the software and, by extension, to the cost
of employing developers to write that software. Programmers began
thinking about ways to make programmers more efficient and began to rely
on abstractions around data. The focus on *data abstraction* as a means
of organizing software projects culminated with the development of
object-oriented programming languages. At their core, object-oriented
programming languages are defined by their reliance on *encapsulation*
of data together with the code that operates on that data. Each entity
(*object*) in an object-oriented programming language is responsible for
maintaining its internal data and modifying it according to the user's
requests.

The data contained by an object is hidden (*data hiding*). Users of an
object can access  internal, hidden data and/or manipulate that data by
sending the objects *messages*. *Message passing* is the way that a user
accesses (views) an object's internal data or instructs an object to
manipulate its internal data. Data hiding gives the object implementer
the ability to change the way that the data is represented internally
(for expansion, performance or, really, any reason) without having to
change the code of software that interacts with it. As long as the
object continues to respond to messages the same way that it always has,
then it can represent its data internally however it chooses. Cool!

Objects in an object-oriented programming language can be arranged to
form a hierarchy. The descendants of an object are related (somehow) to
their parents. Descendants can, in turn, be the parents of another
object. Descendant objects *inherit* the functionality of objects from
which they descend! Those objects can simply reuse the functionality of
their parents *or* modify (even if slightly) the functionality. This
technique provides a powerful method for reusing code -- another way to
help the programmer improve their efficiency.

But, if every object can (re)implement the methods of its parents, then
the language needs a mechanism to determine which version of a given
function to call at a given time. For example, if my function expects to
be invoked with a Car object, valid arguments may be a Tesla object, a
Ford object, or a Rivian object. Which implementation of a `start`
message handler should be invoked? That decision is made at runtime in a
process known as *dynamic binding*. Dynamic binding is also known as
*runtime polymorphism*.

Object-oriented programming languages are not a complete break from
imperative/procedural programming languages. They also have loops,
conditionals, sequences and functions.

Well-known object-oriented programming languages include C++, Java,
Smalltalk, and Ruby.

#### Functional

Now for something entirely different! (First, let's assume that we are
only talking about *pure* functional programming languages -- we will
talk about the distinction between pure and impure functional
programming languages in more depth when we come to that module.)

In programs written in functional programming languages functions are
*first class objects*. That means that functions can be stored in
variables, passed to functions and even*, gasp*, returned from
functions!Basically, functions in a functional programming language are
just like `int`s, <sub>std::string</sub>s and `bool`s in C++.

What's more mind bending is that in a program written in a *pure*
functional programming language, there is no state! Are you kidding? No,
it's amazing.

Moreover, functional programming language do *not* contain loop
combining forms -- they contain only recursion to accomplish repeated
execution of a block of statements!

The most important component of a functional programming language is,
well, functions! In functional programming languages, unlike imperative
an object-oriented programming languages, a function produces the same
output when given the same input *no matter when it is executed.* This
*referential transparency* is a consequence of the program having no
state!

All kinds of great benefits accrue when you can make the assumption that
a program has no state. Interestingly, it makes it possible to easily
reason about the parts of a program that can execute in parallel!

The theoretical underpinning of the functional programming paradigm is
the *lambda calculus*.

Examples of (again, pure) functional programming languages include
Haskell, Miranda, and Elm. Impure functional programming languages
(though still occupying a niche like all functional programming
languages) are more popular. Examples include: Lisp, Scheme, Racket,
Erlang, Clojure, and Scala.

Despite your effort to avoid functional programming, I *bet* that your
favorite language includes patterns/syntax that support writing programs
in a functional "style". In fact, JavaScript was originally developed as
a way to give programmers the ability to write programs for the web
browser in a functional way (other examples of languages that include
significant support for writing programs according to a functional
paradigm include Python, C++, Java and Rust).

#### Logic/Declarative

If you thought that functional programming languages were weird, wild
stuff, just wait until you see logic/declarative programming languages.

Though by far the most different paradigm from imperative/procedural,
the concept behind logic programs can be stated succinctly: Whereas
programs written in imperative, object-oriented and functional
programming languages describe *how* to compute a result, programs
written in logic programming languages describe the characteristics of a
correct solution.

In other words, logic programmers specify the *what* and not the *how*.
Want a program that sorts a list, just describe the requirements of a
list that is in sorted order (e.g.,
`for all indexes i and j of an array a where i < j, a[i] < a[j]`) and
let the "compiler" figure out how to make it happen!

It's awesome!

The theoretical underpinning of the logic programming paradigm is the
*predicate calculus*.

"They" say that SQL is a logic/declarative programming language. I've
never understood their rationale, but that's a story for a different
day. In this class, we will learn Prolog, (arguably) *the* logic
programming language.

</div>
