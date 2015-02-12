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
