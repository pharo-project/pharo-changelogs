# Actions in Pharo 1.3

Pharo 1.3 saw a lot of changes to improve important part of the systems. We are really happy and convinced that these changes will give large benefits in the future. We thanks you all that helped us so much. Without you pharo would change slower and would be less fun.

Over 700 items in the issue tracker have been solved in 1.3. A complete list can be found on the Issue Tracker

The Build Server always has the latest release, so please give it a test run! Build Server.

Currently known bugs:

* Core: http://code.google.com/p/pharo/issues/list?can=2&q=milestone=1.3
* Full: http://code.google.com/p/pharo/issues/list?can=2&q=Milestone%3D1.3-DevImage
 

## Cleaning architectural dependencies

We clean a lot of unwanted dependencies between several packages. We applied Moose tools and we will continue to improve the architecture of the system. In particular we will identify better layers in the system. This is important to be able to change large components and to be agile and make certain hypotheses exposed.

## Applying code critics to the complete system

We started to run code critics on the complete system and fix them. We will continue on this path and we will add automated code critics in the hudson build scripts. In particular we removed more than you can expect duplicated code between classes and subclasses. We plan to add Pharo specific Lint Rules and also bring rule checking for all the hosted applications on our hudson server.

## Support for server and headless images

Being able to run Pharo on headless servers is important for web development as well as for building scripts. We introduced a better way of handling non interactive mode. We want to make sure that Pharo can run without UI. Ideally we would like to be able to plug a UI layer on the fly to get a real headless mode but this is clearly future. But at least you know our vision.

* We improved the way the command line works. A new implementation is now available and it can support multiple extensions without conflicts.

* Pharo has now a support for stdin, stdout and stderr.


###More robust and better startup/shutdown. 
At startup and shutdown the image executes the methods startUp: and shutdown: of registered classes (registered using addToStartUpList:, addToShutDownList:, ... methods and friends). Now we improved the robstuness of actions performed at startup by introducing a two stages process. During the first stage of start up the UI manager, the default uimanager is switched to a specific non interactive ui manager (StartupUIManager). Note that this specific non interactive UIManager kills the system on any attempt to open windows and interaction. So be warned, don't use interaction in the first phase. Then all registered classes execute their start up procedures (which should not imply interactive behavior). After startup list is finished, any deferred startup actions are executed, which you can add using the method addDeferredStartupAction: method. This change is important since it structures the startup and make sure that certain actions only occurs when they can run.

# Better look and feel

We copied the work done for Moose and reorganize a bit the themes. We deprecated some old ones. We will continue to improve this aspect.

## Better widgets

In general we believe that the core widgets should be more powerful. We did a lot of progress there and we will continue our effort.

## Better support for syntax highlighting.
Now we introduced a NullStyler? to be able to have a more modular system.

##Deprecation of ParagraphEditor, introduction of TextEditor
We deprecated ParagraphEditor and use the new text editor. We got a better TextMorph?, with a better find/replace behavior. There is now a really powerful text selection that can show automatically all the occurrences of a selection in the complete text. This makes code changes really fast. The visual impact is excellent.

PluggableTextEditorMorph was a funky and somehow duplicated class so it got deprecated.
 

Better PluggableListMorph and friends
PluggableList Morph was improved in multiple fashions. Multiple selection is now supported. List items can be searched then the focus on a new item can be driven using keyboard. PluggableListMorph can now behaves like a multiple selection list. This behavior can be switched on the fly. (MultipleListOfMany, PluggableIconListMorphOfMany are now deprecated since PluggableListMorph can do the same). Benjamin van Ryseghem did an excellent job there.

MorphTreeMorph speed was improved.
Deeper merge of Polymorph.
We continued to integrate deeper Polymorph into the system and revisit also some polymorph choices.

## Better GeneralScrollPane. 
Now it supports both spaceFill and shrinkWrap.
* Cleaner and simpler Modal mode (no more thisContext usage). We remove duplicated code in addition.
* MorphTreeMorph keystroke event handling now accept an event.
* We removed the left over of ST-80 old and nearly unused classes.
* Now menus should be created via UIManager so that they do not break the non interactive mode.
 

#Better tools

Our goal is to be able to get models for all the tools and to rewrite all the basic tools so that we can deprecate the old hierarchy around StringHolder. We made good progress there. Benjamin van Ryseghem really helped a lot for this task.

Tools are now accessed via Smalltalk tools toolName. A tool at class side should implement #registerToolsOn: method. This method will be executed automatically for all classes, when you issue
Smalltalk resetTools. Note, that with tools registry, you are no longer need to keep (and implement) a singleton pattern per each tool class, which requires it , i.e.SomeTool default doSomething. instead, with using registry, you can register a sole tool instance (or class) to registry , and then just write Smalltalk tools someTool doSomething.

* RecentMessageList, the Finder and Senders and implementors underlying widgets were totally rewritten.
* Better Monticello branch encoding.
* Better debugger menu context.
* Huge amount of little fixes.
* New time profiler.
* StringHolder hierarchy got a lot of deadcode and other cleaning action.
* Deferred UI messages was now better handled.
* Speeding up the Help browser by 50%.

After a long discussion that started at ESUG last year, we started to remove toolbuilder dependences. We should be able to remove ToolBuilder?. ToolBuilder was a good idea: a set of specification objects abstracted the common widgets and some of the existing tools were using it. It was potentially good to port the current and fixed set of tools to new UI frameworks. The current problems were that there is no new UI framework on the horizon and second the default tools could not take advantage of the new UI widgets of Polymorph. So since we would really like to get a new set of powerful widgets and since ToolBuilder  did not support an existing need, we will remove it. If the need arrives, we may reimplement it.
 

#New libraries or Enhancement

Support for more robust Announcements infrastructure is now in place and used. The problems we faced were, how can we make sure that solid and tested code can be executed when sometimes end-users code can break the loop executing system code. A typical example is announcement, event handling, ui rendering thread.
A new method on:fork: is introduced, on error it will manipulate the stack and fork a process with the part containing the error. This lets in particular the execution of non broken behavior continue to run. This changes will bring a lot of stability and robustness in the system in key core places. The logic of the UI thread will be rewritten to take advantage of it.

#Weak Announcements
Announcements are important and we improved the first naive implementation. Support for weak announcements was first added. Then announcement took advantage of the on:fork: introduction. It makes sure now that all system announcement will be delivered.

* WeakOrderedCollection  needed for Magma has been added.
* Generator was added.
* Stratified Proxy Often when you build proxy, you cannot control all the messages sent to the proxy because the proxy implementation relies on DNU and ProtoObject. We designed a new version which does not suffer such limit based on an not so well known VM hook. Ghost a proxy library is also available.

## Removing Old Undo Framework
We removed the old undo framework and introduced a brand new one working really well. Thanks Alain Plantec

## Cleans
*  Now Set can contain nil.
* Added lots of explicit exceptions for Collections errors (instead of just calling #error:)
* Improved Smalltalk cleanUp, use it in #cleanUpForRelease.
* SystemNavigation  has been further enhanced to work with environments.
* More class comments
Thanks to the wonderful idea of Laurent Laffont we started to systematically comment, uncommented classes!

Old Compiler

While we continued to work on OPAL and in particular its decompiler and various point between layers, we continued to integrate improvements to the old compiler.

Sync with Squeak trunk code base of old compiler
inline #whileTrue:
Cleaning FakePool  usage
Old positional experiments removed from compiler
ifNotNil:, ifTrue: and friends are now added to the literal array and thus are shown when searching for "senders of".
 

# Network

Some defined primitives were not used. Now they are.
Now we use the excellent package Zinc for the HTTP client/server for fetching packages.
 

# Varia

Better systemVersion API
Mail support improvements.
Linux line breaking and copy and paste clipboard.
Serial plugin fixes got introduced.
We started to make sure that we can bootstrap the system. Some fixed points and hidden assumptions were identified and resolved.
We fixed all the senders of == to numbers, as == is not a test for numerical equality.
Add support for Threaded VMs in Process
Cleanup of Tests to make them usable in a continuous integration setting (e.g. remove PCCByCompilationTest)
Cleanups

The system continues to contain a lot of dead code. In the 1.3 release cycle we continued cleaning unused code. We use a combination of two strategies. For one, deprecating code (moving classes and methods to the Deprecated13 package). This allows clients to continue to use this code and slowly migrate. The second strategy is hard and radical deletion.

* Cleaning of ChangeSet, ChangeSorter  and related.
* remove ExternalSettings. A third preferences subsystem that saved preferences in files (unused).
* Deprecation of PCXReadWriter, as this format sees not much use these days.
* Clean up MVC leftovers.
The removal of MVC allowed to do start a major cleanup related to the text model. Paragraph has been replaced by MultiNewParagraph everywhere, lots of unused code was removed from text and canvas classes.

We continued to clean some Etoy leftovers.
* Uniclasses, which complicated the system considerably.
* Imports, Tiles, random unused code.
* We evaluated and cleaned the startup list and actions. We removed a lot of obsolete ones. Some should be fixed.
* Duplicated code related to encoding of temps in CompiledMethods  was removed. Simplifies considerably understanding (and future cleanup) saving the image embedded in the vm executable has been removed. Simplifies image snapshot
* Cursor cleaning.
* Deprecated13 contains 26 classes, 786 Methods with over 5000 lines of Code.
 

# Security

We removed the old security manager as it was not used. Better things will be added in the future.
As a start, there is a new way of dealing with plugin brings in more security and flexibility. Here are two new primitives which are added to the VM. SmalltalkImage >>loadModule: aModuleName loads a module of the given name. Fail if module cannot be found, or cannot be loaded, or failed to initialize. SmalltalkImage >>disableModuleLoading disables a new module loading mechanism for the rest of current session. This operation is not reversible. Any subsequent attempts to load either external or internal module(s) will fail.
