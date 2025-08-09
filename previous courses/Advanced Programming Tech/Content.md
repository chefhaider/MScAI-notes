

1. **Introduction to Advanced Programming Techniques**:
    
    1.  High Performance Computing
    2. Introduction to C++ terms and definitions (statements, blocks, functions, return types, arguments).
    3. Standard IO, variables, data types, operators, and namespaces.
    4. Control structures (While, For, If statements).
    5. Classes: data structures, member functions, and operators.
    6. Advanced C++ concepts such as smart pointers, templates, metaprogramming, exceptions, coroutines and upcoming standards.
    7. Shared-memory parallelization, design patterns, optimizing C++, Python and HPC, HPC and AI, and performance portability.

2. **Computer Architecture and Compilers**:
    
    8. Computer architecture basics and history.
    9. Von Neumann computer architecture.
    10. Instruction sets and machine code.
    11. Compiler basics and construction.
    12. Phases of a compiler: lexical analysis, parsing, semantic analysis, intermediate code generation.
    13. Compiler optimisation for performance, code size, power consumption, security, debugging.
    14. Clang AST example.
3. **Types in C++**:
    
    15. Literal constants (integer, floating-point, boolean, character, string).
    16. Escape sequences.
    17. Variables: object, declaration, definition, type specifier, identifier.
    18. Type-checking (statically typed).
    19. Scope: global, class, namespace, local, block, statement.
    20. Pointers.
4. **Classes in Detail**:
    
    21. Classes: abstract data types, data, function, and type members.
    22. Access specifiers: public, private, protected.
    23. Data abstraction and encapsulation.
    24. Const and mutable data members.
    25. Name lookup in classes.
    26. Constructors and constructor initializer lists.
    27. Overloaded operator design.
    28. Input and output operators.
    29. Arithmetic and relational operators.
    30. Assignment and subscript operators.
5. **Smart Pointers and Dynamic Memory**:
    
    31. Arrays.
    32. New and delete expressions.
    33. Standard Library allocator class.
    34. Managing pointer members.
    35. Use count.
6. **Functions**:
    
    36. Basic definitions: function prototype, call operator, parameters vs arguments.
    37. Header files and header guards.
    38. Argument passing: nonreference, pointer, const, and reference parameters.
    39. Command line options and functions with varying parameters.
    40. Return statement.
    41. Local objects and inline functions.
    42. Class member functions and the 'this' pointer.
    43. Overloaded functions and overload resolution.
    44. Argument-type conversions.
    45. Pointers to functions.
    46. Lambda expressions.
7. **Templates**:
    
    47. Class and function templates.
    48. Template parameters: type and non-type parameters.
    49. Template argument deduction.
    50. Trailing return types.
    51. Perfect forwarding.
    52. Overloading and function templates.
    53. Type traits.
    54. Concepts.
8. **C++ Standard Library**:
    
    55. Overview of the standard C++ library.
    56. Object-oriented library and IO library.
    57. Features of IO library: international character support and manipulators.
    58. Condition states.
    59. Buffers and file streams (fstream).
    60. File modes.
    61. Single-byte and multi-byte operations.
    62. String streams.
    63. Standard Template Library (STL): abstract data types and containers.
    64. Size types.
    65. Sequential containers: vector, list, deque, forward_list, array.
    66. Iterators and iterator ranges.
    67. Invalidated iterators.
    68. Sequence container operations.
    69. Library vector type.
    70. How a vector grows.
    71. Container adaptors: stack, queue, priority_queue.
    72. Pairs.
    73. Associative containers: map, set, multimap, multiset.
    74. Map operations and additional typedefs.
    75. Set and multiset.
    76. Unordered containers.
    77. Generic algorithms.
    78. Eliminating duplicates.
    79. Predicates.
    80. Insert iterators and reverse iterators.
    81. Iterator categories.
    82. Structure of generic algorithms.
9. **Advanced C++ Standard Library**:
    
    83. Tuple type.
    84. Regular expressions.
    85. Random numbers.
    86. Chrono library.
    87. Other library parts: std::function, std::source_location, std::optional, std::any.
    88. Concepts and type traits.
    89. SFINAE.
10. **Code Generation for High-Performance Computing (HPC)**:
    
    90. HPC and its challenges.
    91. The 3P's: Performance, Portability, Productivity.
    92. Tackling the 3P's with scientific libraries/frameworks and code generation.
    93. Source-to-source compilers.
    94. Code generation process.
    95. Example: Jacobi 5-Point Stencil.
    96. ExaStencils: domain-specific language (DSL) for stencil codes.
    97. Automatic parallelization for CPU and GPU systems.
11. **Domain-Specific Languages (DSLs) and Code Generation**:
    
    98. Definition of DSLs.
    99. Standalone vs. embedded DSLs.
    100. DSLs as metaprogramming tools.
    101. Automatic algorithm synthesis.
    102. Generating parsers for context-free grammars.
    103. Metaprogramming with embedded DSLs.
    104. C++ compile-time regular expression parser.
    105. Abstraction in numerical programming.
12. **Inheritance**:
    
    106. C++ object model.
    107. Object-oriented programming (OOP) and polymorphism.
    108. Derived classes.
    109. Types of inheritance: public, private, protected.
    110. Conversions from derived to base.
    111. Pure virtual functions and abstract base classes.
    112. Multiple and virtual inheritance.
    113. Dynamic cast.
13. **Exceptions**:
    
    114. Exception handling.
    115. C++ Standard library exceptions examples.
    116. Catch-all.
    117. Exception safe and stack unwinding.
14. **C++ Threads**:
    
    118. Parallel programming and multithreaded programming.
    119. Race conditions and deadlocks.
    120. C++ Memory Model.
    121. Atomics.
    122. Mutual exclusion (mutex).
    123. Future and promise.
    124. Volatile keyword.
15. **Design Patterns**:
    
    125. Builder pattern.
    126. Abstract Factory pattern.
    127. Chain of Responsibility.
    128. Mediator pattern.
16. **Modern C++ (C++20, C++23, ...)**:
    
    129. C++20 features: attributes, modules, coroutines, concepts, ranges library.
    130. Attributes syntax and examples.
    131. Modules advantages and examples.
    132. Coroutines.
    133. Ranges library and examples.
    134. C++23 features.
17. **Overcoming Drawbacks of C++**:
    
    135. Portability.
    136. Security.
    137. Profiling Problems.
18. **Metrics for HPC Codes**:
    
    138. Execution Time (T).
    139. Speedup (S).
    140. Efficiency (E).
    141. Scalability: Weak Scaling and Strong Scaling.
    142. Portability Metrics: Code Compatibility, Performance Portability, Library Dependency.
    143. Productivity Metrics: Development Time (Tdev), Code Complexity (C), Code Maintainability (M), Code Reusability (R).
19. **Software Engineering for HPC**:
    
    144. Parallel Programming.
    145. Performance Optimization.
    146. Scalability.
    147. Reliability and Fault Tolerance.
    148. Testing and Debugging.
20. **Domain Specific Languages**:
    
    149. Embedded and External DSLs.
21. **Code Generation**:
    
    150. Code Generation Process in a Compiler.
    151. Coupling C++, DSLs and AI.
22. **Coupling C++ Code with AI Generated Code**:
    
    152. Direct Integration.
    153. Function Replacement.
    154. Module Addition.
    155. Code Refactoring.
    156. Test Case Generation.
    157. Documentation Generation.
23. **LLVM Compiler Infrastructure**.
    
    158. Source Code Front End, LLVM IR, LLVM Optimizer, Back End Target Code.
24. **Kaleidoscope Tutorial Overview**.
    
    159. Implementing Lexer and Parser.
    160. Implementing an Abstract Syntax Tree (AST).
    161. Generating LLVM IR from AST.
    162. Adding JIT compilation support.