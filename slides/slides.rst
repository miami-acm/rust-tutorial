.. role:: bash(code)
   :language: bash

.. role:: rust(code)
   :language: rust

=============================
The Rust Programming Language
=============================

Nate Mara

2015-02-12

=====
Intro
=====

Rust is a systems programming language that combines the speed of C/C++ with
the 'safety' of garbage-collected languages like Python & Java. It is being
developed by Mozilla for their new browser engine, Servo.

=========
Why Rust?
=========

Rust has several features that make it a good choice for a project:

    - Zero-cost abstractions
    - Guaranteed memory safety at compile time
    - Trait-based generics
    - Type inference
    - Pattern matching

======================
Zero Cost Abstractions
======================

`Python Example <https://gist.github.com/natemara/e84c14966384c428a3d8>`_

========================
Guaranteed Memory Safety
========================

This has a few important implications:

    - No Segmentation Faults!
    - No memory leaks!
    - No data races in multithreaded programs!
    - No Null Pointers!!!!!

====================
Trait Based Generics
====================

Consider this C++ code:

.. code-block:: cpp

    template <class T>
    bool foo(T x, T y) {
        return x == y;
    }

Equivalent Rust:

.. code-block:: rust

    fn foo<T: PartialEq>(x: T, y: T) -> bool {
        x == y;
    }

==============
Type Inference
==============

The type of variables does not explicitly have to be defined when defining
variables.

.. code-block:: rust

     let mut hashes = HashSet::new();
     hashes.insert("00f013675328fac432");

====================
Algebraic Data Types
====================

- Create new types based on combinations of other types
- Not the same as creating classes with getters and setters
- This is a type that can only have a specific number of values

.. code-block:: rust

    enum Suit {
        Hearts,
        Clubs,
        Diamonds,
        Spades,
    }


===============
Patten Matching
===============

    - Borrowed from Haskell
    - Can match against boolean conditions or variants of an enum.
    - More powerful than a `switch` statement as it forces you to account for
      all possibilities.

.. code-block:: rust

    match card.suit {
        Hearts => println!("Hearts"),
        Clubs => println!("Clubs"),
        Spades => println!("Spades"),
    } // will not compile because Diamonds case was not dealt with

=================
No Null Pointers!
=================

    - No way to create a null pointer in normal Rust
    - Only used when interfacing with C

        - Have to explicitly check for null pointer

.. code-block:: rust

    match deck.draw_card() {
        Some(card) => println!("You picked {}", card),
        None => println!("No more cards left!"),
    }
