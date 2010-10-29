fundata1 README
===============

Karmic Social Capital Benchmark
-------------------------------

We provide textual documents in the Markdown format.  While being just plain `.txt` documents, they look best when rendered with markdown-aware tools -- e.g. on `github` this `README.markdown` can be seen at [github as fundata1](http://github/alexy/fundata1). 

_FunData_ is a functional data shootout.  The current shootout, the very first one, is for processing real-world Twitter data.

The results are in!

[fundata1-results.markdown](http://github.com/alexy/fundata1/blob/master/fundata1-results.markdown)

The [server specs](fundata1-server.markdown) where the timings were obtained.

Some interesting lessons are being gathered in

[fundata1-lessons.markdown](http://github.com/alexy/fundata1/blob/master/fundata1-lessons.markdown)

The data format, as distributed, are described in 

[fundata1-replier-graph-format.markdown](http://github.com/alexy/fundata1/blob/master/fundata1-replier-graph-format.markdown)
	
Getting the data is described in the aptly named

[fundata1-getting-the-data.markdown](http://github.com/alexy/fundata1/blob/master/fundata1-getting-the-data.markdown)

The question we're solving is computing Khrabrov and Cybenko's Karmic Social Capital (KSC) for all users communicating via Twitter as present in the data.  The mathematical definition is in the file 

[khrabrov-2010-mind-economy-eccs.pdf](http://github.com/alexy/fundata1/blob/master/khrabrov-2010-mind-economy-eccs.pdf)
	
A textual description of KSC is in 

[fundata1-khrabrov-karmic-social-capital.markdown](fundata1-khrabrov-karmic-social-capital.markdown)	
	
This `git` repository is in fact a supermodule for the three submodules comprising the currently available three reference functional representations of the KSC algorithm.  Each of them is also hosted on `github`, here in the order of appearance in the target language:

* [Clojure KSC -- _badjer_](http://github.com/alexy/badjer)
* [Haskell KSC -- _husky_](http://github.com/alexy/husky)
* [OCaml KSC -- _clams_](http://github.com/alexy/clams)
	
Each of those languages' repos contains further notes on the choices and possible improvements available in their respective implemetations.  Since JVM languages lack an obvious efficient general-purpose serialization, we relax the rules for them a bit.
	
The machine is a SunFire 4320 server with 64 GB of RAM and 8 CPUs.
	
The purpose of having separate repos by language is to facilitate forking and improvement of their implementations, potentially beating other languages.  You're welcome to supply an implementation of the KSC conforming to the rules in other languages, not necessarily functional.  

Some observation on these implementations are posted at [functional.tv](http://functional.tv/).

NOTE: I am submitting my Ph.D. in data mining to UPenn/Dartmouth and am looking for a cool job in the Valley/Seattle, hence my bandwidth in improving my own implementations will be somewhat limited for a while into 2011.  If you have a self-contained implementation installable on CentOS 5 or Gentoo Prefix, or from source with clear steps, I'd be happy to run it, in the Wide Finder spirit.  If you want to speed up the existing implementations, see the [TODO](http://github.com/alexy/fundata1/blob/master/TODO.markdown).

	