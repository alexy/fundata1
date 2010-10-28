README file for the FunData1
============================

Karmic Social Capital Benchmark
-------------------------------

We provide textual documents in the Markdown format.  While being just plain `.txt` documents, they look best when rendered with markdown-aware tools -- e.g. on `github` this `README.md` can be seen at [http://github.com/alexy/fundata/](github). 

FunData is a functional data shootout.  The current shootout, the very first one, is for processing real-world Twitter data.

The data format, as distributed, are described in 

	Twitter-Replier-Graph-Format.md
	
Getting the data is described in the aptly named

	Getting-the-Data.md

The question we're solving is computing Khrabrov and Cybenko's Karmic Social Capital (KSC) for all users communicating via Twitter as present in the data.  The mathematical definition is in the file 

	Khrabrov-Karmic-Social-Capital.pdf
	
A textual description is in 

	Khrabrov-Karmic-Social-Capital.md
	
This `git` repository is in fact a supermodule for the three submodules comprising the currently available three reference functional representations of the KSC algorithm.  Each of them is also hosted on `github`, here in the order of appearance in the target language:

	[http://github.com/alexy/badjer](Clojure KSC -- _badjer_)
	[http://github.com/alexy/husky](Haskell KSC -- _husky_)
	[http://github.com/alexy/clams](OCaml KSC -- _clams_)
	
Each of those languages' repos contains further notes on the choices and possible improvements available in their respective implemetations.  Since JVM languages lack an obvious efficient general-purpose serialization, we relax the rules for them a bit.
	
The shootout rules and measurements are described in 

	Twitter-Shootout-Rules.md
	
The current results are in

	Twitter-Shootout-Results.md
	
The purpose of having separate repos by language is to facilitate forking and improvement of their implementations, potentially beating other languages.  You're welcome to supply an implementation of the KSC conforming to the rules in other languages, not necessarily functional.  

Some observation on these implementations are posted at [functional.tv](http://functional.tv/)

	