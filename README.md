# JavaPerformance
## JVM JIT compiler
  - The JIT compiler consists of two compilers **C1(Client compiler)** & **C2(Server compiler)**. **C1** is used for most of the code lines. But if a code line is repeated multiple times, **C2(Server compiler)** compiler compiles the code with further optimization and moves the compiled code to Code cache. This is called Tired Compilation.
  - 32 bit machine has only C1 compiler. While 64 bit has both C1 and C2 compiler.
  
## VM arguments
  - _-XX:+PrintCompilation, -XX:+UnlockDiagnosticVMOptions & -XX+LogCompilations_ - Prints the bytecode compilation by JVM.
  - _-XX:+PrintCodeCache_ - Prints the used, total and reserved code cache.
  - _-XX:InitialCodeCacheSize_ - Sets the code cache during initial phase.
  - _-XX:ReservedCodeCacheSize_ - Set the maximum code cache size JVM can reach.
  -_ -XX:CodeCacheExpansionSize_ - The amount by which the code cache should expand.
  - _-XX:-TieredCompilation_ - Turns off tiered compilation. JVM will select either Client or Server compiler to interpret the code, but not both.
  - _-XX:CICompilerCount=n_ - Set the number of parallel compiler threads.
  - _jps_ - Returns the java process running in machine.


## Java memory model - Stack, Heap and Metaspace
 - **Stack** : Is used to store local primitive varaibles and method calls of a method or a code block.
  
  
  
  
