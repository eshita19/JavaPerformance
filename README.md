# JavaPerformance
## JVM JIT compiler
  - The JIT compiler consists of two compilers **C1** & **C2**. **C1** is used for most of the code lines. But if a code line is repeated multiple times, **C2** compiler compiles the code with further optimization and moves the compiled code to Code cache.
## VM arguments
  - -XX:+PrintCompilation, -XX:+UnlockDiagnosticVMOptions & -XX+LogCompilations - Prints the bytecode compilation by JVM.
  - -XX:+PrintCodeCache - Prints the used, total and reserved code cache.
