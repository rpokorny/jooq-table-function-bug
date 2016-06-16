# jooq-table-function-bug
Demonstration repo for a bug with jOOQ 3.8's code generation for table-valued
functions.

Starting with version 3.6, it seems that jOOQ is supposed to expose table-valued
functions as Tables, not Routines.  In 3.8 it appears that they are Routines
again, and there does not appear to be a way to use them within the context of
the DSL, in either the SELECT or FROM clauses.

Steps to reproduce:
1. Run mvn clean install
2. Look in the `target/generated-sources/jooq/jooqbug/tables` directory
Expected Results: A Test.java file representing the test() function defined in
the SQL that is loaded in pom.xml
Actual Results: The directory does not exist.  Instead, a `routines` directory
exists.  Additionally, Routines.java only includes invocations of the function
that include a `Configuration` parameter.
