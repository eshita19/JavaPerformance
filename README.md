# JavaPerformance
## JVM JIT compiler
  - The JIT compiler consists of two compilers **C1(Client compiler)** & **C2(Server compiler)**. **C1** is used for most of the code lines. But if a code line is repeated multiple times, **C2(Server compiler)** compiler compiles the code with further optimization and moves the compiled code to Code cache. This is called Tired Compilation.
  - 32 bit machine has only C1 compiler. While 64 bit has both C1 and C2 compiler.
  
## VM arguments
  - -XX:+PrintCompilation, -XX:+UnlockDiagnosticVMOptions & -XX+LogCompilations - Prints the bytecode compilation by JVM.
  - -XX:+PrintCodeCache - Prints the used, total and reserved code cache.
  - -XX:InitialCodeCacheSize - Sets the code cache during initial phase.
  - -XX:ReservedCodeCacheSize - Set the maximum code cache size JVM can reach.
  - -XX:CodeCacheExpansionSize - The amount by which the code cache should expand.
  - -XX:-TieredCompilation - Turns off tiered compilation. JVM will select either Client or Server compiler to interpret the code, but not both.
