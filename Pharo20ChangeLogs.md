Actions in Pharo 2.0

Here is a log of all the actions done in 2.0. The idea is not to replicate the bug tracker, as it is easy to get a complete list here. Instead, the idea is to have a list of the major improvements with some explanations.

#UI

We started a long term effort on the Pharo UI.

##Spec a new way to build UI. 

We started to rethink the way we build user interfaces in Pharo. Spec has been developed by Benjamin van Ryseghem under the guidance of Stéphane Ducasse. Spec is based on a declarative syntax to specify user interfaces and on valueHolder port composition. Spec supports widgets definition, reuse and composition. New widgets can be created by composing existing widgets. Many existing tools have been reimplemented using Spec. We wrote a tutorial for Spec. Spec will be used for the UIPainter that we will develop for Pharo 3.0. In Pharo 3.0 we will revisit and improve Spec. One of the idea is that Spec should be independent of Morphic so that we can use it to build native tools or with Amber.

##Widget enhancements. 
Several important widgets were greatly enhanced. This effort was led by Benjamin van Ryseghem. For example, multiple selection and single selection lists were unified. A new widget list has been developed from scratch and it exhibits massive speed improvements.

##Layout improvements/cleanups. 

We improved the protocol used for creating LayoutFrame. We cleaned its implementation and simplify clients code. Now instance of layoutFrame are systematically well initialized. Clients do not need to check against nil values and a new protocol avoids to be forced to specify rectangle when only one number is required.

## Keybindings. 
Keybindings is a new library developed by Guillermo Polito to manage key bindings. We started to use it to define widgets keybinding as well as menu shortcut. In Pharo 3.0 we will systematically rewrite all the hard-coded bindings with it and write a documentation. It supports:
* source code navigation
* running tests
* basic refactoring
* creating classes
and many more shortcuts: see "Shortcuts Description" in the window menu (triangle on the top right) in Nautilus

##New icons (famfam). 
Pharo now uses new icons. We are looking for designers that could help us to define the UI look of the future Pharo versions.

##"Growl" style notifications. 
To avoid to get UI blocked by simple notifications, Pharo now uses a growl like notification systems.
##Revamp progress bar.
We started to rewrite the progress bar framework. We introduced the Job class and notification to specify progress bar.

##Rectangle intersection improvements. 
Rectangle intersection is a central part for UI redrawing and invalidating screen regions. Rectangle intersection is then an important functionality. We started to address the problem of the non-specification of the intersection of non overlapping rectangles. We introduced the intersect:ifNone protocol. As a side effect this improves the damage recording mechanisms and provide a faster system.
Developer tools

##Nautilus browser. 
Nautilus, a new code browser has been developed by B. van Ryseghem. It supports: in place hierarchy, groups, refactorings, multiple views, icon navigation and many other features. Nautilus has a plugin infrastructure so everybody can use existing plugin or write new ones. Nautilus is fully navigable using shortcut. In Pharo 3.0 we plan to rewrite Nautilus using Spec.

##Critics browser. 
From Pharo 2.0 on we want to systematically run rule checking rules. We revisited the SmallLint rules to customize them to Pharo and we better documented them. We developed a new browser that will helps you to apply SmallLint rules. In particular it supports the notion of todos. We can mark an issue as a false positive or as todos and get the bar green. We wrote a complete chapter on the Critics Browser. We will start to work on an infrastructure to systematically evaluate SmallLint rules on the projects published in the Pharo distribution.

##Omnipresence of the Refactoring Engine. 
We believe that Pharo itself should use the best tools it has to change itself. This is why we decided to introduce the Refactoring Engine and SmallLint rule checkers. Note that this move to integrate extra tool is not against our vision to produce a minimal core. Once we have fast fuel based package loading we will be able to remove Metacello from the core.
 

##Improved version diff browsing. 
We improved the diff and merging tool.
 

##Spotlight. 
Spotlight is a ubiquitous tool to find classes and methods. You can activate it just press shift+enter.
Revamp E/O Completion and smart chars. In the past, smart characters (automatically closing parenthesis, single quote...) did not play well with auto completeion. In addition, they were duplicated functionality between two automatic ecompletion algorithms. In Pharo 2.0 we unified the two algorithms under a single umbrella and integrate them smoothly with smart-characters.

##Interactive navigation using "ctrl/cmd+click" over classes/methods. 

Now Pharo supports the interactive navigation of source code using cmd/ctrl-click on selectors and class names in the source-code [implementors, senders, users].
Shout themes. Several syntax highlighting themes have been defined.

##Andreas profiler. 
As a tribute to Andreas Raab, we included an alternate profiler developed by Andreas.
Networking

##New version of Zinc. 
Zinc is developed by Sven Van Caekenberghe. New versions of Zinc the http client/server library has been integrated.
 

## Zodiac (SSL). Z
odiac is an extension of Zinc to support SSL connections.
 

#System

##System Announcer. 
Pharo had a change notification system. A change notification system is important because tools can register to events to update or react without getting coupled with the system. The problem was that the previous change notification broadcasted only symbols and not plain objects. It was limiting the power that we can get about first class objects. In addition not all the events were raised and competing with Announcements (announcements raised plain objects). In Pharo 2.0, we redefined system events as Announcements, introduced a System Announcer whose responsibility is to raise announcement for all the events and removed the old SystemChangeNotifier. This sets up the basis for the future communication between tools.

##RPackage replacing PackageInfo. 
PackageInfo is a way to identify if a method belongs to a package. The implementation is based on dynamic queries. Such queries it leads to problems to produce new generation browser and tools. We defined a new implementation of the package management of Pharo. The idea is to represent package as real objects. In Pharo3.0 we will continue to remove the dependency to PackageInfo.
##Manifest: Package metadata. 
We introduce the notion of package metadata. Package metadata are used
to manage all false positives or todos of SmallLint so that you do not have to check all the time rule results. Each package can now have a class named ManifestNameOfXPackageNameX. It will be the place to add documentation and other information.

##Command line tools / Headless mode. 
We really want to make sure that Pharo can be used in non interactive mode and that we can pass scripts to it on the command-line. For this reason we continued to work on making sure that Pharo can be used headless. In particular we introduced a new way to handle command line parameters. See pharoVM my.image --help and pharoVM my.image --list
st Handle .st source files

* Fuel Handle fuel files
* config Install and inspect Metacello Configurations from the command line
* save Rename the image and changes file
* test Run tests from command line
* update Load updates
* printVersion Print image version
* eval Evaluate directly passed-in one line script


##Native boost. 
NativeBoost is a library that generates assembly code on the fly. It is used to generate FFI calls. By default NativeBoost is included mostly for future use. In Pharo3.0 vector graphics will be used and Nativeboost will be used to invoke the graphics primitives.

##Ring metamodel. 
Ring is a new meta model introduced in Pharo 1.4. It is used to represent code that is not currently executed. Ring has an API that is polymorphic with a subpart of the core executing entities of Pharo (Class and CompiledMethod). This has the nice property that the tools that manipulate such entities can also manipulate ring objects. Hence Ring supports of image browsing. In Pharo 3.0 we will rewrite certain tools to use ring and deprecate some abstractions like pseudo-classes and file packages.

##Fuel. F
uel is one of the fastest and versatile object serializer. In Pharo 2.0, we decided to use fuel as a default serializer. In particular, on error the execution stack is saved now in fuel format. Therefore it is possible to reopen a debugger on a similar image for debugging purpose.

##Freetype fonts. 
We offer now a better handling of freetype fonts and their management.

##Metacello: a universal package map.
Metacello is a framework to describe is included in the default image. In the future Pharo will be managed by Metacello. The idea also is that once we have fast fuel based package loading we will be able to remove Metacello from the core.
 

#Kernel

##New object-oriented and powerful filesystem.
The old library to support file was dated and cumbersome to use. This version of Pharo uses FileSystem a new framework developed by Colin Putney. We revisited and integrated deeply into Pharo core. A full chapter is available in the new book http://rmod.lille.inria.fr/pbe2/. The work includes a complete removal of FileDirectory. There is a compatibility package to support the transition. Enjoy the new and clean API.

##DateAndTime refactoring. 
All the DateAndTime internals are now UTC-based. This prevents bugs in certain edge-cases where the image is moved through different time-zones, most prominently for daylight saving time.
 

#VM

* Latests cog builds
* SSLPlugin
* FilePlugin enhancements
* SocketPlugin fixes
* Included libraries: freetype2, cairo
* Large Cleanups

# Cleanings

# FileDirectory removal. 
FileDirectory the old file system has been removed. It is packaged as a separate package to support migration to Pharo2.0.

##Deprecation of old serialization framework.
ReferenceStream and SmartRefStream are removed. In addition, DataStream is cleaned to be only used by Monticello. For a general purpose serializer, use Fuel instead.

##Large amount of bugs fixes. 
You already guessed in addition we integrated a lot of small improvements, cleanups and bug fixes.

#Continuous Integration

##Zeroconf scripts.
Weren't you fed up not be able to install Pharo from a single command line or to pass it arguments?
Using a nice debugger and an interactive environment development does not mean that Pharo developers do not value automatic scripts and love command line. Yes we do and we want the best of both worlds! Since Pharo 2.0, Pharo supports a way to define and handle command line argument and offer zero conf scripts. We even wrote a chapter on them. Here is a nice start with a zero-conf bash scripts: wget --quiet -O - http://files.pharo.org/script/ciPharo20PharoVM.sh | bash

##CI for everything. 
A new infrastructure to support continuous integration is now in place.
* First new images and vms are mirrored under http://files.pharo.org/
* Second the key parts of pharo are automatically built on https://ci.inria.fr/pharo/
* Third community project can be hosted at http://ci.inria.fr/pharo-contribution/
