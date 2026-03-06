# MicroJava_Compiler

**Author:** Sofija Joksimović  

## Project Overview
This project implements a compiler for **MikroJava**, a simplified Java-like programming language used for educational purposes.  
The compiler translates syntactically and semantically correct MikroJava programs into **MikroJava bytecode**, executable on the **MikroJava Virtual Machine (MJVM)**.  

The compiler includes four main components:  
1. **Lexical Analysis** – tokenizes source code.  
2. **Syntax Analysis (Parser)** – builds an Abstract Syntax Tree (AST).  
3. **Semantic Analysis** – checks context rules and symbol usage.  
4. **Code Generation** – produces executable bytecode for MJVM.

---

## Features

### Lexical Analysis
- Implemented using **JFlex** (`mjlexer.flex`), generating a scanner in Java.  
- Recognizes:
  - Identifiers
  - Constants
  - Keywords
  - Operators
  - Comments (ignored during parsing)
- Skips whitespace (`\t`, `\r\n`, space, backspace, form feed).  
- Detects and reports lexical errors with:
  - Unrecognized character sequence  
  - Line number  
  - Column position  

### Syntax Analysis
- Implemented using **AST-CUP**, an extension of **CUP** for AST generation.  
- Builds an **Abstract Syntax Tree** from valid token sequences.  
- Supports **error recovery** for robust parsing.  
- Provides a `toString()` method to display the AST.  
- Grammar supports Nivo A, B, and C features (basic expressions, control structures, functions, arrays, inheritance, inner classes, etc.).

### Semantic Analysis
- Implemented via `SemanticAnalyzer` extending `VisitorAdapter`.  
- Performs context checks and symbol validation.  
- Integrates with a **symbol table** (`symboltable-1-1.jar`).  
- Checks:
  - Variable and constant usage  
  - Function calls  
  - Type correctness  
  - Inheritance and polymorphism rules  
- Provides `tsdump()` to display the symbol table.

### Code Generation
- Implemented via `CodeGenerator` extending `VisitorAdapter`.  
- Traverses AST to generate **MJVM bytecode** (`.obj` file).  
- Supports:
  - Expressions, arrays, variables  
  - Control structures (`if`, `for`, `switch`)  
  - Functions and methods  
  - Classes and inheritance  
  - Polymorphic method calls
    
## Technologies Used
- **Java 1.8** – compiler implementation  
- **JFlex** – lexical analyzer generator  
- **AST-CUP / CUP** – parser generator with AST support  
- **MJVM** – MikroJava Virtual Machine  
- **Symbol Table Library** (`symboltable-1-1.jar`)  
- **JUnit / custom tests** – for validation of parser, semantic analyzer, and code generator

## Source code will be published after the course policy allows it.


## Project Structure
