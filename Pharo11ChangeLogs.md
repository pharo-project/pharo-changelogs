# Pharo version 1.1

Pharo 1.1.1 was released on October 1, 2010. This is maintenance release is based on Pharo 1.1 and it adds support for the new JIT VM named Cog. In addition it fixes some important bugs in Pharo 1.1. The versions of the external packages was not modified. For CogVM we recommend to use the latest version from www.mirandabanda.org/files/Cog/VM/

Pharo 1.1 was released on July 26, 2010. This is the second release. It provides bug fixes, system cleanup, and new features. In total, 883 issues were resolved and went into this version.

Summary of the work done in 1.1

## Settings framework
Setting is a new Preference framework that supports modularity. No need to have a global Preference class anymore nor having the class Preference hardcoded everywhere. Settings lets you define advanced preferences without tying all the system to one class. Old preferences have been evaluated and migrated when necessary. Thanks Alain Plantec for this cool work.

##New world menu
Menu items are declared using pragmas. That is, they are not hardcoded anymore and hence are easier to extend.

## Core libraries
The collection hierachy has been refactored to have both Set and Dictionary a subclass of HashedCollection instead of having Dictionary a subclass of Set. Pharo now uses a better distributed identityHash for identity sets and dictionaries.

StandardFilestream now performs read-buffering, dramatically speading up some operations like "Object compileAll" (2x improvement) as well as various other operations (scanning change lists etc). This change was taken from Squeak.

A new extensible number parser hierharchy has been introduced NumberParser and its subclasses provide support for parsing and building numbers from strings and streams.

## Smalltalk globals and system queries

SystemDictionary and SmalltalkImage have been refactored. Smalltalk is now an instance of SmalltalkImage, representing a facade for system-wide queries and actions. SmalltalkImage contains a global environment, an instance of SystemDictionary, which the environment used by classes. Thus, SmalltalkImage current == Smalltalk, Object environment == Smalltalk globals.

##Compiler fixes and improvement

Selectors including minus are now parsed correctly. The parser was improve to reject some ill-defined expressions such as '#1' returning 1.

##Cleanup and simplifications

Removal of the required/provided selectors computation code that was in the Traits package for historical reasons. This removes 17 classes with about 240 methods from PharoCore. The code is re-packaged and moved to SqueakSource.

A new general cleanup protocol has been added. The cleanUp protocol takes an optional argument to indicate whether we're doing an aggressive cleanup (which involves deleting projects, change sets, and possibly other destructive actions) or a more gentle cleanup that's only supposed to clean out transient caches. This change was taken from Squeak.

##Improved modularization and smaller production image size

Many small changes in the packaging to get a better modularization (as a preparation for bootstrapping from a minimal kernel image). Repackaged methods holding icons and font definitions to produce smaller images (do "ScriptLoader new cleanUpForProduction"). The resulting image is only 6.2 MB.

## Performance optimizations
Better Identity hashing, encoding conversions, collection changes, rendering speedups (e.g., through inlining a lot of common morph extensions and using Strike fonts by default)
Reading PNG images has been significantly sped up for some common cases. The improvements are in 50-200x range and heavily affect interactive uses of such files.

##Exceptions
OutOfMemory has been added as a standard exception being signaled when an allocation fails, replacing the previous signaling of the low space semaphore. Improved #ensure: performance avoiding remote context manipulation (via #tempAt:put:) in the default case. This change was taken from Squeak.

## SUnit
TestCase assert: show now only take booleans.

## CompilerMethodFormat

We adopted the changes of Igor Stasenko to have a cleaner implementation of compiled method meta information.
Native host menu support for Mac
On Mac VMs the world menu is available as a native menu.
