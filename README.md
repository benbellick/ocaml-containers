ocaml-containers
================

A bunch of containers,written in different occasions. Not all
containers are properly tested (see `tests/` and `make tests`
if you have installed `OUnit`).

The design is centerred around polymorphism rather than functors. Such
structures comprise:

- `PHashtbl`, a polymorphic hashtable (with open addressing)
- `SplayTree`, a polymorphic splay heap implementation
- `Heap`, an imperative heap based on `SplayTree`
- `Graph`, a polymorphic imperative directed graph (on top of `PHashtbl`)
- `Hashset`, a polymorphic imperative set on top of `PHashtbl`
- `FQueue`, a purely functional queue structure
- `Heap`, a purely functional polymorphic heap

Other structures are:

- `Univ`, a universal type encoding with affectation
- `Cache`, a low level memoization cache for unary and binary functions
- `Deque`, an imperative double ended FIFO (double-linked list)
- `Vector`, a growable array (pure OCaml, no C; not tested)
- `FlatHashtbl`, a (deprecated) open addressing hashtable with
    a functorial interface (replaced by PHashtbl)

## Use

You can either build and install the library (see `Build`), or just copy
files to your own project. The last solution has the benefits that you
don't have additional dependencies nor build complications (and it may enable
more inlining). I therefore recommand it for its simplicity.

If you have comments, requests, or bugfixes, please share them! :-)

## Build

There are no dependencies (`Sequence` is included). Type:

    $ make

To build and run tests (requires `oUnit`):

    $ opam install oUnit
    $ make tests
    $ ./tests.native

To build the small benchmarking suite (requires `Bench`):

    $ opam install bench
    $ make bench
    $ ./benchs.native

## License

This code is free, under the BSD license.
