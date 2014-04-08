Dear Pharo users,

We are pleased to announce the release of Pharo 1.0. This has been a huge effort since starting the project in May 2008. Pharo 1.0 is just a milestone on our journey, and development of the next version is well underway. We take the opportunity to review the major features of this release.

Community, Infrastructure and Processes

Pharo 1.0 is a product of our community. We thank all of you that have spent time making Pharo better, either directly contributing to the system or helping us making the right decisions.

 

We have established clear processes to track bugs, integrate changes, and manage a release. We have put the following infrastructure in place:

A clean and up-to-date website (www.pharo-project.org),
Google code project for tracking issues and the wiki for developers,
SqueakSource? for MC source code management,
Inria file server for web downloads
A test suite with over 9000 tests (100% pass)
 

MIT license

We have put significant effort into making Pharo license clean. Pharo is now MIT licensed with parts under the Apache License. This is great news! Code that was not MIT licensed was removed from the system and where necessary rewritten from scratch. From the beginning of Pharo we have maintained a strict rule that every contributor has to sign our license agreement.

 

Improved Look and Feel

The overall look and feel as well as new widgets (e.g., toolbar, merge tool) have been introduced from the Polymorph project. UIBuilder is improved and there is a new theme system. Menus are reorganized and cleaned, making them much more usable.

 

We have a new set of subpixel anti-aliased Deja Vu bitmap fonts (from the Cuis project). The default sizes include 7pt (for handheld devices), 9pt (generic text, list, and menu fonts) as well as 12pt (window and title fonts).

In addition, we have Freetype font support, which allows you to use any font installed on your machine.

Bug fixes

We have closed over 1000 issues in our bug tracker. You can find the details here: http://code.google.com/p/pharo/issues/list

 

Major System Cleanup

An incredible amount of dead and duplicated code is removed or cleaned up:

Underscores and hidden character usage in source code
Fileout code - no HTML H1 logic in class source code fileout
Utilities class
MappedCollection?
ReadOnly? binding experiments
PackageOrganizer?
 

Morphic and MVC

Various optimizations and speedup of Morphic applied
Most historic MVC code is removed. There are no more isMorphic conditional tests everywhere
Cleaner package structure

Lots of package dependency cycles are removed. Class extensions were added in the right places.
Package naming conventions in place - we can now unload all the tests
 

Removed Packages

MorphicExamples? is extracted into an external package
The sound system is modularized and put into an external package
SqueakMap? is unloaded
Preferences

Many broken, unused, and obsolete preferences are removed
In addition, many references to preferences caused tangled dependencies. Packages are now ready for Preference removal so that in 1.1 the application logic does not call the preference during execution.
 

Nebraska and Etoy code has been removed. This task is complex and a work in progress.

The Tiling system, colored streams and related stack-oriented experiments are also removed.
The UniClasses? logic is removed. PasteUpMorph? and Morph have also received a lot of cleaning.
 

Traits

Improved and simplified Traits implementation.
Compiled methods are not shared anymore.
 

Tests

All tests pass.
Collection library is cleaned up and a large test suite systematically applied.
Significant test coverage included for collections and streams
 

By cleaning unused objects and code, the memory footprint is significantly reduced: the size of a PharoCore? 1.0 image file on disk is about 8MB (compared to 16MB of a Squeak 3.9 image).

Core Class Improvements

 

Speed improvements

Collection and Number improvements (faster printing, more robust reader)
Faster collections (uses selectorDo: and friends instead of creating intermediate collection
UTF-8 speedup. We have generalized the trick from ByteString?>>#squeakToUtf8 to every converter, which dramatically improves performance of file operations.
 

New or improved

Process-specific variables are now supported
SplitJoin? methods are integrated
CanvasCharacterScanner? and MultiCanvasCharacterScanner? are fixed.
Better doesNotUnderstand: logic
Stream fixes (back, ensures, for example) and use of MultiByteStream?
Better handling of crlf
CompiledMethod? are now more polymorphic with respect to MethodReference?
Implementations introduced for Float #predecessor, #successor etc. Updates to the compact class indexes of LargePositiveInteger? and LargeNegativeInteger?.
Float changes are made to convey their approximate nature.
 

New infrastructural packages added to the core system

Regular Expressions
MD5 and SHA1 secure hash algorithms
Annoucements
 

Compiler

Support for literal ByteArray? syntax is added. Byte arrays can now be written as #2 3? instead of #(1 2 3) asByteArray avoiding the need for conversion and a more compact default representation.
Compiler now throws an exception rather than returning an instance of StringMorph? as its SyntaxError?.
 

Full Closure Support

Pharo now supports full block closure semantics. With full closures you can finally use recursive blocks. Blocks now close over temps correctly. We no longer require the use of #fixTemps. We especially thank Teleplace for funding Eliot Miranda's work and releasing it to the community.

 

New Event Logic

The old polling event logic is replaced with a new event framework. The polling logic has not yet been removed from the core system for backwards compatibility but code should be migrated to use the new infrastructure.

 

Improved Developer Tools

A lot of work has been performed on the developer tools

Faster and thread safe Transcript
Better Message Tally
Gofer, which is a new tool to script Monticello package loading. This is the foundation for Metacello, the new package management system.
A new inspector tool
Refactoring engine cleaned with a new test suite
OmniBrowser? now has all its tests passing and has a lot of fixes
OmniPackageBrowser? has been separated from OmniBrowser? and supports package browsing and traits definition.
SUnit GUI is improved, e.g., with test coverage computation
 

Source Code Management ---------------------- Monticello is improved. Various load-order issues are fixed, making loading of packages more robust. Monticello and PackageInfo? are now faster in several areas making browsing of large repositories significantly faster. A new diff tool is also provided by Polymorph.

Attribution

We thank all the contributors: Adrian Lienhard, Alain Plantec, Alexandre Bergel, Andrew Black, Bart, Gauquie, Cesar Rabak, Cyrille Delaunay, Dale Henrichs, Damien Cassou, Damien Pollet, Dan Corneanu, David Roethlisberger, Douglas Brebner, Esteban Lorenzano, Fabrizio Perin, Fernando Olivero, Gabriel Calero, George Herolyants, Giovanni Corriga, Gwenael Casaccio, Henrik Sperre Johansen, Hernan Wilkinson, James Foster, Jean-Baptiste Arnaud, John McIntosh?, Johan Brichau, Jorge Ressia, Laurent Laffont, Luc Fabresse, Lukas Renggli, Marcus Denker, Mariano Martinez Peck, Martin McClure?, Matthew Fulmer, Michael Rueger, Miguel Coba, Mike Roberts, Nicolas Cellier, Niko Schwarz, Norbert Hartl, Noury Bouraqadi, Oscar Nierstrasz, Peter Hugosson Miller, Philipp Marshall, Rob Rothwell, Serge Stinckwich, Sergio Del Franco, Sheridan Mahoney, Simon Denier, Stephane Ducasse, Stephan Eggermont, Torsten Bergmann

 

Thanks also to external projects from which we integrated changes: Cuis (font support), Polymorph (GUI), Squeak (various fixes), Teleplace (full block closure support)