# Pharo 11

A large international community of developers worked hard to prepare a new release of the Pharo platform.

## Highlights

## All issues
Current Pharo development status.
- @@TODO@@ forks on GitHub
- @@TODO@@ issues
- @@TODO@@ Pull requests, not counting separately managed projects such as:
	- [http://github.com/pharo-spec/Spec](http://github.com/pharo-spec/Spec)
	- [http://github.com/pharo-spec/NewTools](http://github.com/pharo-spec/NewTools)
	- [http://github.com/pharo-vcs/Iceberg](http://github.com/pharo-vcs/Iceberg)
	- [http://github.com/pharo-project/opensmalltalk-vm](http://github.com/pharo-project/opensmalltalk-vm)

## ChangeLog
  
### Features

- Updated Fuel (and users of Fuel) to 5.0.4
- Dictionary class<<#newFrom: now accepts duplicated keys
- beginsWith: and endsWith:  return true on empty string
- KeyboardKey with key accessing methods
- Enhance quality rules 
    - missing subclass
    - not optimised if 
- Cleanups for CleanBlock/FullBlock/BlockClosure hierarchy
- better inspections on: Array2D
- Clean Blocks: 
    - Debugger fixes
    - Cleanups for CleanBlock hierarchy
- Debugger 
    - Adding possibility to add bindings in debugger context interaction model
    - Lots of small improvements
    - Lots of small UI fixes and tweaks
    - Cleanups
- Inspector
    - Columns now can be resized
    - Lots of small UI fixes and tweaks
- MetaLinks 
    - can be put on Pragmas
- TestRunner
    - We added a new experimental model
- DoIts (Relevan in playground, etc.)
    - we now can compile DoIts without a method header and without the need of code reformatting (without having to add a return).
- Compiler
    - It can now create methods from a Bytecode IR
- Metamodel
    - Storage of class comments enhanced
    - 

### Speed

- Improve #indexOfMonth: to not create symbols and compare without using #match 
- Major speedup of the SelectorTable
- Reduce Symbol creation during compilation and interactive use
- support for arithmetic SIMD bytecodes 

### Fixes

- printStringLimitedTo:Using: will fail to actually respect limit 
- MiniDrTests raise error 
- Support UTF8 in Git Commit messages
- Fix context menu commands of the StDebugger stack.
- Enabled IM support in SDL2

### CleanUps

- Deprecated10 package removed
- Simplify SymbolTable code
- remove methods that are the same in the superclass
- Image size Reduced
    - Clear SelectorTable
    - Improve Implementation of AllProtocol


## Contributors

We always say Pharo is yours. It is yours because we made it for you, but most importantly because it is made by the invaluable contributions of our great community (yourself).  
More than eighty people directly contributed to Pharo 10.0:  

Thank you all for your contributions.

### Contributors for Pharo 10

@@TODO@@

And many many more who contributed indirectly by reporting bugs, participating in discussion threads, providing feedback etc., etc., etc.


Latest taken into account: === 29/2022


