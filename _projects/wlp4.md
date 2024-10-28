---
layout: page
title: wlp4-compiler
description: A WLP4 (subset of C) compiler written in C++ that compiles to MIPS assembly.
img: assets/img/compiler.jpg
importance: 2
category: work
giscus_comments: true
---

WLP4 is a language developed by the CS241 staff at uWaterloo, standing for "Waterloo Language Plus Pointers Plus Procedures". Here is a <a href="https://student.cs.uwaterloo.ca/~cs241/wlp4/WLP4tutorial.html">tutorial</a> and here is <a href="https://student.cs.uwaterloo.ca/~cs241/wlp4/WLP4.html">the formal language specification</a> . This compiler implements a scanner (simplified maximal munch scanning algorithm), parser (SLR(1) algorithm), type checker and code generator.

Since this was a compiler written for a course, I can provide it privately if contacted at <a href="m3damani@uwaterloo.ca">m3damani@uwaterloo.ca</a>

<h2><b>Compiler Processes:</b></h2>
<h4><b>Scanning</b></h4>
<p>The compiler first tokenizes/scans given WLP4 code. Scanning is implemented through a Simplified Maximal Munch Algorithm, which attempts to consume input until it gets "stuck", at which point it is determined whether or not the input is in an accepting state. If in an accepting state, a token will be produced. Otherwise, the input will be rejected. The algorithm scanned through the code uses an NFA, for which the lexical syntax used can be found here.</p>

<h4><b>Parsing</b></h4>
<p>Parsing is implemented using Pushdown Automata to determine if the code can be recognized using a Context Free Grammar (CFG). The context-free syntax of WLP4 can be found here. The final product upon parsing a CFG generates a derivation of the input string, which uniquely defines a parse tree used to represent the structure of the program. For the purposes of this compiler, a Bottom-Up Parsing algorithm is used, specifically the SLR(1) parser.</p>

<h4><b>Context-Sensitive Analysis</b></h4>
<p>The next step of the compiler is to determie if the code follows the context-sensitive rules of WLP4. Examples of common rules used by popular languages are:
<ul>
<li>Not declaring multiple variables with the same name</li>
<li>Not using a variable prior to its declaration</li>
</ul>
The full set of semantic/type-inference rules can be found here, and the full set of context-sensitive rules can be found here. To accomplish this, the compiler parses through the parse tree generated from the last step to ensure each rule is followed.<p>

<h4><b>Code Generation</b></h4>
<p>The final part of the compilation process is code generation, and completing the process of translating WLP4 source code to MIPS assembly language. Basic features are supported including code generation for the main procedure, integer variables and constants, declarations, assignment, arithmetic, control flow, and printing, and additional support for pointers, other procedures, and dynamic memory allocation is also implemented.</p>
