# Pharo 6.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 6.0 a great release. 
Pharo 6.0 saw a large set of changes, infrastructural improvements and others: more than 1400 tickets got closed. 
Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.
Remember that Pharo is your open-source system!

## Overall

- The PharoVM and image are now provided in 64-bit version in Linux and OSX and brings even better performance and stability
- A new code changes management system named Epica for easier reviewing and recovering of your code
- Integrated support for Git and easy-to-use tool for repositories and commits management named `Iceberg` (as preview for Pharo 7)
- `Unified foreign function interface` (UFFI) for interfacing with the outside world was significantly improved
- Introduction of objects immutability, alternative bytecode sets and block closures independent on outer context 
- The whole Pharo is now able to be bootstrapped from source codes managed by Git and Pharo modularity was improved
- The `Dark Theme` was improved and set as default color theme for Pharo

## All Issues

In Pharo 6 over 1400 fixes and enhancements was integrated. The most significant are:
The complete list of fixed issues is too big to be placed here, but you can review all issues at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). 

Thank you all for your contribution.

### Tools

- `Epicea` - Code changes manager
- `Iceberg` - Git repositories manager
- `GTInspector`, `GTDebugger` and other tools are now based on FastTable to display list of items for better performances
- `GToolkit`, `GTools` update
- `Quality Assistant` improvements
- More reliable interruption by `CMD+.`
- `Playground` variables are now visible from debugger
- `Debugger` temp names mapping is fixed
- _Close all debuggers_ in taskbar context menu
- _Run To Here_ in `GTDebugger`
- Filtering of the results and critiques in the `MessageBrowser`
- Improvements of the `Dependency Analyzer`
- Nautilus 
- - Split large variable entries in the Variables menu
- - Deprecated methods are shown with strikethrough emphasis
- - Abstract classes are shown in italic with a slight color adjustment 

### VM related

- 64-bits support
- Improve host platforms management (32-bit/64-bit)
- Improved UnifiedFFI
- Introduction of objects immutability
- Introduction of `FullBlockClosure` which will help for future evolutions of Pharo 
- `Ephemerons` support, introduce Ephemeron Registry
- Support of alternative bytecode sets and introduction of `Sista Encoder`, the encoder for the SistaV1 bytecode set. This will be the base of future Pharo's improvements 

### Reflectivity

- General improvements
- `haltOnce` is active by default per method. It does not require global turning on and it is managed from source code area in `Nautilus`
- Execution counter for message nodes in source code area in `Nautilus`
- API for `Metalinks` on AST nodes
- Mirror primitives (Those are reflection primitives which access object state without messaging them, see `MirrorPrimitives` class)
- Inlined method const can be implemented by `Metalinks`

### Other

- Dark Theme improvements
- Improvement of theme change while windows are open
- Support of two double quotes inside comments
- Standalone Morphic worlds in separate windows
- StringMorph can now display emphasis underlined (2r100) and strikethrough (2r10000)
- Fix of several memory leaks
- Improve working directory structure (introduction of a `pharo-local` directory to includes Pharo directories as `package-cache`)
- Better autocategorisation of methods
- Introduction of a `FuzzyMatcher` for approximate string matching
- `Glamour` integration in `Spec`
- Renaming (`CMD+R`) in `Nautilus` supports more AST nodes
- `anObject asMethodConst` to cache expressions dynamically
- `GlobalIdentifier` for computer identification
- `NeoUUIDGenerator` replace the old UUIDGenerator
- `STON` was improved and is now used by `Monticello FileTree`
- Storing of suspended announcements 
- Improved `newAnonymousSubclass`
- Inheritable process specific variables
- Fuel improvements
- Enable methods using `<example>` to be easily executed
- Support for `<sampleInstance>`
- New class and methods API for tags as replacement for categories and protocols
- `TabMorph` improvements
- faster source code fetching from .changes & .sources
- Unify `Dictionary` APIs
- Package manifests improvements
- Improve `RadioButton` groups

### Cleanups

- `Object>>#name` is now deprecated and will be removed in Pharo 7
- Tab, TabBar, TabManager, and LockableTab renamed with a Morph postfix
- Better system modularization
- Ability of the system to be fully bootstrapped from source codes
- Turn of catalog search in `Spotter` by default (This improve the stability of Pharo under poor internet connection)
- Remove `Chroma-CubeHelix` and `TxWorkspace`
- Rename `Pragma>>#selector` to `Pragma>>#methodSelector`
- Improve icons management (`#iconNmaed:` was introduce to replace DNUs)
- Limit use of `#asClass` in order to rely on an environment
- It is now possible to give a rewrite rule when deprecating a method to automatically rewrite code with deprecation (`#deprecated:transformWith:`)
- Deprecation of:
    - `Object>>name`
    - `ShortRunArray` class
    - `Object>>confirm:orCancel:`
    - `Object>>ifNil:ifNotNilDo:`
    - `Object>>ifNotNilDo:`
    - `Object>>ifNotNilDo:ifNil:`
    - `Collection>>ifEmpty:ifNotEmptyDo:`
    - `Collection>>ifNotEmptyDo:`
    - `Collection>>ifNotEmptyDo:ifEmpty:`
    - `SequenciableCollection>>copyLast:`
    - `Integer>>asBytesDescription`
    -  `Pragma>>method:`

### Unit testing/Documentation

- `RecursionStopper`: It provides an easy way to check if we are in a recursion and execute code just once in a recursion.
- New process specific variable `CurrentExecutionEnvironment` with values: `DefaultExecutionEnvironment` by default and `TestExecutionEnvironment` during test run
- SUnit improvements: time limit for tests, preventing "forked debuggers"
- New assert extension to compare floats by closeTo:
- More class comments and documentation

### Network

- Support `Server Name Indication` (SNI) in `Zodiac/SSLPlugin`
- `Zinc/Zodiac` update

## Contributors

We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 6.0: 

### Contributors for Pharo 6.0

Abdelghani Alidra,  Clara Allende,  David Allouche,  Nicolas Anquetil,  Thibault Arloing,  Jean Baptiste Arnaud,  Philippe Back, Mangesh Bendre,  Clement Bera,  Alexandre Bergel,  Torsten Bergmann,  Usman Bhatti,  Vincent Blondeau,  Johan Brichau,  Camillo Bruni,  Miguel Campusano, Damien Cassou,  Nicolas Cellier,  Danny Chan,  Andrei Chis,  Christopher Coat,  Ben Coman,  Bernardo Contreras,  Gabriel Omar Cotelli,  Tommaso Dal Sasso,  Paul De Bruicker,  Sean De Nigris,  Christophe Demarey,  Simon Denier,  Marcus Denker,  Martin Dias,  John Dougan,  Stephane Ducasse,  Stephan Eggermont,  Johan Fabry,  Sergio Fedi,  Cyril Ferlicot,  Holger Hans Peter Freyther,  Joshua Gargus,  Tudor Girba,  Thierry Goubier,  Kris Gybels,  Norbert Hartl,  Thomas Heniart,  Dale Henrichs,  Nicolai Hess,  Alejandro Infante,  Henrik Johansen, Goran Krampe,  Pavel Krivanek,  Juraj Kubelka,  Denis Kudriashov,  Matthieu Lacaton, Laurent Laffont,  Kevin Lanvin,  Jannik Laval,  Alexander Lazarević, Skip Lentz,  Max Leske,  Dave Lewis, Esteban Lorenzano,  Sheridan Mahoney,  Mariano Martinez Peck, Max Mattone,  John McIntosh,  Rene Meusel,  Eliot Miranda,  Henrik Nergaard,  Marion Noirbent,  Merwan Ouddane,  Nick Papoulias,  Nicolas Passerini,  Alain Plantec,  Guillermo Polito,  Damien Pollet,  Baptiste Quide,  Alain Rastoul,  Stefan Reichhart,  Lukas Renggli,  Mark Rizun,  Michael Rueger,  Valentin Ryckewaert,  Ronie Salgado,  Udo Schneider,  Boris Spasojevic,  Igor Stasenko,  Roger Stebler,  Serge Stinckwich,  Aliaksei Syrel,  Camille Teruel,  Pablo Tesone,  Yuriy Tymchuk,  Peter Uhnak,  Masashi Umezawa,  Dion Stewart, Sven Van Caekenberghe,  Jan Van De Sandt,  Benjamin Van Ryseghem,  Toon Verwaest,  Franck Warlouzet.

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
