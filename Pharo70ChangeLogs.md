# Pharo 7.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 7.0 a great release. Pharo 7.0 saw a large set of changes, infrastructural improvements and others: more than 2100 tickets got closed. Our actions are targeted at building a sound infrastructure on top of which new generation of systems can be built. Remember that Pharo is your open-source system!

# Highlights

- Pharo development moved to Github and Pharo is now bootstraped
- 64bit VM for windows as technical preview
- Introduction of a modular implementation of Stateful traits (See user documentation [here](https://github.com/pharo-open-documentation/pharo-wiki/blob/master/General/Traits.md))
- Replacement of `Nautilus` by [Calypso System Browser](https://github.com/pharo-ide/Calypso) 
- New version of [Iceberg](https://github.com/pharo-vcs/Iceberg) with a new intefrace more user friendly.
- Migrate `Streams` to `Zinc streams` implementation that is more modular

# All issues

Over 2100 fixes and enhancements were integrated in this release.

As the complete list of fixed issues is too large to be placed here, you can review it on [the FogBugz issue tracker](https://pharo.fogbugz.com) (requires account). 

## Revolutionary kernel changes
- Pharo is now bootstraped
- Modular stateful traits
- Traits flattening in kernel packages
- New sources file for every bootstrapped version, empty changes
- New class builder
- Binary packages loading (Hermes)
- Use `Zinc streams` as default streams

## Infrastructure changes
- Switch to GitHub
- Tonel code format 
- Update building infrastructure to Jenkins 2

# Code management
- Introduction of Calypso, the new system browser
  - New navigation model    
  - Faster UI
  - Tabs toolbar instead of single source code panel
  - Explicit commands instead of duplicated menu and shortcuts
  - Extendable by plugins
  - Suitable for the remote scenario
  - "Dynamic protocols", support multiple tags per method
  - Not required star convention for class extension
  - Visibility option for inherited methods
  - Variable view as the special mode for method group view.
  - Better keyboard navigation
  - And many more

# Iceberg
- A new friendly user interface
- Simplification of solving problems with repositories
- Workflow simplification
- Better GitHub, BitBucket, GitLab support
- Improved code merging and comparisons
- New code serialization format (Tonel)
- Repositories metadata
- Documentation
- Better error handling, tags support
- Improved Iceberg-Metacello integration
- Credentials store

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
- Integration of `WebBrowser`, an utility to open the default web browser of the user on an URL
- Integration of `ReferenceFinder` to find reference paths between objects to help find memory leaks
- Integration of `Hermes`, a binary code loader for Pharo's bootstrap
- Integration of `Refactoring 2`, a rearchitecture of the `Refactoring` project
- Integration of `Commander`, a projct to implement `Commander` design pattern
- Integration of `ClassAnnotation`, a reusable mechanism for first class annotations in Pharo

# Spec
- Rename ComposableModel into ComposablePresenter and change the suffix of all subclasses
- New calendar presenter 
- Spec-Demo (Under Help menu entry)
- Improve Spec linking to domain models

# Look & Feel
- Use the white theme by default
- Improve themes switching
- Main menu bar to make Pharo more standard to other applications
- Improvement of the desgin of the `Taskbar`
- New window management shortcuts
- Better support of fallback bitmap fonts
- Improved Inspector refreshing
- Spotter is looking for opened windows
- Display scale factor
- FastTable improvements

# VM interface
- 64bit VM for windows as technical preview
- DoubleWord and DoubleByte arrays
- Add EncoderForSistaV1
- Read-only literals support
- Improvements and fixes for 64-bit support
- Fixes for FullBlockClosure
- Support of the new bytecode set
- Use FFI to bridge Pharo with FreeType

# Reflectivity
- Breakpoints improvements
- Introduction of a Breackpoint browser (under the `Debugging` menu bar entry)
- Test coverage using metalinks
- Reflectivity and metalinks improvements

# Other
- The logic of the `Finder` was rewritten
- Startup running in a fresh process
- Better pin messages
- NewValueHolder and Model API unification
- Better working and image directories meaning separation
- SortFunctions composable
- Better OSWindow support
- Convert rules to the Renraku architecture
- Class and method comments improvements
- Extensible Playground (pageActionOrder:)
- Optional password management for command line handlers
- System dependencies tests
- Unify way to obtain package manifests
