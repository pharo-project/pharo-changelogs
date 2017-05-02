# Pharo 6.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 6.0 a great release. 
Pharo 6.0 saw a large set of changes, infrastructural improvements and others: more than 1400 tickets got closed. 
Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.  
Remember that Pharo is your open-source system!

## New Stuff

- The PharoVM and image is now provided in 64-bit version and brings even better performance and stability
- A new code changes management system named Epica for easier reviewing and recovering of your code
- Integrated support for Git and easy-to-use tool for repositories and commits management named Iceberg (as preview for Pharo 7)
- Unified foreign function interface (UFFI) for interfacing with the outside world was significantly improved
- Introduction of objects immutability, alternative bytecode sets and block closures independent on outer context 
- The whole Pharo is now able to be bootstrapped from source codes managed by Git and Pharo modularity was improved
- The Dark Theme was improved and set as default color theme for Pharo

## All Issues

In Pharo 6 over 1400 fixes and enhancements was integrated. The most significant are:

### Tools

- Epicea - code changes manager
- Iceberg - Git repositories manager
- Inspector, Debugger and other tools are now based on FastTable for better performance
- GToolkit, GTools update
- Quality Assistant improvements
- more reliable interruption by `CMD+.`
- Playground variables are visible from debugger
- Debugger temp names mapping is fixed
- "close all debuggers" in taskbar context menu
- "Run To Here" in GTDebugger
- filtering and critiques in MessageBrowser
- split large variable entries in the Variables menu
- improved Dependency Analyzer

### VM related

- 64-bits support
- improve host platforms management (32-bit/64-bit), 
- improved UnifiedFFI
- introduction of objects immutability
- introduction of `FullBlockClosure`
- Ephemerons support, introduce Ephemeron Registry
- Sista Encoder
- support of alternative bytecode sets

### Reflectivity

- Reflectivity improvements
- haltOnce is active by default per method. It does not require global turning on and it is managed from source code area in Nautilus
- execution counter for message nodes in source code area in Nautilus
- API for metalinks on AST nodes
- mirror primitives
- inlined method const can be implemented by metalinks

### Other

- Dark Theme improvements, better themes switching
- support of two double quotes inside comments
- standalone Morphic worlds in separate windows
- fix of several memory leaks
- improve working directory structure (introduce pharo-local)
- better autocategorisation of method
- FuzzyMatcher for approximate string matching
- Glamour integration in Spec
- renaming (`CMD+R`) in Nautilus supports more AST nodes
- `anObject asMethodConst` to cache expressions dynamically.
- `GlobalIdentifier` for computer identification
- `NeoUUIDGenerator` for UUID generation
- STON was improved and is now used by Monticello FileTree
- storing of suspended announcements 
- improved `newAnonymousSubclass`
- inheritable process specific variables
- Fuel improvements
- enable `<example>` methods to be easily executed
- support for `<sampleInstance>`
- new class and methods API for tags as replacement for categories and protocols
- `TabMorph` improvements
- unify Dictionary APIs
- package manifests improvements
- improve RadioButton Group

### Cleanups

- `Object>>#name` deprecation
- better system modularization
- ability of the system to be fully bootstrapped from source codes
- turn of catalog search in Spotter by default
- remove Chroma-CubeHelix, TxWorkspace
- rename `Pragma>>#selector` to `Pragma>>#methodSelector`
- improve icons management (`#iconNmaed:` instead of relying on DNU)
- limit use of `#asClass`

### Unit testing

- `RecursionStopper`
- new process specific variable `CurrentExecutionEnvironment` with values: `DefaultExecutionEnvironment` by default and `TestExecutionEnvironment` during test run
- SUnit improvements: time limit for tests, preventing "forked debuggers".
- new assert extension to compare floats by closeTo:
- more class comments and documentation

### Network

- support Server Name Indication (SNI) in Zodiac/SSLPlugin
- Zinc/Zodiac update

The complete list of fixed issues is too big to be placed here, but you can review all issues at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). 

Thank you all for your contribution.

## Contributors

We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 6.0: 

### Contributors for Pharo 6.0

Abdelghani Alidra,  Clara Allende,  David Allouche,  Nicolas Anquetil,  Thibault Arloing,  Jean Baptiste Arnaud,  Philippe Back, Mangesh Bendre,  Clement Bera,  Alexandre Bergel,  Torsten Bergmann,  Usman Bhatti,  Vincent Blondeau,  Johan Brichau,  Camillo Bruni,  Miguel Campusano, Damien Cassou,  Nicolas Cellier,  Danny Chan,  Andrei Chis,  Christopher Coat,  Ben Coman,  Bernardo Contreras,  Gabriel Omar Cotelli,  Tommaso Dal Sasso,  Paul De Bruicker,  Sean De Nigris,  Christophe Demarey,  Simon Denier,  Marcus Denker,  Martin Dias,  John Dougan,  Stephane Ducasse,  Stephan Eggermont,  Johan Fabry,  Sergio Fedi,  Cyril Ferlicot,  Holger Hans Peter Freyther,  Joshua Gargus,  Tudor Girba,  Thierry Goubier,  Kris Gybels,  Norbert Hartl,  Thomas Heniart,  Dale Henrichs,  Nicolai Hess,  Alejandro Infante,  Henrik Johansen, Goran Krampe,  Pavel Krivanek,  Juraj Kubelka,  Denis Kudriashov,  Matthieu Lacaton, Laurent Laffont,  Kevin Lanvin,  Jannik Laval,  Alexander Lazarević, Skip Lentz,  Max Leske,  Dave Lewis, Esteban Lorenzano,  Sheridan Mahoney,  Mariano Martinez Peck, Max Mattone,  John McIntosh,  Rene Meusel,  Eliot Miranda,  Henrik Nergaard,  Marion Noirbent,  Merwan Ouddane,  Nick Papoulias,  Nicolas Passerini,  Alain Plantec,  Guillermo Polito,  Damien Pollet,  Baptiste Quide,  Alain Rastoul,  Stefan Reichhart,  Lukas Renggli,  Mark Rizun,  Michael Rueger,  Valentin Ryckewaert,  Ronie Salgado,  Udo Schneider,  Boris Spasojevic,  Igor Stasenko,  Roger Stebler,  Serge Stinckwich,  Aliaksei Syrel,  Camille Teruel,  Pablo Tesone,  Yuriy Tymchuk,  Peter Uhnak,  Masashi Umezawa,  Dion Stewart, Sven Van Caekenberghe,  Jan Van De Sandt,  Benjamin Van Ryseghem,  Toon Verwaest,  Franck Warlouzet.

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
