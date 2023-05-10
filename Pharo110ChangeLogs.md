# Pharo 11 changes overview

A large international community of developers worked hard to prepare a new release of the Pharo platform.

## Highlights

### Tools
- Iceberg (the Git client/VCS control tool) has received a lot of tweaks and fixes to work better with GitHub and other remote control files.
- The debugger now incorporates a lot of tweaks and, notably, the capability of adding bindings in the context interaction model.
- TimeProfiler (the profiling tool) has a new UI and also incorporates the alternative Andreas Profiler.
- DrTests (the Test Runner alternative) has been improved and updated to the latest Spec.
- There is a new implementation of Rewrite tools. 
- There is a new tool: The Document Browser, which allows the visualization of Microdown (Markdown compatible) documents placed on the web or locally. 
- Calypso (the System Browser) has incorporated some interesting mini tools: package dependency and baseline visualization.
- We have introduced new and improved Inspectors, notably for AST/Blocks/IR, among others."
- All versions of NewTools, Spec, Roassal and Microdown have been updated with a lot of bug fixes. 

### System 
- Slots now have a Setting for unrestricted definitions.
- Slots now allow more complex Slot definitions (cascade).
- Compiler support for full blocks without outer context.
- We have enabled optionInlineTimesRepeat and optionInlineRepeat by default.
- Adding an API in OCBytecodeToASTCache, RBMethodNode and RBBlockNode to map AST nodes to a pc range.
- Add a "parse plugin" mechanism to OpalCompiler.
- Improve faulty parsing.
- A Lots of bug fixes and cleanups.
- Constant Block Closures are created at compile time (speeds up both creating and evaluation of [#blockslikethis])
- Support for ephemerons.
   
### Virtual machine
- Ephemerons are production ready (a large number of Ephemerons supported, leaks fixed, support for old finalization, tests).
- Improving the Memory Map of the VM (Using constant positions).
- Initial support for Single-Instruction Multiple-Data (SIMD)
    - Initialization of new objects using SIMD (ARM64)
    - Adding Bytecode Extensions to support SIMD instructions
    - Adding Vector Registers
    - Vector Register bytecodes
- Third-Party Dependency Update (Newer versions, Graphic Libraries using Hardware Acceleration).
- Fixing errors and simplification of primitives.
- Clean Ups: We have removed a significant amount of old code, notably old experiments, dead code, and unused code such as Newspeak and unused plugins.

## Status
Current Pharo development status:
1. 309 forks on GitHub
2. 972 issues closed since Pharo 10
3. 1412 Pull requests processed since Pharo 10, not counting separately managed projects:
- [http://github.com/pharo-spec/NewTools](http://github.com/pharo-spec/NewTools)
- [http://github.com/pharo-spec/NewTools-DocumentBrowser](http://github.com/pharo-spec/NewTools-DocumentBrowser)
- [http://github.com/pharo-spec/Spec](http://github.com/pharo-spec/Spec)
- [http://github.com/pharo-vcs/Iceberg](http://github.com/pharo-vcs/Iceberg)
- [http://github.com/ObjectProfile/Roassal3](http://github.com/ObjectProfile/Roassal3)
- [http://github.com/pillar-markup/Microdown](http://github.com/pillar-markup/Microdown)
- [http://github.com/pillar-markup/BeautifulComments](http://github.com/pillar-markup/BeautifulComments)
- [http://github.com/pharo-project/opensmalltalk-vm](http://github.com/pharo-project/opensmalltalk-vm)

## Contributors
We always say Pharo is yours. It is yours because we made it for you, but most importantly, because it is made by the invaluable contributions of our great community (yourself).  
A large community of people from all around the world contributed to Pharo 11.0 by making pull requests, reporting bugs, participating in discussion threads, providing feedback and more.  
Thank you all for your contributions!  

## Changelog

The complete list of changes can be viewed on a weekly basis [here](https://github.com/pharo-project/pharo-changelogs/tree/master/weekly). 
