#Pharo 4.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 4.0 a great release. Pharo 4.0 saw a large set of changes, infrastructural improvements and others: more than 1697 tickets got closed. Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.  
Remember that Pharo is your open-source system!

In addition, many changes have been made to support the generation of a more modular system. 
This release integrates a quite large number of fixes and enhancements you can find at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). Thank you all for your contribution.

The Fosdem15 presentation has a short overview of what is new in Pharo4: 
* Slides: http://www.slideshare.net/MarcusDenker/2015-fosdempharo

New stuff
=========

- GTools 
	- Playground
	- Inspector
	- Spotter
- Slots model instance variables as first class enities and enable meta-programming on this level.
- ShoreLine reporter: submit information automatically when errors happen
- TxModel, a modern text model who works with Athens (Preview)
- OSWindow, a new way to handle windows and input events (Preview)
- Glamour, a mature declarative browser builder
- Dark theme

Updated stuff
=============

- Zinc
	- new object logging
	- improvements to character encoding/decoding
	- improvements to URL parsing
	- bug fixes, simplifications, comments
- Zodiac
	- bug fixes
- Fuel
- Versionner

Important changes
=================

User interface
--------------
- FreeType fonts now default (Source Sans Pro and Source Code Pro)
- Enhances to Nautilus Refactorings 
- Enhances to Nautilus to detect: examples, scripts, initializations
- Enhanced Monticello GUI (including status icons)

Athens
------
- enhanced Morph drawing with Athens (almost all widgets now can be rendered)
- more examples

System
------
- Enhanced Collection hierarchy vocabulary
- Enhanced String vocabulary
- Fixed and important bug in Delay
- TimeStamp class replaced with DateAndTime
- ContextPart and MethodContext classes replaced with Context
- #on:sent:to: Announcer message replaced with #when:send:to:

Compiler
--------
- Many bugs are fixed
- Backends for new bytecode sets
- OpalDecompiler

VM
--- 
- Now can be compiled on Raspbian
- Now can be compiled on FreeBSD
- Added out-of-the-box: libgit2, libssh2, libsdl2
- several small fixes

Cleanups
========

- Lots of Morphic cleanups
- Lots of Spec cleanups

Removals
========

- PackageInfo (replaced by RPackage)
- ObjectExplorer (replaced by GTInspector)
- Spotlight (replaced by GTSpotter)

#External projects and packages

Many existing add-on projects already moved their code to Pharo 4.0 and many new shiny projects already appeared.
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
* CodeCity - 3D visualization engine
* Roassal - 2D visualization engine
* GraphET - charting engine

##Web:

* Seaside - the well know Smalltalk web framework
* Pier - the Seaside based CMS
* Bootstrap - Seaside add-on to to easily use the Twitter Bootstrap library
* Iliad - for modern web applications

##Testing:

* Autotest - a live testing tool
* BabyMock2 - a visual mock object library

##Tools:

* Pomodoro - a pomodoro timer
* TilingWindowManager - to organize your screen

##Applications:

* Phratch - a port of Scratch for Pharo

##Databases:

###Tools
* DBXTalk/Glorp - provides Object-Relational mapping for several database drivers (PostgreSQL, OpenDBXDriver). 
* Voyage - provides Object-Document mapping for MongoDB. 

###Drivers
* OpenDBXDriver - provides access relational databases (MySQL, Oracle, MSSQL, PostgreSQL)
* PunQLite - provides access to the embeddable UnQlite NoSQL database engine
* SQLite3 - provides access the embeddable SQLite3 relational database engine
* MongoTalk - provides access to Mongo databases. 
* Prhiak - provides access to Riak databases.

##For compatibility:

* FFI - the foreign function interface that later got replaced by NativeBoost 
* OldAlien - the Alien interface for external bindings

This and much more is easily installable with a few clicks right from the Configuration browser in the world menu. Many more Pharo 4.0 projects are available on repositories like Smalltalkhub.com, GitHub and others. 

#Contributors
We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the unvaluable contributions of our great community (yourself).  
In this version contributed directly:  

Clara Allende, Jean-Baptiste Arnaud, Jean-Christophe Bach, Philippe Back, Clement Bera, Alexandre Bergel, Torsten Bergmann, Vincent Blondeau, Noury Bouraqadi, Santiago Bragagnolo, Johan Brichau, Sven Van Caekenberghe, Damien Cassou, Nicolas Cellier, Guido Chari, Dimitris Chloupis, Andrei Chis, Ben Coman, Bernardo Contreras, Tommaso Dal Sasso, Jan Van De Sandt, Christophe Demarey, Sean DeNigris, Marcus Denker, Martin Dias, Stephane Ducasse, Stephan Eggermont, Luc Fabresse, Johan Fabry, Hilaire Fernandes, Jerome Garcia, Tudor Girba, Thierry Goubier, Jigyasa Grover, Kris Gybels, Norbert Hartl, Dale Henrichs, Pablo Herrero, Nicolai Hess, Pavel Krivanek, Juraj Kubelka, Jan Kurs, Laurent Laffont, Jannik Laval, Kevin Lanvin, Max Leske, David Lewis, Diego Lont, Esteban Lorenzano, Tim Mackinnon, Attila Magyar, Esteban Maringolo, Stefan Marr, Max Mattone, Martin Mc Clure, Eliot Miranda, Alain Plantec, Guillermo Polito, Damien Pollet, Stefan Reichhart, Mark Rizun, Udo Schneider, Ignacio Sniechowski, Henrik Sperre Johansen, Igor Stasenko, Aliaksei Syrel, Ciprian Teodorov, Camille Teruel, Sebastian Tleye, Yuriy Tymchuk, Peter Uhnak, Andres Valloud, Sven Van Caekenberghe, Thomas Vincent, Jan Vrany, Martin Walk, Richard Wettel, Dmitri Zagidulin

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
