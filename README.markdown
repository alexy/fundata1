fundata1 README
===============

Karmic Social Capital Benchmark
-------------------------------

We provide textual documents in the Markdown format.  While being just plain `.txt` documents, they look best when rendered with markdown-aware tools -- e.g. on `github` this `README.markdown` can be seen at [github as fundata1](http://github/alexy/fundata1). 

_FunData_ is a functional data shootout.  The current shootout, the very first one, is for processing real-world Twitter data.

The results are in!

[fundata1-results.markdown](fundata1-results.markdown)

The data format, as distributed, are described in 

[fundata1-replier-graph-format.markdown](fundata1-replier-graph-format.markdown)
	
Getting the data is described in the aptly named

[fundata1-getting-the-data.markdown](fundata1-getting-the-data.markdown)

The question we're solving is computing Khrabrov and Cybenko's Karmic Social Capital (KSC) for all users communicating via Twitter as present in the data.  The mathematical definition is in the file 

[khrabrov-2010-mind-economy-eccs.pdf](khrabrov-2010-mind-economy-eccs.pdf)
	
A textual description of KSC is in 

[fundata1-khrabrov-karmic-social-capital.markdown](fundata1-khrabrov-karmic-social-capital.markdown)	
	
This `git` repository is in fact a supermodule for the three submodules comprising the currently available three reference functional representations of the KSC algorithm.  Each of them is also hosted on `github`, here in the order of appearance in the target language:

* [http://github.com/alexy/badjer](Clojure KSC -- _badjer_)
* [http://github.com/alexy/husky](Haskell KSC -- _husky_)
* [http://github.com/alexy/clams](OCaml KSC -- _clams_)
	
Each of those languages' repos contains further notes on the choices and possible improvements available in their respective implemetations.  Since JVM languages lack an obvious efficient general-purpose serialization, we relax the rules for them a bit.
	
The shootout rules and measurements are described in 

	Twitter-Shootout-Rules.md
	
The current results are in

	Twitter-Shootout-Results.md
	
The purpose of having separate repos by language is to facilitate forking and improvement of their implementations, potentially beating other languages.  You're welcome to supply an implementation of the KSC conforming to the rules in other languages, not necessarily functional.  

Some observation on these implementations are posted at [functional.tv](http://functional.tv/)

	