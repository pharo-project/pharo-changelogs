#Pharo 5.0 

A large, international community of developers worked hard for several months to iron out all problems and to make Pharo 5.0 a great release. Pharo 5.0 saw a large set of changes, infrastructural improvements and others: more than [NUMBER] tickets got closed. Our actions are targeted at building a sound infrastructure on top of which a new generation of systems can be built.  
Remember that Pharo is your open-source system!

New Stuff
---------

- The PharoVM is now based on Spur, the new memory manager, and it brings with it a 35% speedup!
- A new unified foreign function interface (UFFI) replaced NativeBoost to provide a strong Spur-compatible framework for interfacing with the outside world.
- The Glamorous Toolkit now includes the GTDebugger to offer a moldable infrastructure that allows the developer to customize the debugger deeply.
- The underlying Reflectivity mechanism has reached maturity, with multiple pieces coming together to empower developers to instrument their own systems. For example, we now have breakpoints implemented as just a simple extension of this mechanism.
- QualityAssistant is now part of the image to provide live feedback during development.

All Issues
---------
Many changes have been made to support the generation of a more modular system. This release integrates 
quite a large number of fixes and enhancements: more than 2450! List is so big that we cannot put it here 
(it wouldn't make any sense), but you can review all issues at [FogBugz issue tracker](https://pharo.fogbugz.com) (you will need an account there, sorry). 

Thank you all for your contribution.

#Contributors
We always say Pharo is yours. It is yours because we made it for you, but most importantly, because it is made by the invaluable contributions of our great community (yourself).  More than seventy people directly contributed to Pharo 5.0: 

contributors for pharo 5.0

Abdelghani Alidra,  Clara Allende,  David Allouche,  Nicolas Anquetil,  Thibault Arloing,  Jean Baptiste Arnaud,  Mangesh Bendre,  Clement Bera,  Alexandre Bergel,  Torsten Bergmann,  Usman Bhatti,  Vincent Blondeau,  Johan Brichau,  Camillo Bruni,  Miguel Campusano, Damien Cassou,  Nicolas Cellier,  Danny Chan,  Andrei Chis,  Christopher Coat,  Ben Coman,  Bernardo Contreras,  Gabriel Omar Cotelli,  Tommaso Dal Sasso,  Paul De Bruicker,  Sean De Nigris,  Christophe Demarey,  Simon Denier,  Marcus Denker,  Martin Dias,  John Dougan,  Stephane Ducasse,  Stephan Eggermont,  Johan Fabry,  Sergio Fedi,  Cyril Ferlicot,  Holger Hans Peter Freyther,  Joshua Gargus,  Tudor Girba,  Thierry Goubier,  Kris Gybels,  Norbert Hartl,  Thomas Heniart,  Dale Henrichs,  Nicolai Hess,  Alejandro Infante,  Henrik Johansen, Goran Krampe,  Pavel Krivanek,  Juraj Kubelka,  Denis Kudriashov,  Matthieu Lacaton, Laurent Laffont,  Kevin Lanvin,  Jannik Laval,  Alexander Lazarević, Skip Lentz,  Max Leske,  Dave Lewis, Esteban Lorenzano,  Sheridan Mahoney,  Mariano Martinez Peck, Max Mattone,  John McIntosh,  Rene Meusel,  Eliot Miranda,  Henrik Nergaard,  Marion Noirbent,  Merwan Ouddane,  Nick Papoulias,  Nicolas Passerini,  Alain Plantec,  Guillermo Polito,  Damien Pollet,  Baptiste Quide,  Andreas Raab (RIP),  Alain Rastoul,  Stefan Reichhart,  Lukas Renggli,  Mark Rizun,  Michael Rueger,  Valentin Ryckewaert,  Ronie Salgado,  Udo Schneider,  Boris Spasojevic,  Igor Stasenko,  Roger Stebler,  Serge Stinckwich,  Aliaksei Syrel,  Camille Teruel,  Pablo Tesone,  Yuriy Tymchuk,  Peter Uhnak,  Masashi Umezawa,  Dion Stewart, Sven Van Caekenberghe,  Jan Van De Sandt,  Benjamin Van Ryseghem,  Toon Verwaest,  Franck Warlouzet.


And many, many more who contributed indirectly, by reporting bugs, participating in discussion threads, providing feedback, etc.
