# Actions in Pharo 1.4

 

All in all, there were over 860 issues treated in the issue tracker: http://code.google.com/p/pharo/issues/list can=1&q=milestone%3D1.4 Not all the changes are reported here, but this is to give you an impression. Thanks a lot for your participation. We all accomplished a huge task.

##Changes

* New code model: Ring
* Support for startUp preference script
* #class message is not a byte code anymore
* Better union and intersection methods
* Better primitive simulation
* Better headless support
* Better support for error at startup
* Introduction of FileSystem 
* Less dependencies: Color, Scrollbar do not depend on Compiler anymore
* Cleaning tests
* Unload hostSystemsMenus
* More consistent API for browser opening
* No event pulling anymore
* More class comments
* Announcement driven system notification
* Better API for sharedPool
 
##Zinc Improvement

New mechanism for Zinc servers start/stop handling after system startUp/shutDown
and a lot a lot and a lot more.

## Tools

* Support Cherrypicking when merging
* Better timeProfilerBrowser
* Better MC commit error
* MC handles better dependencies
* Better Debugger
* Better Inspector
* Search in tools
* New Finder tool
* Cmd-Click for senders and implementors
* Senders and implementors deals with class
* Better tool registry
* Improvements for the FlatBrowser 
* Better Transcripter
* Faster diffBuilder
* New version of OCompletion and Ecompletion that can play together and without code duplication.
 

##UI

* Better search
* MultiSelection  improvements
* Drag and drop in multi selection list
* PluggableListMorph  improvements
* PluggableListMorph  selection on drag
* Iconic Button improvements
* PharoTheme 
* Better CheckBox 
* Enhanced PluggableButtonMorph 
* Polymorph enhancements
* Deprecate PluggableListMorphOfMany 
* Merged NewParagraph  and MultiNewParagraph 
* New Widget: Ticking list and widget
* LazyListMorph  cleaning
* NewTextMorph  and TextComposer  improvements
* Improve behavior of MorphTreeMorph 
* Removing NewTextMorph  and related
* StringMorph 

## Cleaning

* Object
* Old HTTP code
* No references to Utilities
* Removed toolbuilder
* Restructure packages
* Canvas hierarchy
* MorphicModel 
* Deprecate recentMessageSet
* Deprecate ImageSegment 
* Deprecate MessageNames 
* Deprecate TimeProfileBrowser 
* Really cleaning messageSet and subclasses
* SystemChangeNotifier 
* Removed Project
* Removed BlockContext , blue book old closure encodings
* Font downloading
* HandMorph 

##Some Fixes

* Set growth with nil
* Better weak finalization
* isPrime fixed
* Compiler Fixes
* Russian characters in editor
* More class comments
* Fix drawing shadow morphs
* Trait support
* Fixed syntax hilighting
* Better pointersTo:
* Speedup MethodDictionary  #rehash
* Compiler enhancements.
* Stream should not print its contents
* Progress bar
* InputSensor 
* CombinedChar 
* BytexTextConverter  fixes
