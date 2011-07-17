ocamlyacc with some additional features
=======================================

This is a fork project of ocamlyacc which includes the following
additional features:

Embedded Action
---------------

Embedded action allows you to write a bare action in the rule. This is
an original feature of Berkeley Yacc which had been disabled on
porting to OCaml.

Example:

    expr: NUM PLUS { print_endline "trying to add" } NUM { $1 + $4 }

This is equivalent to:

    expr: NUM PLUS e NUM { $1 + $4 }
    e: { print_endline "trying to add" }
