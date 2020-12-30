Conway's Game of Life in 12 Programming Languages
=================================================

This is a straightforward implementation of the [Game of Life][0] rules in 12 programming languages:
  * [C++][1] (version 2011 and later) &mdash; [life.cc](life.cc), [life0.cc](life0.cc), [life2.cc](life2.cc)
  * [Python][2] (version 2 and 3) &mdash; [life.py](life.py), [life.py3](life.py3)
  * [PHP][3] &mdash; [life.php](life.php)
  * [Perl][4] (version 5) &mdash; [life.pl](life.pl)
  * [Ruby][5] &mdash; [life.rb](life.rb)
  * [JavaScript/ECMAScript][6] (via Node.js) &mdash; [life.js](life.js)
  * [Tcl][7] &mdash; [life.tcl](life.tcl)
  * [Lua][8] &mdash; [life.lua](life.lua)
  * [Scheme][9] (at least R5RS and later) &mdash; [life.scm](life.scm)
  * [Java][10] (version 8 and later) &mdash; [life.java](life.java), [life2.java](life2.java)
  * [Julia][11] &mdash; [life.jl](life.jl), [life0.jl](life0.jl), [life2.jl](life2.jl)
  * my own programming language called [MANOOL](https://manool.org) &mdash; [life.mnl](life.mnl)
  * hypothetical language MANOOL-2 &mdash; [life.manool2.mnl](life.manool2.mnl), [life2.manool2.mnl](life2.manool2.mnl)

The program simply displays an initial configuration and then the configuration after _G_ generations and exits. The grid (board) dimensions are given by
parameters _N_ and _M_, and the initial configuration is hard-coded but can be modified at your will. The universe is wrapped.

The MANOOL version has an additional parameter, _AllocOpt_, which determines whether the code is explicitly memory allocation-aware or completely relies on
copy-on-write aspects of the language semantics.

The main purpose of this repository is to have a benchmark (which is both computationally intensive and fun) to compare performance of the MANOOL translator
with that of other language implementations and to compare MANOOL with other languages. However, while coding the same task in so many of them, I suddenly
realized how *bizarre* are the similarities (and differences) between programming languages.

Examples of command line to run:

* C++:

      g++ -std=c++11 -O3 life.cc && time ./a.out; rm -f a.out

  or

      clang++ -std=c++11 -O3 life.cc && time ./a.out; rm -f a.out

* Python:

      time python life.py

  or

      time python3 life.py3

* PHP:

      time php life.php

* Perl:

      time perl life.pl

* Ruby:

      time ruby life.rb

* JavaScript/ECMAScript:

      time node life.js

* Tcl:

      time tclsh life.tcl

* Lua:

      time lua life.lua

  or

      time luajit life.lua

* Scheme:

      time guile life.scm

  or

      csc -C -O3 life.scm && time ./life; rm -f life

* Java:

      javac life.java && time java Main; rm -f Main.class

* Julia:

      time julia -O3 life.jl

* MANOOL:

      time MNL_PATH=~/manool/build/lib ~/manool/build/mnlexec life.mnl


[0]:  https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life
[1]:  https://en.wikipedia.org/wiki/C%2B%2B
[2]:  https://en.wikipedia.org/wiki/Python_(programming_language)
[3]:  https://en.wikipedia.org/wiki/PHP
[4]:  https://en.wikipedia.org/wiki/Perl
[5]:  https://en.wikipedia.org/wiki/Ruby_(programming_language)
[6]:  https://en.wikipedia.org/wiki/JavaScript
[7]:  https://en.wikipedia.org/wiki/Tcl
[8]:  https://en.wikipedia.org/wiki/Lua_(programming_language)
[9]:  https://en.wikipedia.org/wiki/Scheme_(programming_language)
[10]: https://en.wikipedia.org/wiki/Java_(programming_language)
[11]: https://en.wikipedia.org/wiki/Julia_(programming_language)
