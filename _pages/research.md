---
layout: single
title: "Research Projects"
permalink: /research/
author_profile: true
---

- **[ELEVATE](https://elevate-lang.org/)** is a language for describing optimization strategies in a composable way.

- **[RISE](https://rise-lang.org/)** is a functional pattern-based data-parallel language.
  Programs are expressed at a high level in RISE.
  Programs are then transformed using a set of rewrite rules that encode implementation and optimization choices.
  The _Shine_ compiler generates high-performance parallel C or OpenCL code while preserving the optimization choices made during rewriting.<br/>
  We are currently actively working on a prototype implementation in Scala available on [GitHub](https://github.com/rise-lang/rise) as well as an implementation in of [RISE in MLIR](https://rise-lang.org/mlir) that is also available on [GitHub](https://github.com/rise-lang/mlir).<br/>
  RISE is a spiritual successor to the Lift project.

- **[Lift](http://www.lift-project.org)** is a project aiming to achieve _performance portability_ across modern parallel architectures. The _Lift compiler_ transforms a program expressed in the high-level  _Lift programming language_ into optimised low-level OpenCL code. In this transformation optimisations are automatically explored using a set of rewrite rules.
  Lift is open source software available on [GitHub](https://github.com/lift-project/lift).
  Lift has been described in multiple research [publications](/publications-lift/) and is developed by a [research team](http://www.lift-project.org/index.html#team) including multiple PhD students based in Scotland and Germany.

- **[PACXX](http://pacxx.github.io/page/)** allows programming of accelerators with modern C++.
  PACXX is developed by [Michael Haidl](http://www.uni-muenster.de/PVS/en/mitarbeiter/haidl.shtml) at the University of Münster.
  In a series of collaborative [publications](/publications-by-project/#pacxx) we explore [challenges of heterogeneous compiler implementations](/publications/2016/GPGPU-2/) and the [design of modern C++ range-based libraries](/publications/2017/PMAM/) for parallel programming. PACXX is open source software available on [Github](https://github.com/pacxx/pacxx-llvm).

- **[GPU Compilation for Interpreted Languages](/publications/2017/VEE/)** is the one of the first solutions for compiling a dynamic interpreted programming language -- namely R -- to GPU code.
  The generation of GPU code happens at runtime after crucial information of the program, such as data types, have been observed by profiling.
  [Juan Fumero](http://homepages.inf.ed.ac.uk/s1369892/) has developed our implementation which is described in our recent [paper](/publications/2017/VEE/) and is available on [Bitbucket](https://bitbucket.org/juanfumero/fastr-gpu).

- **[Marawacc](/publications-by-project/#marawacc)** is a solution for GPU programming from Java.
  Marawacc combines a library interface similar to the stream API from Java 8 and a compiler which generates OpenCL code from Java byte code at runtime.
  Data management optimisations eliminate the overhead of data marshalling.
  Marawacc is open source software available on [Bitbucket](https://bitbucket.org/juanfumero/marawacc).
  Marawacc has been described in multiple [publications](/publications-by-project/#marawacc) and has been developed by [Juan Fumero](http://homepages.inf.ed.ac.uk/s1369892/).

- **[SkelCL](https://skelcl.github.io)** is a library providing high-level abstractions to alleviate programming of modern parallel heterogeneous systems comprising of multi-core CPUs and GPUs.
  SkelCL is open source software available on [GitHub](https://github.com/skelcl/skelcl).
  SkelCL has been described in multiple research [publications](/publications-skelcl/).
  SkelCL is no longer under active development.
