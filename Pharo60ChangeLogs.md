#Pharo 6.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 6.0 a great release. Pharo 6.0 saw a large set of changes, infrastructural improvements and others: more than [NUMBER] tickets got closed. Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.  
Remember that Pharo is your open-source system!

New Stuff
---------

- The PharoVM and image is now provided in 64-bit version and brings even better performance and stability
- A new code changes management system named Epica for easier reviewing and recovering of your code
- Integrated support for Git and easy-to-use tool for repositories and commits management named Iceberg (as preview for Pharo 7)
- Unified foreign function interface (UFFI) for interfacing with the outside world was significantly improved
- Introduction of objects immutability, alternative bytecode sets and block closures independent on outer context 
- The whole Pharo is now able to be bootstrapped from source codes managed by Git and Pharo modularity was improved
- The Dark Theme was improved and set as default color theme for Pharo

All Issues
---------

In Pharo 6 a lot of small fixes and improvements was integrated. The most significant are:

new 

- Epicea for code changes
- Iceberg 

vm related

- 64-bits support
- improve host platforms management (32-bit/64-bit), 
- Introductionof FullBlockClosure
- Ephemerons support, introduce Ephemeron Registry
- introduction of objects immutability
- improved UnifiedFFI
- Sista Encoder
- support of alternative bytecode sets

reflectivity

- Reflectivity improvements
- haltOnce is active by default per method. It not requires global turning on and is managed from source code area in Nautilus
- execution counter for message nodes in source code area in Nautilus
- API for metalinks on AST nodes
- mirror primitives
- inlined method const could be implemented by metalinks

other

- support of standalone Morphic worlds in separate windows
- two double quotes inside comments
- fix of several memory leaks
- GToolkit, GTools update
- Quality Assistant improvements
- Glamour integration in Spec
- improve working directory directory structure (introduce pharo-local)
- FuzzyMatcher for approximate string matching
- filtering and critiques in MessageBrowser
- better autocategorisation of method
- cmd+r in Nautilus supports any nodes: message rename, inst var rename, class rename and etc.
- anObject asMethodConst to cache expressions dynamically.
- GlobalIdentifier for computer identification
- NeoUUIDGenerator for UUID generation
- STON was improved and is now used by Monticello FileTree
- storing of suspended announcements 
- improved newAnonymousSubclass
- improve icons management (#iconNmaed: instead of relying on DNU)
- rename #Pragma>>#selector to Pragma>>#methodSelector
- Fuel improvements
- enable <example> methods to be easily executed
- new class and methods API for tags as replacemnt for categories and protocols
- TabMorph improvements
- split large variable entries in the Variables menu
- unify Dictionary APIs
- imrpoved Dependency Analyzer
- package manifests improvements
- improve RadioButton Group
- support for <sampleInstance>
- limit use of #asClass
- Dark Theme improvements, better themes switching

clenaups

- Object>>name deprecation
- turn of catalog search in Spotter by default
- remove Chroma-CubeHelix, TxWorkspace
- ability of the system to be fully bootstrapped
- better system modularization

sunit

- inheritable process specific variables
- new process specific variable CurrentExecutionEnvironment with values: DefaultExecutionEnvironment by default and TestExecutionEnvironment during test run
- SUnit improvements: time limit for tests, preventing "forked debuggers".
- new assert extension to compare floats by closeTo:
- more class comments and documentation

debugger, inspector

- inspector, debugger and ohter tools are now based on FastTable for better performance
- RecursionStopper
- workspace variables are visible from debugger
- improved debugger title for DNU
- debugger temp names mapping is fixed
- more reliable interruption by cmd+.
- "close all debuggers" in taskbar context menu
- "Run To Here" in GTDebugger

network
- suport Server Name Indication (SNI) in Zodiac/SSLPlugin
- Zinc/Zodiac update



Overall list of more than 1400 fixes and enhancemens is to big to be put here, but you can review all issues at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). 

Thank you all for your contribution.

#Contributors
We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the invaluable contributions of our great community (yourself).  More than seventy people directly contributed to Pharo 6.0: 

contributors for pharo 5.0

Abdelghani Alidra,  Clara Allende,  David Allouche,  Nicolas Anquetil,  Thibault Arloing,  Jean Baptiste Arnaud,  Mangesh Bendre,  Clement Bera,  Alexandre Bergel,  Torsten Bergmann,  Usman Bhatti,  Vincent Blondeau,  Johan Brichau,  Camillo Bruni,  Miguel Campusano, Damien Cassou,  Nicolas Cellier,  Danny Chan,  Andrei Chis,  Christopher Coat,  Ben Coman,  Bernardo Contreras,  Gabriel Omar Cotelli,  Tommaso Dal Sasso,  Paul De Bruicker,  Sean De Nigris,  Christophe Demarey,  Simon Denier,  Marcus Denker,  Martin Dias,  John Dougan,  Stephane Ducasse,  Stephan Eggermont,  Johan Fabry,  Sergio Fedi,  Cyril Ferlicot,  Holger Hans Peter Freyther,  Joshua Gargus,  Tudor Girba,  Thierry Goubier,  Kris Gybels,  Norbert Hartl,  Thomas Heniart,  Dale Henrichs,  Nicolai Hess,  Alejandro Infante,  Henrik Johansen, Goran Krampe,  Pavel Krivanek,  Juraj Kubelka,  Denis Kudriashov,  Matthieu Lacaton, Laurent Laffont,  Kevin Lanvin,  Jannik Laval,  Alexander Lazarević, Skip Lentz,  Max Leske,  Dave Lewis, Esteban Lorenzano,  Sheridan Mahoney,  Mariano Martinez Peck, Max Mattone,  John McIntosh,  Rene Meusel,  Eliot Miranda,  Henrik Nergaard,  Marion Noirbent,  Merwan Ouddane,  Nick Papoulias,  Nicolas Passerini,  Alain Plantec,  Guillermo Polito,  Damien Pollet,  Baptiste Quide,  Andreas Raab (RIP),  Alain Rastoul,  Stefan Reichhart,  Lukas Renggli,  Mark Rizun,  Michael Rueger,  Valentin Ryckewaert,  Ronie Salgado,  Udo Schneider,  Boris Spasojevic,  Igor Stasenko,  Roger Stebler,  Serge Stinckwich,  Aliaksei Syrel,  Camille Teruel,  Pablo Tesone,  Yuriy Tymchuk,  Peter Uhnak,  Masashi Umezawa,  Dion Stewart, Sven Van Caekenberghe,  Jan Van De Sandt,  Benjamin Van Ryseghem,  Toon Verwaest,  Franck Warlouzet.


And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
