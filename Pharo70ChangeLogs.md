# Pharo 7.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 7.0 a great release. Pharo 7.0 saw a large set of changes, infrastructural improvements and others: more than 2100 tickets got closed. Our actions are targeted at building a sound infrastructure on top of which a new generation of systems can be built. Remember that Pharo is your open-source system!

# Highlights

- Pharo development moved to Github and Pharo is now fully bootstrapped from source
- 64-bit VM for Windows as a technical preview
- Introduction of a modular implementation of Stateful traits (see user documentation [here](https://github.com/pharo-open-documentation/pharo-wiki/blob/master/General/Traits.md))
- Replacement of `Nautilus` by [Calypso System Browser](https://github.com/pharo-ide/Calypso) 
- A complete new version of [Iceberg](https://github.com/pharo-vcs/Iceberg) with a new, more user-friendly interface
- Migration of `Streams` to the `Zinc streams` implementation that is more modular and modern

# All issues

Over 2100 fixes and enhancements were integrated into this release.

As the complete list of fixed issues is too large to be placed here, you can review it on [the FogBugz issue tracker](https://pharo.fogbugz.com) (requires an account). 

## Revolutionary kernel changes
- Pharo is now bootstrapped from source of the core
- Modular stateful traits
- Traits flattening in kernel packages
- New sources file for every bootstrapped version, empty changes
- New class builder
- Binary packages loading (Hermes)
- Use of `Zinc streams` as default streams 
  - migration guideline: https://github.com/pharo-open-documentation/pharo-wiki/blob/master/Migration/MigrationToPharo7.md
- Support for executable and testable example at method level

## Infrastructure changes
- Switch from SmalltalkHub to GitHub
- Tonel code format for better git handling and reading
- Update building infrastructure to Jenkins 2

# Code management
- Introduction of Calypso, the new system browser
- New navigation model    
- Faster UI
- Tabs toolbar instead of single source code panel
- Explicit commands (e.g., add new method) instead of duplicated menu and shortcuts
- Extendable by plugins
- Suitable for the remote scenario
- "Dynamic protocols", supporting multiple tags per method
- No longer requires star convention for class extension
- Visibility option for inherited methods
- Variable view as the special mode for method group view.
- Better keyboard navigation
- And many more improvements

# Iceberg
- A totally rewamped and friendly user interface
- Simplification of solving problems with repositories
- Workflow simplification (follow the repair propositions)
- Better GitHub, BitBucket, GitLab support
- Improved code merging and comparisons
- New code serialization format (Tonel)
- Repositories metadata
- Documentation
-- https://docs.google.com/document/d/14_RmTdA_8ta5I1mipeaxw7hasxKseovnGEOKK8pd8us/edit
- Better error handling, tags support
- Improved Iceberg-Metacello integration
- Credentials store management

# Cleanups
- Remove Nautilus
- Remove UpdateStream
- Remove all Configurations
- Remove ShoreLine-Report
- Remove TxText
- Remove PluggableTabBarMorph
- Remove the old Compiler
- Remove Watery theme
- Remove Versionner
- Remove Komitter
- Remove LegacyWeakSubscription
- Continue on deprecation of FileStream
- Dead code cleanups
- Code organization cleanups
- Unify categorization of common methods
- Cleanups of object inspection protocol
- Start Ring deprecation
- Better structure of packages
- Add more package comments

# Updates
- `Zinc`
- `Epicea`
- `FFI`
- `Metacello`
- `Fuel`

# New projects
- Integration of `Calypso`
- Integration of `WebBrowser`, a utility to open the default web browser of the user on an URL
- Integration of `ReferenceFinder` to find reference paths between objects to help find memory leaks
- Integration of `Hermes`, a binary code loader for Pharo's bootstrap
- Integration as preview of `Refactoring 2`, a re-architecture of the `Refactoring` project
- Integration of `Commander`, a project to implement `Command` design pattern
- Integration of `ClassAnnotation`, a reusable mechanism for first-class annotations in Pharo

# Spec
- Renamed ComposableModel into ComposablePresenter and changed the suffix of all subclasses
- New calendar presenter 
- Spec-Demo (Under Help menu entry)
- Improved Spec linking to domain models

# Look & Feel
- Uses the white theme by default
- Improves themes switching
- Uses a Main menu bar to make Pharo more standard to other applications
- Improvement of the design of the `Taskbar`
- New window management shortcuts
- Better support of fallback bitmap fonts
- Improved Inspector refreshing
- Spotter is now looking for opened windows
- Support for display scale factor
- FastTable improvements

# VM interface
- 64-bit VM for windows as a technical preview
- DoubleWord and DoubleByte arrays
- Added EncoderForSistaV1
- Added read-only literals support
- Improvements and fixes for 64-bit support
- Fixes for FullBlockClosure
- Support of the new bytecode set
- Uses FFI to bridge Pharo with FreeType

# Reflectivity
- Breakpoint improvements
- Introduction of Breakpoint browser (under the `Debugging` menu bar entry)
- Test coverage using metalinks
- Reflectivity and metalink improvements

# Other
- The logic of the `Finder` was fully rewritten
- Startup now running in a fresh process
- Better pin messages
- NewValueHolder and Model API unification
- Better separation of working and image directories
- SortFunctions are now composable
- Better OSWindow support
- Converted rules to the Renraku architecture
- Class and method comment improvements
- Extensible Playground (pageActionOrder:)
- Optional password management for command line handlers
- System dependencies tests
- Unified way to obtain package manifests

## Contributors

We always say Pharo is yours. Is yours because we made it for you, but most important, because is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 7.0: 

Thank you all for your contribution.

### Contributors for Pharo 7.0

Gabriel Omar Cotelli, Gustavo Santos, Marcus Denker, Torsten Bergmann, Esteban Lorenzano, Bernardo Ezequiel Contreras, Guille Polito, Pablo Tesone, Yoan Geran, Stéphane Ducasse, Cyril Ferlicot, Vincent Blondeau, Denis Kudriashov, Julien Delplanque, Tim Mackinnon, Max Leske, Andrew P. Black, Tomohiro Oda, Clément Béra, Ben Coman, Eric Gade, Yuriy Tymchuk, Nicolas Cellier, Biyalou-Sama Asbath, Myroslava, Sean DeNigris, Juraj Kubelka, Noury Bouraqadi, Holger Freyther, Geoff Reedy, Norbert Hartl, Paul DeBruicker, Alain Plantec, Martín Dias, Peter Uhnak, Tomohiro Oda, Benoît Verhaeghe, Santiago Bragagnolo, Wouter van Zuilen, Bernhard Pieber, Damien Pollet, Geoff Hill, Hans-Martin Mosner, Ronie Salgado, Philippe Back, Aliaksei Syrel, Dayne Guerra, Rafael Luque, Serge Stinckwich, Vincent Aranega, Hernán Morales Durand, Petr Fischer, Rajula Vineet Reddy, Alexandre Bergel, Esteban A. Maringolo, Jan Blizničenko, Johan Brichau, Luc Fabrese, Quentin Ducasse, Sébastien Roccaserra, Stephan Eggermont, Sven Van Caekenberghe, Takano Mitsuhiro, Pavel Krivanek, Allex Oliveira, Christophe Demarey, Lionel Akue, Nicolai Hess, Martin McClure, Alistair Grant, Pierre Tsapliayev, Milton Mamani, Matteo Marra, Thomas Dupriez, Asbathou Biyalou-Sama, Henrik Nergaard.

And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.

