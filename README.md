# bs-interp
An interpreter for a language called bs-core which is capable of bootstrapping a compiler for bs-core. The bs-core language is a subset of lisp like languages that could be used to efficiently implement arbitrary programming languages. As part of this project bs-core is used to implement a language called bs which is the language that can be used to boot  The full language bs can then be used to bootstrap arbitrary languages.

An interpreter for bootstrapping a lisp implementation.
### Goals
* Write a simple but efficient interpreter capable of being bootstrapped.
* The end language (BS) should be able to efficiently implement arbirary typed and untyped programming languages. 
  * #lang languages
  * nanopass based compiler framework
* The bs-core lanugage should be an efficient compilation target for bootstrapping other languages.
  * Static and Dynamically sized data.
  * Linklets
  * Compilation to native executables, 
* The intitial interpreter should be able to efficiently compile itself.
  * Able to write macro expander
  * Able to serialize ir to serialize heap into boot file.
  * Able to call c code
  * Able to write and replace:
    * reader
    * eval
      * expander
      * compile
      * eval
    * printer
    * serializer
    
### Non-Goals
* Write a full featured programming language. 

###
1. Write basic interpret for bs-interp (the subset of bs-core implemented in the interpreter)
2. Write reader and expander in bs-interp
3. Write simple compiler for bs-interp to remove the overhead of interpreting bs-interp.
4. Write naive translation layer via macro expansion between bs-core and bs-interp
5. Write bs in terms of bs-core
6. Write a optimizing compiler for bs-core in bs.


### Questions


### Brainstorm / Inspiration / Resources
* Lua
  * Simplicity first
  * A few base types can do most of everything if chosen correctly.
    * Functions
    * Immutable strings / symbols - Same datastructure.
      * String=? Is normal string equality with some shortcuts.
      * Symbol=? Does symbol unification while comparing to make future comparisons cheaper.
        * Hashing for quicker disequality
        * Union Find for Quicker equality.
    * Composite Datatypes
      * Sequences
      * Ordered Maps
      * records / structs
        * 
    * Foreign Data

* [Chez Scheme](https://github.com/cisco/ChezScheme)
  * Uses the mutable top level environment to boot strap.
  * Copying BIBOP Garbage Collector
* Racket
  * Immutable top level.
  * #lang languages
  * and most of the technology for layering languages on top of each other via macros
  * Linklets as an abstraction over
* [Zuo](https://github.com/racket/zuo)
* [OCaml]()
  * The underlying memory model for ocaml inspires the implementation
  * Modules
