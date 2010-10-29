The subdirectory `data/` contains the full replier graph,

	dreps.json.hdb.7z
	
stored as follows:

Tokyo Cabinet HDB with each replying `@username` as key, and his/her dynamic adjacency list as [JSON](http://json.org/).  The exact semantics of the daily ajacency list is described in [the replier graph format](fundata1-replier-graph-format.markdown).  This HDB file is compressed with [7z](http://www.7-zip.org/), the best open-source compressor available.
	
From that, you should be able to produce subsets, and convert them to language-specific storage formats as needed, using the tools provided by each reference implementations.  We provide the first 100,000 subset of _dreps_ sliced off and also ready for loading into each language as follows:
	
* `dreps100K.json.hdb` -- the first 100,000 keys of _dreps_, Tokyo Cabinet HDB with raw JSON, uncompressed
* `dreps100K.clb` -- Tokyo Cabinet of Google Protobuffers with Map extensions from [clojure-protobuf](http://github.com/ninjudd/clojure-protobuf)
* `dreps100K.mlb` -- a dump of OCaml Marshal'led graph from the [clams](http://github.com/alexy/clams) reference implementation
* `dreps100K.hsb.zip` -- a dump of Haskell's graph with strings from the [husky](http://github.com/alexy/husky) reference implementation
* `dreps100K.int.hsb.zip` -- a dump of Haskell integer graph, with the string nicknames interned in `users100K.dic.hsb.zip` custom two-way dictionary from `husky`