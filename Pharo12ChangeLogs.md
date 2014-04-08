#Pharo version 1.2
The Pharo Project is proud to announce the release of Pharo 1.2.1, the third major release of this clean, innovative, open-source Smalltalk environment.
 

On Tuesday, March 29th 2011, update #12345 was issued to Pharo's 1.2 development line, a line that started back in June 2010 and was frozen in January 2011. Next, Pharo's continuous integration machinery successfully started building various artifacts based on this 'Pharo Core 1.2', the most important one being 'Pharo 1.2' proper, the full featured development image.

Pharo Core 1.2.1 passes 7.836 unit tests, Pharo 1.2.1 no less than 10.760. A large, international community of developers worked hard for several months to iron out all problems and to make Pharo compatible with various Smalltalk libraries and frameworks, among them Seaside 3.0.3 which passes its 1.599 tests.

## Pharo Core Changes
True to the Pharo philosophy, this release contains numerous small changes, refactorings, cleanups and bugfixes improving the overall quality. Important changes include:
* Cleaned the Pluggable hierarchy
* Added new undo framework
* Cleaned Morph and PasteUpMorph
* Added DummyUIManager, a UIManager for operating without a UI
* Added NewTextMorph
* Removed left overs from MVC: PopUpMenu, SelectionMenu and CustomMenu
* Cleaned Utilities, Preferences and TheWorldMenu
* Included SimpleMorphic preview
* Removing empty classes
* Added new TextEditor and SmalltalkEditor
* Added new, clean and simple Glamorous, Glamorous Orange GUI Themes

* Added new Pro GUI Theme
* Added Cog compliant behavior
* Added better blocks debugging
* Better support for separating SmalltalkImage and SystemDictionary
* Fixed package dependencies, providing a good platform for kernel images
* Removed old JIT experiments
* Migrated to MethodReferenceWithSource and friends

* Added more pages under the Help system
* Improved the number of commented classes

* New Finder tool (replacing Messages Names and Method Finder)
* New Recent Changes tool (replacing Recent Submissions)
* Improved SpaceTally
* Fixed pointer finders tools
* Integrated SUnit 4

##Started Continuous Integration: 
use Hudson/Jenkins to automatically build images, run tests, and compile VMs

For the Core 1.2 Image development line, 693 issues were resolved.

##Pharo Changes
The full featured Pharo development image is built automatically by loading the Metacello configuration aptly called ConfigurationOfPharo. Important changes include:
* Updated to latest Metacello and all configurations used to use symbolic versions
* New tools: Metacello Configuration Browser, Memory Monitor, and Autotest
* Updated versions of Shout, RoelTyper, OCompletion, OmniBrowser, AutomaticMethodCategorizer, RefactoringBrowsers, Nile, ProfStef
* Added XML-Support, and more Help
* Removed NewInspector
For the Full Dev 1.2 Image development line, 57 issues were resolved.


##Downloads
You can obtain Pharo 1.2.1 through various downloads:
Pharo 1.2.1 One-Click is the easiest to get started: it includes all needed components (image, change and source file as well as the VM) in one package that requires no installation

* Pharo 1.2.1 the primary developer image, changes and sources file
* Pharo Core 1.2.1 just the core image, changes and sources file

## Success Stories

Pharo has a large user base spread all over the world. Hence there is a growing collection of success stories, projects using Pharo that choose to go public with this. Recently, the following were added:
* DrGeo - an award winning interactive geometry application also used for teaching primary and secondary level students.
* Issys Tracking - a workflow platform to support authorization procedures for the medical practice for a large social organization/health insurance in Argentina.
* Inceptive's Custom ERP - an application for the event planning and resource management administration of a large cultural centre in Flanders.