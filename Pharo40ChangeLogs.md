#Pharo 4.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 4.0 a great release. Pharo 4.0 saw a large set of changes, infrastructural improvements and others: more than [COMPLETE] tickets got closed. Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.  
Remember that Pharo is your open-source system!

In addition, many changes have been made to support the generation of a more modular system. 
This release integrates a quite large (really!) number of fixes and enhancements you can find at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). Ideed, we closed [COMPLETE] tickets! Thank you all for your contribution.

[ REPLACE THIS WITH MARCUS NEW PRESENTATION
The Fosdem14 presentation has a short overview of what is new in Pharo3: 
* Video: https://www.youtube.com/watch?v=son_bhZ93ec 
* Slides: http://www.slideshare.net/MarcusDenker/pharo3-at-fosdem
]

#User interface 
* Dark theme now available

#Infrastructure
* Zeroconf scripts updated. 
* Pharo ppa for ubuntu systems now available.  
* Instead of the one .app directory, we now have three zip files for the three architectures: mac, win and linux.
* As google has shutdown the API support of the Issue Tracker, we moved to FogBugz. (Thank you, Fog Creek!) https://pharo.fogbugz.com
* Downloads have been moved from gforge to a dedicated server at http://files.pharo.org.
* Better staged integration process using Jenkins and github. https://pharo.fogbugz.com

#Kernel

## Slots

## Reflection enhancements

##Compiler

##Debugger

#Graphics

##Morphic now can use Athens
[COMPLETE]

#Tools
We are evolving all the tool set for Pharo with the inclusion of the new GTools!
[COMPLETE]

# Previews

* TxModel
* OSWindow

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
* Pier - the Seaside based CMS
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

This and much more is easily installable with a few clicks right from the Configuration browser in the world menu. Many more Pharo 3.0 projects are available on repositories like Smalltalkhub.com, GitHub and others. 

#Contributors
We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the unvaluable contributions of our great community (yourself).  
In this version contributed directly:  

Jean-Baptiste Arnaud, Simon Allier, Philippe Back, Clément Bera, Alexandre Bergel, Torsten Bergmann, Usman Bhatti, Vincent Blondeau, Noury Bouraqadi, Johan Brichau, Camillo Bruni, Sven Van Caekenberghe, Damien Cassou, Nicolas Cellier, Guido Chari, Dimitris Chloupis, Bernardo Contreras, Ben Coman, Gabriel Omar Cotelli, Jordi Delgado, Tommaso Del Sasso, Gisela Decuzzi, Christophe Demarey, Sean DeNigris, Marcus Denker, Martin Dias, Erwan Douaille, Stephane Ducasse, Stephan Eggermont, Pablo Estefo, Luc Fabresse, Johan Fabry, Hilaire Fernandes, Nahuel Garbezza, Leo Gassman, Lucas Giudice, Tudor Girba, Thierry Goubier, Norbert Hartl, Dale Henrichs, Pablo Herrero, Nicolai Hess, Andre Hora, Alejandro Infante, Ricardo Jacas, Henrik Sperre Johansen, Denis Kudryashov, Pavel Krivanek, Juraj Kubelka, Laurent Laffont, Jannik Laval, Max Leske, David Lewis, Diego Lont, Esteban Lorenzano, Stefan Marr, Mariano Martinez Peck, Roberto Minelli, Hernan Morales Durand, Eliot Miranda, Fernando Olivero, Nicolas Papagna Maldonado, Nick Papoylias, Nicolas Passerini, Vanessa Peña, Nicolas Petton, Alain Plantec, Guillermo Polito, Damien Pollet, Sergi Reyner, Jochen Rick, Benjamin Van Ryseghem, Ronie Salgado, Camille Teruel, Juan Pablo Sandoval Alcocer, Samir Saleh, Frank Shearar, Igor Stasenko, Aliaksei Syrel, Sebastian Tleye, Yuriy Tymchuk, Andres Valloud, Martin Walk, Hernan Wilkinson.

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
