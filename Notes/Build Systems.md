
When designing a project build it can get complex, after a certain point it's easiest to just automate it to reduce the chance of error, this is where build systems come in.

>A build system's goals are to:
>
>- _organize the magical incantations_: automate the compilation and linking of source files into executables
>- _process only what's necessary_: recompile only the changed portion of the source code, and the portion dependent on changed code
>- _make maintaining the build system easier_: the build system should be a programming language that allows you to avoid redundant (copied) code
>
>(*Gabriel Palmer*)

Although, it is important to remember to **build incrementally**.

Examples of things that assist are [[Makefiles]] and Maven.