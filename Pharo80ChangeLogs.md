# Pharo 8.0

A large international community of developers is working hard to prepare new revolutionary changes for the Pharo platform like the headless VM with support of various new displaying backends, superb debugging experience and seamless integration with the operating system. We are pleased to introduce the new stable Pharo 8.0 release that will allow you to taste the first fruits of their efforts. This release is focused on performance improvements, bug fixes and system cleanups. More than 1500 pull-requests were integrated into the base system, which does not include the heroic work on the new virtual machine, UI framework and other tools.

## Highlights

- mature 64-bit VM for Windows
- alternative headless VM (preview)
	- a virtual machine without integrated support of GUI
	- the user interface is managed by Pharo code directly which brings more flexibility (command-line argument `--interactive` expected to start the IDE window)
	- full backwards compatibility with the old windows management
	- threaded FFI with callbacks support
- better system performance
- many more tests (UI, FFI, ...) and testable documentation via executable comments. Each commit is validated by 64617 tests.
- the new generation of Spec UI building framework (preview)
- new tests management tool called DrTests (preview)
- new code completion engine

## All issues
More than 1500 fixes and enhancements were integrated into this release. For the complete list of changes see the Pharo [GitHub repository](https://github.com/pharo-project/pharo/commits/Pharo8.0).

## Infrastructure changes
- system performance testing on the CI
 Infrastructure changes
- all VM sources managed by Git
 Infrastructure changes
- intensive VM testing
 Infrastructure changes
- bootstrap process documentation improved

## Git support (Iceberg)
- enhanced projects and repositories management.
- improved merging 
- more exposed settings
- faster loading and comparison for projects with big packages.
- closer integration with `Calypso`
- fixes in Tonel format support

## Code management
- new code completion engine
- `Calypso` (system browser)
	- suggestions for class definitions
	- more refactorings
- safer deprecation
- better pool dictionaries support in `Dependency analyzer`
- cursors, shared pools and variables inspectors
- `Enlumineur` (preview) - new code formatter
- better syntax highlighter performance
- branch coloring support in `Hiedra`

## Reflectivity
- more slots examples (`HistorySlot`…)
- better slots integration
- `Reflectivity-Tools` refactoring

## UI building framework (Spec)
- introduction of `Spec 2` (as preview)
	- better support of multiple backends (Morphic, Gtk…)
	- simplified implementation
	- better layouts
	- easier testing
	- applications management

## Look & Feel
- the dark theme as default
- fonts corruption fixes
- more settings for production images
- copy windows title command

## FFI and VM Interface
- `UFFI` 
	- better support of literals
	- more types implemented
	- supports of ThreadedFFI backend
- `OSWindow`
	- improved events and windows management
	- world rendering in different backends
	- more capable backends setting
- `File Attributes Plugin`
	- new file systems properties interface

## New projects

- `DrTests` (preview) - tests management tool with plugins support
- `Clap` - Command line argument parser
- `Beacon` - logging engine
- `SUnit-Visitor` - standardized way to visit test suites
- `Spec 2` (preview) - UI building framework with multiple backends 
- `Commander 2` (preview) - advanced command pattern implementation and documentation [http://books.pharo.org/booklet-Commander/](http://books.pharo.org/booklet-Commander/)

## Performance
- faster Collections implementation
- speed-up of system queries and sources access
- faster Spotter searches
- better class building performance
- SSD friendly read-write streams
- faster `Athens`, examples improvements

## Other
- `Ring` (language meta-model)
	- standalone environment models
	- better support of undefined entities
	- browseable using Calypso
- more executable comments
- read-only image mode
- WeakIdentitySet
- the old editor removal
- pre-debugger improvements
- `Opal` compiler cleanups and enhancements
- cleanups:
	- flags
	- package dependencies
	- baselines 
	- access to globals (system dictionary, `ActiveWorld`…)
	- `Spotter` package structure 
	- `Glamour`/`GT` dependencies
	- methods categorization
	- unused variables
- better mails sending support
- more consistent collections API
- more thread-safe system
- themes switching fixes
- memory leaks fixes
- `Fast Table`
	- fixes, better sorting support
	- variable height rows
- better TelePharo support
- better Gemstone compatibility
- more class comments
- ...and many more small fixes and improvements...

## Contributors
We always say Pharo is yours. Is yours because we made it for you, but most important because it is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 8.0: 

Thank you all for your contribution.

### Contributors for Pharo 8.0

Serge Stinckwich, Myroslava Romaniuk, Hilaire Fernandes, Alexandre Bergel, David Bajger, Sean DeNigris, Theodore Moen, Dayne Guerra Calle, Juraj Kubelka, Max Leske, Santiago Jose Dandois, Alistair Grant, Sabine Mana, Chia Yu, Stephan Eggermont, Milton Mamani, Pavel Krivanek, Ben Coman, Marcus Denker, Pierre Misse, Christophe Demarey, Allex Oliveira, Andreina Cota, Theo Rogliano, Clément Dutriez, Quentin Ducasse, Cyril Ferlicot, Cameron Bierwagen, Marek Niepieklo, Clotilde Toullec, Esteban Lorenzano, Vincent Blondeau, Danil Osipchuk, Eiichiro Ito, Noury Bouraqadi, Oleksandr Zaytsev, Jason Riggs, Alain Plantec, Kasper Osterbye, Leonardo Cecchi, Chi Huynh, Santiago Bragagnolo, Antonio Pierro, Pablo Tesone, Tim Mackinnon, Wesley Duerksen, Wilfred Hughes, John Brant, Evelyn Cusi Lopez, Manuel Leuenberger, Thomas Dupriez, Norbert Hartl, Gabriel Omar Cotelli, Carlo Teixeira, Guille Polito, Torsten Bergman, Damien Pollet, Holger Hans Peter Freyther, Julio Ripoll, Carolina Hernandez Phillips, Julien Delplanque, Hugo Lasnier, James Foster, Will Hensel, Erik Stel, Sven Van Caekenberghe, Martín Dias, Tomohiro Oda, Konrad Hinsen, Sébastien Roccaserra, Stéphane Ducasse, Denis Kudriashov, Ellis Harris, Steven Costiou.


And many many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc., etc., etc.

