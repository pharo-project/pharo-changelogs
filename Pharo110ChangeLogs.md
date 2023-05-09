# Pharo 11

A large international community of developers worked hard to prepare a new release of the Pharo platform.

## Highlights

### Tools
- Iceberg (the git client/vcs control tool) has received a lot of tweaks and fixes to work better with github and other remote control files.
- The debugger now incorporates a lot tweaks and notably the capability of adding bindings in the context interation model.
- TimeProfiler (the profiling tool) has a new UI, and incorporates also the alternative Andreas Profiler.
- DrTests (the Test Runner alternative) has been updated to latest Spec and make usable again.
- The is a new new implementation of rewrite tools 
- There is a new tool: The Document Browser, which allow the visualisation of microdown (markadown compatible) documents placed in the web or locally. 
- Calypso (the System Browser) has incorporated some interesting mini tools: package dependency and baseline visualisation.
- New and improved Inspectors (to be used by the inspector), notably for AST/Blocks/IR but also a lot others.
- All versions of NewTools, Spec, Roassal annd Microdown have been updated with a lot of bugfixes. 

### System 

- Slots now have a Setting for unrestricted definitions 
- Slots now allow more complex Slot defininions (cascade)
- Compiler support for full block without outer context
- enable optionInlineTimesRepeat and optionInlineRepeat by default
- Adding an API in OCBytecodeToASTCache, RBMethodNode and RBBlockNode to map AST nodes to a pc range
- add a "parse plugin" mechanism to OpalCompiler
- Improve faulty parsing
- lots of bugfixes and cleanups
- Constant Block Closures are created at compile time (speeds up both creating and evaluation of [#blockslikethis])
- Support for ephemerons
   
### Virtual machine
- 

## Status
Current Pharo development status.
- 309 forks on GitHub
- 972 issues closed since Pharo 10
- 1412 Pull requests processed since Pharo 10, not counting separately managed projects:
	- [http://github.com/pharo-spec/NewTools](http://github.com/pharo-spec/NewTools)
	- [http://github.com/pharo-spec/NewTools-DocumentBrowser](http://github.com/pharo-spec/NewTools-DocumentBrowser)
	- [http://github.com/pharo-spec/Spec](http://github.com/pharo-spec/Spec)
	- [http://github.com/pharo-vcs/Iceberg](http://github.com/pharo-vcs/Iceberg)
	- [http://github.com/ObjectProfile/Roassal3](http://github.com/ObjectProfile/Roassal3)
	- [http://github.com/pillar-markup/Microdown](http://github.com/pillar-markup/Microdown)
	- [http://github.com/pillar-markup/BeautifulComments](http://github.com/pillar-markup/BeautifulComments)
	- [http://github.com/pharo-project/opensmalltalk-vm](http://github.com/pharo-project/opensmalltalk-vm)

## Contributors

We always say Pharo is yours. It is yours because we made it for you, but most importantly because it is made by the invaluable contributions of our great community (yourself).  
More than eighty people directly contributed to Pharo 10.0:  

Thank you all for your contributions.

### Contributors for Pharo 11

@@TODO@@

And many many more who contributed indirectly by reporting bugs, participating in discussion threads, providing feedback etc., etc., etc.


Latest taken into account: === 29/2022


