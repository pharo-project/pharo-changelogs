# Pharo 9

A large international community of developers worked hard to prepare a new release of the Pharo platform with innovations like the implementation of a new UI framework that accepts different backends (currently our own, Morphic, plus Gtk3), the use of it to re-implement in a revolutionary way some of the tools of the environment (playground, inspector, debugger, spotter), incorporating the new concept of "object-centric debugging" and a big set of changes in the virtual machine level, from a real AIO event-driven VM to support for ARM64 including the new Apple M1!

But this is just a teaser since we have treated more than 2150 pull requests! 

## Highlights

- Full redesign of the Spec UI framework (new logic, application, style, **GTK3 backend**)
- Tools: 
	- new playground, 
	- new object-centric inspector, 
	- new object-centric debugger.
	- better and new Refactorings
	- class comments are now written in Microdown format (Markdown compatible)
	- classes now can be declared using the new "fluid" api (Preview)
- New completion framework that adapts better to edition contexts and is customizable
- Fast Universal non-blocking FFI, which now uses libFFI as backend.
- Virtual machine
	- Idle VM
	- Support for ARM 64bit
	- Support for Apple M1
	- Built for Ubuntu 18.04, 19.04, 20.04, 21.04, 21.10; Debian 9, 10, Testing; Fedora 32, 32, 34; openSUSE 15.1, 15.2, Tumbleweed; Manjaro; Arch
- When running the UI environment, it now uses Uses SDL 2.0 as backend by default. It supports extended event handling, including trackpad support.
- General speed up due to compiler optimizations and UI simplification
- And many, many more tests.

## All issues
Pharo 9 got an amazing development activity. It saw the rise of enhancements and bug fixes.  
- 252 forks on GitHub
- 1400+ issues
- 2150+ Pull requests, not counting separately managed projects such as:
	- [http://github.com/pharo-spec/Spec](http://github.com/pharo-spec/Spec)
	- [http://github.com/pharo-spec/NewTools](http://github.com/pharo-spec/NewTools)
	- [http://github.com/pharo-vcs/Iceberg](http://github.com/pharo-vcs/Iceberg)
	- [http://github.com/pharo-project/opensmalltalk-vm](http://github.com/pharo-project/opensmalltalk-vm)

## General Speed up
Pharo 9 got a general speed up due to Pragma speed, compiler improvements and the simplification of the UI framework.

## Pharo 9 generalizes executable comments. 
You read the method, and you systematically get examples to show you how to use the message.  
And you can execute the comment (they are also accessible as tests through the DrTest GUI)! 

## New and enhanced refactorings
Pharo 9 made a gret effort on refactorings.  
Pharo 9 is shipped with new refactorings (such as Extract to Setup XXX more?).  
Many refactorings got enhanced. Extract method can now extract a method out of methods in a full hierarchy in one click.  
Refactorings are now accessible in place i.e., instance variables, class variables...

### New refactorings
1. Extract setUp method 
2. Remove senders of method refactoring
3. Copy package as refactoring 
4. Rename package (rename manifest)
5. Merge instance var x in y
6. Move to class side method
7. Create accessors with lazy initialization

### Improved refactors
1. Deprecate method (simple version)
2. Deprecate class
3. Extract method refactoring (comparing btw symbols and strings, show occurrences replaced)
4. Replace senders with another
5. Rename vars (traits)
6. Convert temporary to instance variable (check in the methods and methods of the subclasses if the same name of the temporary variable is used)
7. Push up method refactoring (improve messages)
8. Add access to pushUp and pushDown refactorings from source code
9. Permute parameters when adding an argument
10. Abstract instance variable (now applies abstract methods when there is a reference to more than one variable in a method)

Migrate commands to commander2
- Change to use specific scopes (call refactorings with a selected scope as a model)
	** Add previews to refactorings
- Expose variable refactoring commands
- Auto-select protocol selected when renaming

# Amazing documentation activity
A large set of new books is arriving with Pharo 9. Documenting many aspects of programming
in Pharo:
- Testing in Pharo
- Version control in Pharo
- Calling Foreign Functions with Pharo 
- Pharo with Style
- Zinc 
- Concurrent Programming in Pharo
- Commander 2.0
- Pharo by Example 9 soon out. 

# New Interface Builder
After 7 years of Spec was redesigned and drastically improved.  
Spec 2.0 is the foundation for all the tools of Pharo.  
It is faster and comes with:
- Different layouts and drop the slow interpreter design
- Application concept introduced (support groups of windows)
- New dialog builder
- Styling support
- Dynamic layouts are now simple and the norm
- Transmissions 
- Support for Roassal and Cairo drawings
- Tests
- Multiple back-ends: GTK and Morphic

# New tools 
Pharo 9 comes with three redesigned tools: the inspector, the playground, and a new debugger.  
- Pharo arrives with a brand new inspector that can be extended based on Spec 2.0. Following the GTInspector, any object can have dedicated panes. Now defining advanced panes is as simple as defining a new spec presenter.
- The New playground supports variable sharing between multiple playgrounds.
- The New debugger supports
	- Unique object-centric debugging features: you can halt on only one specific object
	- A plugin architecture for scripting
	- A revamped emergency debugger
	- Architecture to plug different debuggers
-  Pharo 9 includes a new code completion framework opening doors to statically learning. 
In addition, the Pharo parser has been enhanced to support better error handling. 
- Pharo 9 has support for extra larges images (ones that can contain 30 million lines of code).
Special search and completions are provided. 
- An extensible commander framework has been designed and is now in use.

# Great cleanup effort 
Pharo 9 got a large cleanup effort. 
- Glamour and GTTools as well as their private widget sets, got deprecated and replaced by new tools. 
- Spec1 is still deprecated; all tools are being rewritten to take advantage of Spec 2.0 new features.

# Language improvement
Pharo 9 also comes with a set of new language features. 

## Slots
First, a continuous effort has been made to better support for first-class instance variables (Slots)

## Full block closures
All the compiler chain and debugger got adapted to support the new format of block closures.
Such a new format will enable to put in production the dynamic optimizers such as Scorch or variations. It means that future Pharo versions will be able to have modern JIT compiler architecture with speculative optimizers and not just a baseline JIT. 

## New class definition
A new class definition has been designed as presented at ESUG in Slovenia.
It is based on a fluid API that controls the combinatorial explosion of features.

```Smalltalk
SpAbstractPresenter << #SpPresenter
	trait: SpTPresenterBuilder;
	slots: {
			 #application .
			 #focusOrder .
			 #contextKeyBindings => SpObservableSlot .
			 #windowIcon => SpObservableSlot .
			 #aboutText => SpObservableSlot .
			 #extent => SpObservableSlot .
			 #styles };
	tag: 'Base';
	package: 'Spec2-Core'
```

This class definition is optional in Pharo 9 and will be the default version of Pharo 10.

##Microdown
Class comments are now written in Microdown, a retro-compatible version of Markdown
extended with Pillar features. In addition, any class can customize the rendering of the comments
and enhance it.  
Future help will take advantage of Microdown and its architecture.

## "Dynamic call rewriting of deprecated methods" is now systematically used
With Dynamic call rewriting of deprecated methods, Pharo offers a unique feature that supports the automatic migration of your code at runtime. You run your tests or your application and you can get it automatically migrated to the new API.

# More robust and enhanced virtual machine

Pharo 9 saw a massive investment and results on the Virtual machine side.  
It is available for Windows (Intel 64bits/ARM 64bits), Linux (Intel 64bits / ARM 32 bits / ARM 64bits), OSX (Intel 64bits / ARM 64 bits).  
A new VM with
- idle support (no more pulling of events). Better support for server and preserves battery.
- primitive speed improvements in Windows.
- full image-side events handling is now based on SDL2. The complete and total event information is managed at the image level. It supports gesture definition.
- the first fully working ARM-based JIT for Windows, Raspberian and M1. 
- Image can be now embeddable in the executable optionally.
- More stability due to active chasing of difficult to track bugs. Bugs are now all covered by regression tests, even the assembly level  code compaction. 
- Pharo has more than 3000 tests on the VM. These tests have been developed and are run on all platforms on any commits. 
- Builds using OBS: Pharo is built on Arch, Debian10, Debian 90, Fedora 31, 32, 33, raspbian 10, raspbian 90, openSuse Leap 15.1, openSuse Leap 15.2, openSuse Tumbleweed, Ubuntu 18.04,19.04, 20.04, 21.04
- Native windows compilation
	- New UFFI based on [libFFI](https://sourceware.org/libffi/) with speed improvements
	- Clean up of code, repeatible generation of VM code
	- Unification of Socket implementations on the different platform
	- Optional compilation
	- Documentation
	- Cleanup of Plugins

# New threaded architecture
Pharo 9 also comes with a new Threaded FFI support. In fact Threaded FFI is not a single architecture but a set of alternatives that can be chosen depending on the constraints of the OS. TFFI offers adaptability to the different constraints imposed by Cocoa or GTK.

## Contributors
We always say Pharo is yours. It is yours because we made it for you, but most importantly because it is made by the invaluable contributions of our great community (yourself).  
More than seventy people directly contributed to Pharo 9.0: 

Thank you all for your contributions.

### Contributors for Pharo 9

Aaron Bieber, Ackerley Tng, Alban Benmouffek, Ale Cossio, Alexandre Bergel, Alistair Grant, Allex Oliveira, Angela Chia-Ling, Arturo Zambrano, Asbathou Biyalou-Sama, Ben Coman, Benoît Verhaeghe, Carlo Teixeira, Carlos Lopez, Carolina Hernandez, Charles A. Monteiro, Christoph Thiede, Christophe Demarey, Clotilde Toullec, Cyril Ferlicot, Damien Pollet, Daniel Aparicio, David Bajger, David Sánchez i Gregori, Denis Kudriashov, Ellis Harris, Eric Brandwein, Eric Gade, Erik Stel, ErikOnBike, Esteban Lorenzano, Esteban Villalobos, Evelyn Cusi Lopez, Evelyn Cusi Lopez, Ewan Dawson, Francis Pineda, Francis Pineda, Gabriel Omar Cotelli, Geraldine Galindo, Giovanni Corriga, Guille Polito, Himanshu jld, Johan Brichau, Jonathan van Alteren, Jordan Montt, Julien Delplanque, Kamil Kukura, Kasper Østerbye, Kurt Kilpela, Laurine Dargaud, Marco Rimoldi, Marcus Denker, Martin Dias, Martin McClure, Massimo Nocentini, Max Leske, Maximilian Ignacio Willembrinck Santander, Milton Mamani Torres, Moussa Saker, Myroslava Romaniuk, Nicolas Anquetil, Norbert Hartl, Nour Djihan, Oleksandr Zaitsev, Pablo Sánchez Rodríguez, Pablo Tesone, Pavel Krivanek, Philippe Lesueur, Pierre Misse, Rakshit P., Rob Sayers, Roland Bernard, Ronie Salgado, Sean DeNigris, Sebastian Jordan Montaño, Serge Stinckwich, Stephan Eggermont, Steven Costiou, Stéphane Ducasse, Sven Van Caekenberghe, Thomas Dupriez, Théo Lanord, Théo Rogliano, Todd Blanchard, Torsten Bergmann, Vincent Blondeau, Wéslleymberg Lisboa.

And many many more who contributed indirectly by reporting bugs, participating in discussion threads, providing feedback etc., etc., etc.

