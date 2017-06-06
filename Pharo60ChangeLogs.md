# Pharo 6.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 6.0 a great release. 
Pharo 6.0 saw a large set of changes, infrastructural improvements and others: more than 1400 tickets got closed. 
Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built.
Remember that Pharo is your open-source system!

## Highlights

- Pharo is now provided in 64-bit version in Linux and macOS and brings even better performance and stability (beware, 64bits version is a new technology and a small amount of tests is still failing)
- A new code changes management system named Epicea for easier reviewing and recovering of your code easily
- Integrated support for Git through an easy-to-use tool for repositories and commits management named `Iceberg` (as a preview for Pharo 6, it will be the default in Pharo 7)
- `The unified foreign function interface` (UnifiedFFI) for interfacing with the outside world is significantly improved
- The PharoVM is now part of OpenSmalltalk initiative
- Introduction of object immutability, alternative bytecode sets and block closures independent of outer context 
- Pharo can now be bootstrapped from source code managed by Git
- Pharo modularity is improved
- Pharo is faster
- The `Dark Theme` was improved and set as default color theme of Pharo

## All Issues

Over 1400 fixes and enhancements were integrated in this release.

As the complete list of fixed issues is too large to be placed here, you can review it on [the FogBugz issue tracker](https://pharo.fogbugz.com) (requires account). 

### Tools

- `Epicea` provides a code changes manager
- `Iceberg` provides a Git repositories manager
- `GTInspector`, `GTDebugger` and other tools are now based on FastTable (long lists of items are rendered much faster)
- `GToolkit`, `GTools` have been updated
- `Quality Assistant` has been improved
- Interrupt key (`Cmd+/`, `Ctrl+.`) has been made more reliable
- `Playground` variables are now visible from debugger
- `Debugger` temp names mapping is fixed
- There is a "_Close all debuggers_" in the taskbar context menu
- _Run To Here_ in `GTDebugger`
- Filtering of the results and critiques in the `MessageBrowser`
- `Dependency Analyzer` has been improved
- `Nautilus` enhancements  
- - Splitting of large variable entries in the Variables menu
- - Deprecated methods are shown with strikethrough emphasis
- - Abstract classes are shown in italics with a slight color adjustment 

### VM related

- 64-bits support
- Improvement of host platforms management (32-bit/64-bit)
- Improved UnifiedFFI
- The PharoVM is now part of OpenSmalltalk initiative (https://github.com/OpenSmalltalk/opensmalltalk-vm)
- Introduction of object immutability
- Introduction of `FullBlockClosure` which will help for future evolutions of Pharo 
- `Ephemerons` support, introduction of the EphemeronRegistry
- Support of alternative bytecode sets and introduction of `Sista Encoder`, the encoder for the SistaV1 bytecode set. This will be the base of future Pharo's improvements 

### Reflectivity

- General improvements
- `haltOnce` is active by default per method. It does not require global turning on (enable haltOnce) and it is managed from the source code area in `Nautilus`
- Execution counter for message nodes in the source code area in `Nautilus`
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
- Improvement of working directory structure (introduction of a `pharo-local` directory to include Pharo directories as `package-cache`)
- Better autocategorization of methods
- Introduction of a `FuzzyMatcher` for approximate string matching
- `Glamour` integration in `Spec`
- Renaming (`Cmd+R` / `Ctrl+R`) in `Nautilus` supports more AST nodes
- `anObject asMethodConst` to cache expressions dynamically
- `GlobalIdentifier` for computer identification
- `NeoUUIDGenerator` replaces the old UUIDGenerator
- `STON` was improved and is now used by `Monticello FileTree`
- Storage of suspended announcements 
- Improved `newAnonymousSubclass`
- Inheritable process specific variables
- Fuel improvements
- Enablement of `<example>` methods so that they can be executed easily
- Support for `<sampleInstance>`
- New class and methods API for tags as replacement for categories and protocols
- `TabMorph` improvements
- faster source code fetching from .changes & .sources
- Unification of `Dictionary` APIs (including an `OrderedDictionary`)
- Package manifests improvements
- Improvement of `RadioButton` groups

### Cleanups

- `Object>>#name` is now deprecated and will be removed in Pharo 7
- Tab, TabBar, TabManager, and LockableTab renamed with a Morph postfix
- Better system modularization
- Ability for the system to be fully bootstrapped from source code
- Turn off catalog search in `Spotter` by default (This improves the stability of Pharo when used with poor Internet connections)
- Removal of `Chroma-CubeHelix` and `TxWorkspace`
- Rename of `Pragma>>#selector` to `Pragma>>#methodSelector`
- Improvement of icons management (`#iconNmaed:` introduced in order to replace DNU-based icons)
- Limit use of `#asClass` in order to rely on an environment
- It is now possible to give a rewrite rule when deprecating a method to automatically rewrite code with deprecation (`#deprecated:transformWith:`)
- Deprecation of the following:
    - Object>>#name
    - Object>>#confirm:orCancel:
    - Object>>#ifNil:ifNotNilDo:
    - Object>>#ifNotNilDo:
    - Object>>#ifNotNilDo:ifNil:
    - Behavior>>#layout
    - Behavior>>#layout:
    - BitBlt class>>#current
    - BlockCannotReturn>>#deadHome
    - BlockCannotReturn>>#deadHome:
    - Collection>>#groupBy:having:
    - Collection>>#ifEmpty:ifNotEmptyDo:
    - Collection>>#ifNotEmptyDo:
    - Collection>>#ifNotEmptyDo:ifEmpty:
    - CompiledMethod>>#getSource
    - DebugAction>>#keyText:
    - DiskStore>>#basicCreationTime:
    - DiskStore>>#basicModificationTime:
    - DiskStore>>#basicSize:
    - FilePluginPrims>>#size:
    - FileSystem>>#creationTime:
    - FileSystem>>#size:
    - FileSystemStore>>#basicCreationTime:
    - FileSystemStore>>#basicSize:
    - FileSystemStore>>#creationTime:
    - FileSystemStore>>#modificationTime:
    - FileSystemStore>>#size:
    - HashedCollection>>#someElement
    - IconStyler>>#iconProvider
    - Integer>>#asBytesDescription
    - MIMEDocument>>#type
    - MemoryStore>>#basicCreationTime:
    - MemoryStore>>#basicModificationTime:
    - MemoryStore>>#basicSize:
    - Point>>#scaleTo:
    - Pragma>>#method:
    - Pragma>>#selector
    - SequenceableCollection>>#copyLast:
    - SmalltalkImage>>#evaluate:
    - TBehavior>>#propertyValueAt:
    - TBehavior>>#propertyValueAt:ifAbsent:
    - TBehavior>>#propertyValueAt:put:
    - TestResult>>#correctCount
    - some other methods in externally managed packages (get complete list by `SystemNavigation default allMethods select: #isDeprecated`)
    
### Unit testing/Documentation

- `RecursionStopper` provides an easy way to check if we are in a recursion and execute code just once in a recursion.
- New process specific variable `CurrentExecutionEnvironment` with value `DefaultExecutionEnvironment` by default and `TestExecutionEnvironment` during a test run
- SUnit improvements: time limit for tests, preventing "forked debuggers"
- New assert extension to compare floats with `closeTo:` 
- More class comments and documentation

### Network

- Support `Server Name Indication` (SNI) in `Zodiac/SSLPlugin`
- `Zinc/Zodiac` update

## Contributors

We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 6.0: 

Thank you all for your contribution.

### Contributors for Pharo 6.0

Alberto Bacchelli, Alejandro Infante, Alexandre Bergel, Aliaksei Syrel, Alistair Grant, Andrei Chis, Ben Coman, Bernardo Contreras, Bernhard Pieber, Boris Spasojevic, Christophe Demarey, Clement Bera, Cyril Ferlicot, Dale Henrichs, Damien Cassou, Damien Pollet, Dave Lewis, Denis Kudriashov, Dirk Roeleveld, Eliot Miranda, Esteban Lorenzano, Esteban Maringolo, Evan Donahue, Federico Balaguer, Franck Warlouzet, Glenn Cavarle, Guillermo Polito, Gustavo Santos, Henrik Johansen, Henrik Nergaard, Hilaire Fernandes, Holger Hans, Jan Kurs, Jan van de Sandt, Johan Fabry, Juraj Kubelka, K. K. Subramaniam, Ken Causey, Kris Gybels, Lionel Akue, Luc Fabresse, Lucas Godoy, Marcus Denker, Mariano Martinez Peck, Marion Noirbent, Martin Dias, Max Leske, Maxime Roelandt, Merwan Ouddane, Matteo Bellotto, Miguel Campusano, Milton Mamani, Myroslava Romaniuk, Nicolai Hess, Nicolas Cellier, Nicolas Passerini, Norbert Hartl, Offray Luna, Pablo Tesone, Paul De Bruicker, Pavel Krivanek, Peter Uhnak, Philippe Back, Roger Stebler, Ronie Salgado, Sean DeNigris, Serge Stinckwich, Skip Lentz, Sophie Kaleba, Stefan Reichhart, Stephan Eggermont, Stephane Ducasse, Sven Van Caekenberghe, Thibault Arloing, Thibault Arloing, Thibault Raffaillac, Thierry Goubier, Thomas Heniart, Tommaso Dal Sasso, Torsten Bergmann, Tudor Girba, Udo Schneider, Valentin Ryckewaert, Vincent Blondeau, Werner Kassens, Yuriy Tymchuk

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.
