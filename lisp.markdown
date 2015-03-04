---
title: Lisp BNF grammar
---

# Lisp BNF

[Lisp]() is one of the oldest and yet most powerful programming languages. It's said by those just
learning lisp that the enlightenment it gives you makes you a much better programmer overall, even
if you don't use it day to day. Most of the features it had for decades are features other programming
languages only started to get in the last decade.

Despite that, its BNF grammar is incredibly simple. It's amazing that you can do so much with so little.

If you want to learn more, check out PG's [Roots of Lisp](http://www.paulgraham.com/rootsoflisp.html) as well as [What made Lisp different](http://www.paulgraham.com/diff.html)

    s_expression = atomic_symbol \
                   / "(" s_expression "."s_expression ")" \
                   / list 
   
    list = "(" s_expression < s_expression > ")"

    atomic_symbol = letter atom_part

    atom_part = empty / letter atom_part / number atom_part

    letter = "a" / "b" / " ..." / "z"

    number = "1" / "2" / " ..." / "9"

    empty = " "

[http://cui.unige.ch/db-research/Enseignement/analyseinfo/LISP/BNFlisp.html](http://cui.unige.ch/db-research/Enseignement/analyseinfo/LISP/BNFlisp.html)
