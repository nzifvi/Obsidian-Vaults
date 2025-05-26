[[9,1) Vector]] <- Back
[[2) Java Memory Model]] <- Next

---
## Compiling in Java
The Java Compiler, which IntelliJ IDE runs for user, compiles Java source code into executable code.

Compilation includes inserting code for imported libraries, memory management, and many more details.

In Java, executable code produced by compilation is a custom type of executable code. The language is referred to as Java Bytecode.

- Java Bytecode is NOT executable by the CPU. The JVM (Java Virtual Machine) is an interpreter that interprets Bytecode.


## Executing in Java
Bytecode is interpreted by the Java Virtual Machine (JVM).
- JVM turns bytecode instructions into machine actions.
- Machine actions include memory management, IO, and computation.
- Virtual machines exist for a wide range of OS/architectures.
- Java source code can be used in many environments AS LONG as JVM used in that environment is compatible with that environment's compiler.
- Java != a compiled language. C++ is a compiled language.
- Compiled languages source code are compiled for a particular OS/architecture by a specific compiler. Interpreted languages are interpreted by an interpreter.

## Background process of Java during compilation
When compiling Java source code, a lot happens in the background.

This includes...
1) Managing where variables are stored in memory.
2) Deallocating memory assigned to data which is no longer in scope or needed.
3) Creating new objects.
4) ...

