#Pharo 3.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 30 a great release.  Pharo 3.0 saw a large set of changes and infrastructural improvements more: more than 2300 tickets got closed. Our actions are targeted at building a sound infrastructure on top of which new generation of systems (graphics, UI, compiler optimisations, ...) can be built.
Remember that Pharo is your open-source system! And this is clear that you can get an impact on Pharo. 

In addition, many changes have been made to support the generation of a more modular system. 
This release integrates a quite large (really!) number of fixes and enhancements you can find @@Here list of bug in pdf@@. Exactly we close 2331 tickets! Thank you all for your contribution. Thank you again.

# Infrastructure

* Instead of the one .app directory, we now have three zip files for the three architectures: mac, win and linux.
* As google is shutting down the API support of the Issue tracker, we moved to FogBugz. (Thank you, Fog Creek!)
* Downloads have been moved from gforge to a dedicated server at http://files.pharo.org.
* Better staged integration process on Jenkins and github thanks for Camillo Bruni for pushing this effort.


#Kernel

##Continuations

Continuations are now part of Pharo by default. They let the developer save the execution flow and restart it later.  Continuations were originally developped for Seaside. Example : You have an object with the instance variable executionFlow.

You save the current execution flow with :
```
Continuation currentDo: [ :cc | executionFlow := cc]
You restart the execution flow with :
  executionFlow value: true
```

##Simple Delayed Execution for Blocks

We introduce new protocols for block delayed execution:
* valueWithInterval: aDelay. Executes the block every x milliseconds specified in arguments. Answers the process, so you can terminate it.
* valueAfterWaiting: aDelay. Waits for a delay, then executes the block. Answers the process so you can terminate it
These messages may slightly be adapted in future version to fit with the overall API.

##Announcements

Announcements are now more flexible. Instead of special classes they can now be any Object implementing #handlesAnnouncement: . In particular it means that now we can use symbols as Announcements. Here is an example:

```
Announcer new 
   on: #FOO send: #bar to: nil;
   announce: #FOO "should raise DNU bar"
```

#AST + Compiler

##AST code cleanup

We deprecated the wrong protocol for AST visitors. Visitors do not accept they visit!  Now the code is clean and really nice. 

To migrate to the new API the following script should do most of the work, one still needs to check the senders of the old selectors before:

```
m := (RBProgramNodeVisitor allSubclasses gather: #methods) 
    select: [ :e | e selector beginsWith: 'accept' ].

m do: [ :e | 
  e methodClass compile: (e sourceCode copyReplaceAll: 'accept' with: 'visit').
  e methodClass removeSelector: e selector ].
```
## Full AST interpreter

Pharo now contains an interpreter for the RB AST that is complete and he able to run all Kernel tests. It means that it covers the full exception and non-local return semantics of Pharo. This interpreter has been used to develop  test coverage tools. Special thanks to Camillo Bruni and Clément Béra.

##Compiler

The Opal Compiler is now the default compiler. Opal is a new compiler frameworks using visitor and Intermediate representation to support optimisations.  Opal is a stagged compiler. It is based on a real visitor and Intermediate representation. A massive amount of improvements have be done to make Opal working smoothly. Opal is a key infrastructure aspect for the next generation. The compiler API has been clean up and simplified. Simplifying all the old methods with large number of arguments has been done.  Support for blockclosures have been fully revisited and improved. Many changes have been made to also clarify the API. Opal is now able to parse totally Pharo. Special thanks for Marcus Denker and Clément Béra. The following paper describes it http://rmod.lille.inria.fr/archives/papers/Bera13a-OpalIWST.pdf

Opal is based on the RB AST.
* It uses RB Parser.
* It is based on an IR backend for byte-code generation and manipulation.
* Opal supports a mapping for debugger uses AST (pc->AST and AST->highlighting).
* This version offers a radical cleanup of compiler related API.
* The Bytecode->AST decompilation is not used anywhere in the system.

##Debugger

There is a new Debugger: it has a real UI-independent model. The new debugger as a first Spec based UI and we can expect in the future to see more advanced features. 

The old debugger was mixing the view and the model. It was complex and hard to understand and extend. Andrei Chis from the SCG (Bern) implemented a complete clean and nice new debugger model that be independently scripted. On top of this model, a new UI similar to the old has been rewritten. Special thanks to Andrei Chis

# CommandLine

The new commandline handling has been enhanced. 

```
./pharo Pharo.image URL --install 
```

One does not need to give the configuration if the configuration name is canonical, e.g. has the same name as the repository. Special thanks to Camillo Bruni for pushing this. 
There is a full chapter in the deep into Pharo book http://www.deepintopharo.com


#Better OS Interaction

Pharo 30 supports direct access to OS Environment via OSEnvironment
```
Smalltalk os env asDictionary inspect
```

#Graphics

Athens a vector graphics canvas is now integrated to Pharo. In the future it will replace all the existing canvases. 
* Athens will be the base for a new generation of a fully vector graphic IDE. Cairo is now supported by default on all platforms. A chapter is under construction. A tutorial and set of examples are available.
* A new class Margin has been introduced to represent 1,2, or 4 number margins. It plays nicely with the widgets specification.

##Cleaning / Improving Morphic

* PasteUpMorph has been cleaned. Now WorldMorph is not hidden inside PasteUpMorph but a nice subclass.
* FontChooser has been cleaned. 
* Color has been simplified and cleaned. In the past Color did not support alpha blending and TranslucentColor was there to play this role. Now there is only one class for Color supporting by default translucency.
* Widget improvements. MorphTreeMorph, Lists and other got improved. 
* New Widgets such as Tabs have been added.
* A new list implementation has been introduced.
* A massive cleanup of layout frame usage has been performed to avoid creating unnecessary rectangles and in particular bogus (negative extent rectangles) creation is avoided. In Pharo 4.0 the class Rectangle should respect by construction the constraint that the height and width of a rectangle should be positive. 

#Spec

Spec a new interface building frameworks has been improved. It is not dependent anymore (or just a bit) from Morphic. new widgets are supported and a ticking window has been introduced.

#Tools

New tools have been developed. One of the idea is to deprecate the old tools and to write the new ones in Spec so that we can reuse the logic.
* New ChangeSorter. A new changeSorter has been developed by B. Van Ryseghem in Spec.
* New Inspector. Implementation based on Spec and the fast NewList. It has been developed by C. Bera and C. Bruni.
* Suggestions. Pharo 30 support AST-based navigation and menu selection. In the Code editor, try option-t on with the cursor in the code, it will open a list of the operation you can perform on the selected code.  Now it is possible to get the only applicable refactorings or senders/implementors based on the AST node on which the cursor is. Thanks Gisela Decuzzi for this great work. 
* Kommiter. By default all the changes you did in your image get published, Komitter allows one to cherry pick the changes that should be published.  Kommitter has been developed by B. Van Ryseghem in Spec.
* Versionner. Versionner helps to generate and manage Metacello configurations. It has been developed by C. Demarey.
* Enhanced Refactorings. Some refactorings had some glitches that are now fixed. 
* Nautilus has been improved to take advantage of the new package representation. Better Code Browser.
Nautilus has been enhanced to simplify some switching and to take advantage of the package tags. Packages can be filtered to improve visibility.
* Enhanced Finder. The finder is a great tool to help finding information. When using the example based find, it has been improved to show the actual classes that effectively matched the examples.
* Enhanced Critics Browser. The critics browser has been cleaned and enhanced.


##Removal of old tools

Hierarchy Browser was not working and it has been removed as part of the complete rebuild of all the tools.
In the future we expect to fully discard the old Browser. A new minimalist browser (emergency browser) is under development.




#Low-Level Meta Model

##New Code Importer

A new code importer has been extracted from the previous implementation. 

##New class Builder

The old class builder was an arcane and magical piece of code responsible for building classes and migrating instances. Thanks Martin Dias and Camillo Bruni for pushing this important effort. 

## Slots are meta objects representing instances

Similarly to classes being first class objects, slots are first class instance variables. Slots are used by the new class builder and in the future slots will be able to drive Opal to generate efficient code to implement different semantics. To know more about slots read the OOPSLA paper of Verwaest, Bruni et al. http://rmod.lille.inria.fr/archives/papers/Verw11a-OOSPLA11-FlexibleObjectLayouts.pdf

## Cleaning Trait implementation

A first cleaning of the trait implementation has been done. Now classes and traits are a bit more polymorphic.

#Enhancements of NativeBoost

Many improvements have been made in NativeBoost. The most important are
* Stack alignment bugs have been fixed. 
* A new tutorial has been developed and is available at https://ci.inria.fr/pharo-contribution/job/PharoForTheEnterprise/lastSuccessfulBuild/artifact/

#Infrastructure

##RPackage

RPackage went from one RPackageSet / multiple RPackages for one Monticello package to one RPackage / multiple RPackageTags for one Monticello package. This has improved synchronisation between Monticello and RPackage, and allowed new operations (promote / demote) and tools (PackageTreeNautilus).

* PackageInfo is not used anymore by the system and ready to be removed from the system. 
* Removal of the old ClassOrganizer.

##FileSystem improvements

 Some aspects of filesystem got revisited and stabilised.

##Keymappings

Keymappings have been introduced. In the future version all the shortcuts will be defined using keymapping. There is a chapter available in the new forthcoming book: https://ci.inria.fr/pharo-contribution/job/PharoForTheEnterprise/lastSuccessfulBuild/artifact/. Thanks Guillermo Polito for this effort. 


###CharacterScanner improvements

The characterScanner has been speed up and cleaned. Special thanks to Tim Rowledge and Nicolas Cellier for their hard work.

#VM

##Sound

Sound plugins on linux are now recompiled and part of the building process.

@@Esteban@@


#Networking

* New version of Zinc and Zodiac. Sven van Caekenberghe continued to systematically improve Zinc our HTTP client/server architecture. 
* Socket leaking external semaphores have been fixed.


#Cleanups

* There was major refactoring/cleanup of DateAndTime.
* More modularization cleanings have been made such as more Polymorph (Polymorph is an extension of Morph) merging into Morphic.
* Language environments have been cleaned to prepare the future cleaning of leading character in string encodings.
* Many hidden dependencies between packages and projects have been cleaned.
* WorldMenu, Preferences and Utilities are finally gone.
* Cleanup of Tools menu.
* Many classes got documented.

#A glimpse at Pharo 40

For Pharo 40 we really want to put in place a building process that takes a small image and build by loading the system everybody uses. It will be based on the expertise built by Pavel Krivanek with his minimal images and the work of Guillermo Polito on bootstrapping the system. There will be a repackaging effort in addition to change to manage the project using Git as a back-end.
From the Vm perspective we will use the new bytecode sets developed by C. Bera and E. Miranda as well as Spur and many other improvements.


#External projects and packages

Many existing add-on projects already moved their code to Pharo 3.0 and many new shiny projects already appeared.
To name just a few examples:

##Frameworks:

* Artefact - easily generate PDF documents
* Pillar - writing docu and books based on wiki syntax
* Log4S - a logging framework
* Roassal3D - a visualization engine
* Scheduler - to schedule timers
* Units - to deal with units
* DBPedia - to access structured content from DBPedia, a Wikipedia project
* Moose - platform for software and data analysis
* GToolkit - Pharo development tools 
* Glamour - data browsing engine
* CodeCity - 3D visualization engine
* Roassal - 2D visualization engine
* GraphET - charting engine

##Web:

* Seaside - the well know Smalltalk web framework
* Bootstrap - Seaside add-on to to easily use the Twitter Bootstrap library
* Iliad - for modern web applications

##Testing:

* Autotest - a live testing tool
* BabyMock2 - a visual mock object library

##Tools:

* ScriptManager - to manage scripts 
* Pomodoro - a pomodoro timer
* TilingWindowManager - to organize your screen

##Applications:

* Phratch - a port of Scratch for Pharo

##Databases:

* OpenDBXDriver - for accessing relational databases
* PunQLite - provides access to the embeddable UnQlite NoSQL database engine
* SQLite3 - provides access the embeddable SQLite3 relational database engine

##For compatibility:

* FFI - the foreign function interface that later got replaced by NativeBoost 
* OldAlien - the Alien interface for external bindings

This and much more is easily installable with a few clicks right from the Configuration browser in the world menu. Many more Pharo 3.0 projects are available on repositories like Smalltalkhub.com, GitHub and others. 

