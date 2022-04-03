# Pharo 10

A large international community of developers worked hard to prepare a new release of the Pharo platform.

## Highlights

- Spec 2 major release	
	- all layouts are now dynamic
	- API cleaning	
	- add support for more presenters
- A lot of cleaning
	- lots of code removed (image and VM)
	- Image is smaller (58 instead ion 66 MB)
- Removal of Spec 1 (tools written in Spec 1 have been rewritten in Spec 2)
- Removal of Glamour and GTTools (were not maintained anymore and got rewritten in Spec 2)
- Drop support of V3PlusClosures byte code set
- Removal of unused FFI packages
- Improved debugging infrastructure
- Zinc (HTTP client/server) components update
- Roassal 3 update

## All issues
Current Pharo development status.
- 275 forks on GitHub
- 600+ issues
- 700+ Pull requests, not counting separately managed projects such as:
	- [http://github.com/pharo-spec/Spec](http://github.com/pharo-spec/Spec)
	- [http://github.com/pharo-spec/NewTools](http://github.com/pharo-spec/NewTools)
	- [http://github.com/pharo-vcs/Iceberg](http://github.com/pharo-vcs/Iceberg)
	- [http://github.com/pharo-project/opensmalltalk-vm](http://github.com/pharo-project/opensmalltalk-vm)


### General

- Fluid class definition greatly improved (and now functional, even if not activated by default)
- Improve refactors (push down, extract method, ...)
- Improve code critiques (and migrated to Spec2)
- Improve FileReference (fixes in relative Paths, canonicalization of names)
- Improve quality rules (test categorisation, better explanation of rules) 
- Improve debugging infrastructure (sindarin) 
- Fixes in compiler (when using whileTrue:)
- Fixes on shortcut printing (on OSX)
- Fixes undo/redo in the rubric editor
- Microdown V2 (and beautiful comments) revamped
- Enhanced FFI: exposing the function ABI, add TFProcessLocalWorker.
- All repeated literals in image are now shared.
- Enhanced autocompletion support for large images.
- Fuel serializer now supports stateful traits.
- Metacello implements the function "lock" to avoid further modifications to a loaded project.
- Modularisation work: Keymapping, Freetype, ThreadedFFI, Athens, TaskIT
- Networking: improve ipv6
- Removed GTTools
- Removed Glamour
- Removed Spec1
- Removed unused FFI package (Alien, most of FFI-Kernel)
- Removed old EncoderForV3PlusClosures
- ... and many (many for real) clean ups and small enhancements that would be impossible to sumarize here.

### Spec

- Deprecation of class side defaultSpec, now all layouts can be defined in instance side (but defaultLayout can still be defined in class side, in case of need)
- Deprecation of all withSpec suffixes. Now to open a presenter window you just use #open/#openModal, etc. (this was a lot more work as you may think).
- Added #asWindow, #asModalWindow to allow user to modify the window presenter (adding extent, ot title, for example) without needing to override `initializeWindow:` and before the window is opened.
- All layouts are dynamic and can be modified at run time (API depending the layout). 
- Enhancement SpApplication with notion of iconProvider
- Added some standard dialogs (inform, request, confirm) to SpApplication
- Added a progress bar standard dialog/processor (SpJobListPresenter)
- Enhanced CommonWidgets: SpFilteringListPresenter, etc.
- Many improvements to SpCodePresenter, including syntax highlight, better code operations, text search, etc. 
- Implemented drag&drop (not all widget, but required).
- Enhanced styleSheets usage
- Box, grid and scrollable layouts implement SpTAlignable (to better place its contents).
- Enhanced API for building grid layouts.
- Fix all remaining memory leaks (well, some may remain, as always... but we removed all we found ;)
 
### Newtools

- For the new tools already included in the image, this was largely a maintenance release, with a lot of small improvements in performance and usability.
- Spotter has received several iterations looking to improve its reliability and responsibility. It now incorporates also some improvements oriented to large images too.
- Playground has incorporated hooks allowing better extensibility and received several fixes on how code works (mostly due to fixes on `SpCodePresenter`).
- Debugger received some stability fixes. 
- We incorporated also other migrated tools: Dependency Analyser, Critiques Browser, Font Chooser and several minor tools, allowing the removal of Spec1.
- Increment the amount of tests.
- Fixed printing of object information in inspector, to prevent huge chunks of text.
 
### Roassal3

- The visualisation engine now is in version v0.9.9f, full changelog can be seen here: https://github.com/ObjectProfile/Roassal3/releases

### Virtual Machine
Virtual Machine is now v9.0.13, full changelog can be seen here: https://github.com/pharo-project/opensmalltalk-vm/blob/pharo-9/CHANGELOG.md

- Improving the Socket implementation:
    - Better Out of Band Data Handling
    - Better Name Resolution
    - Faster Handling of Network Events in OSX
- Improvements in the Asynchronous I/O Support and native implementations for each OS
- Improvements in FFI
    - Multiple ABI support
    - Better Marshalling of LargeIntegers
- Improving Debugging in Windows
- Automatic Build and Test in all Platforms (OSX Intel & ARM / Linux Intel & ARM 32/64 / Windows Intel)
- Message Profiling
- Fixes in Floats ARM 32 Bits
- Cleanups / Tests 
- Third Party Libraries Update

## Contributors

We always say Pharo is yours. It is yours because we made it for you, but most importantly because it is made by the invaluable contributions of our great community (yourself).  
More than eighty people directly contributed to Pharo 10.0:  

Thank you all for your contributions.

### Contributors for Pharo 10

Aaron Bieber, Ackerley Tng, Alban Benmouffek, Alejandra Cossio, Aless Hosry, Alexandre Bergel, Aliaksei Syrel, Alistair Grant, Arturo Zambrano, Asbathou Biyalou-Sama, Axel Marlard, Bastien Degardins, Ben Coman, Bernardo Contreras, Bernhard Pieber, Carlo Teixeira, Carlos Lopez, Carolina Hernandez, Christophe Demarey, Clotilde Toullec, Connor Skennerton, Cyril Ferlicot, Dave Mason, David Wickes, Denis Kudriashov, Eric Gade, Erik Stel, Esteban Lorenzano, Evelyn Cusi Lopez, Ezequiel R. Aguerre, Gabriel Omar Cotelli, Geraldine Galindo, Giovanni Corriga, Guille Polito, Himanshu, Jan Bliznicenko, Jaromir Matas, Kasper Østerbye, Kausthub Thekke Madathil, Konrad Hinsen, Kurt Kilpela, Luz Paz, Marco Rimoldi, Marcus Denker, Martín Dias, Massimo Nocentini, Max Leske, Maximilian-ignacio Willembrinck Santander, Miguel Campero, Milton Mamani Torres, Nahuel Palumbo, Norbert Hartl, Norm Green, Nour Djihan, Noury Bouraqadi, Oleksandr Zaitsev, Pablo Sánchez Rodríguez, Pablo Tesone, Pavel Krivanek, Pierre Misse-Chanabier, Quentin Ducasse, Raffaello Giulietti, Rakshit, Renaud de Villemeur, Rob Sayers, Roland Bernard, Ronie Salgado, Santiago Bragagnolo, Sean DeNigris, Sebastian Jordan Montt, Soufyane Labsari, Stephan Eggermont, Steven Costiou, Stéphane Ducasse, Sven Van Caekenberghe, Theo Rogliano, Thomas Dupriez, Théo Lanord, Torsten Bergmann, Vincent Blondeau.

And many many more who contributed indirectly by reporting bugs, participating in discussion threads, providing feedback etc., etc., etc.


