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
  -  _-XX:MaxHeapSize=n_ or _-Xmx_ - Set max heap size.
  -  _-XX:InitialHeapSize=n_ or _-Xms_ - Initial  heap size.
  -  _-XX:+HeapDumpOnOutOfMemoryError_ - Generate Heap dump on out of memory.
  -  _-XX:+HeapDumpPath=someFilePath_ - Heap dump path.
  - _jps_ - Returns the java process running in machine.


## Java memory model - Stack, Heap and Metaspace
 - **Thread stacks** - Each thread has its own call stack. The stack stores primitive local variables and object references along with the call stack (list of method invocations) itself. The stack is cleaned up as stack frames move out of context so there is no GC performed here.
 - **Heap** - The heap is where your Class instantiations or “Objects” are stored.
 - **Metaspace(Java8+)**: Metaspace stores the Class definitions of your Objects, and Static variables. **Permgen** space was used for Java <=7. Permgen had fixed size. But metaspace auto increases its size depending on the underlying OS.
 - **Code cache** - The JIT compiler stores native code it generates in the code cache to improve performance by reusing it.
 - **Buffer pools** - Many libraries and frameworks allocate buffers outside of the heap to improve performance. These buffer pools can be used to share memory between Java code and native code, or map regions of a file into memory.
 - **OS memory** - The operating system keeps heap and stacks for a Java process independent of the heap and stacks managed by the JVM itself. There is also memory consumed for each native library loaded (such as libjvm.so). This is usually very small.

## String Constant Pool
  - Since Strings are immutable, same Strings point to same memory location in String Constant pool.
  - String Constant pool uses HashMap as its internal DS.
  - Resides in Heap memory.
  - _-XX:+PrintStringTableStatistics_ : Prints the string constant pool statistics.
  - _-XX:StringTableSize=n_ : n is the number of buckets we need in String constant pool.

## JVisualVM
  - JvisualVM can be used to monitor heap, thread stack, metaspace and to download Heap dump.
  - JMX connection to a docker tomcat. Add Catalina opts: `-Dcom.sun.management.jmxremote=true -Djava.rmi.server.hostname=0.0.0.0 -Dcom.sun.management.jmxremote.port=9010 -Dcom.sun.management.jmxremote.rmi.port=9010 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false`
  - For downloading Heapdump add following JVM options: -XX:+HeapDumpOnOutOfMemoryError, -XX:+HeapDumpPath=someFilePath.
  - Analyze Heap dump in _Eclipse memory analyzer_ - http://download.eclipse.org/mat/1.12.0/update-site/.

  
  
  
  
