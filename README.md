# jooq-table-function-bug
Demonstration repo for a bug with jOOQ 3.8's code generation for table-valued
functions.

Starting with version 3.6, it seems that jOOQ is supposed to expose table-valued
functions as Tables, not Routines.  In 3.8 it appears that they are Routines
again, and there does not appear to be a way to use them within the context of
the DSL, in either the SELECT or FROM clauses.
