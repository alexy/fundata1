Twitter Replier Graph Format
============================

Our data is a Twitter communication graph, extracted from the gardenhose stream for 35 days in October-November, 2009.  Whenever we saw a tweet which is a reply (`in_reply_to_status_id`), from user `@alice` to `@bob` on a day _d_, we increment `alice,bob` count for that day.  After all 35 days are processed, we end with a map of maps, represented most clearly and concisely in Clojure as follows:

	{:alice 0 {:bob 2 ...} ...}

For each user @Alice who tweeted "@Bob: hey!" and "@Bob: did you see the latest Haskell news?" on November 20, 2009, we'll have an edge

	alice   bob   2009-11-20   2
	
in our `dreps` graph, for "daily replies," and also an edge

	bob   alice   2009-11-20   2   
	
in our `dments` graph, for daily mentions.  The last number is the count of alice->bob <=> bob<-alice tweets for that day.

The graphs are stored as adjacency lists.  For instance, if Alice also tweeted like

	alice	mandy	2009-11-20   
	alice	mandy	2009-11-20
	alice	zack	2009-11-25
	
then the resulting node and its adjacency list in `dreps` will look as follows, now in JSON:

	alice -> {"0":{"bob":1,"mandy":2}, "6":{"zack":1}}
	
Note that for each day, we count how many such directed tweets exist, mapping user names to their respective counts.  We also replace the dates with their consecutive day numbers from the time the data set begins, 0-based.

The whole graph is a map of maps of maps, where the toplevel is a map of _from_ user to his _dayly repliers_, where each _daily repliers_ map is from day to the _to_ user-counts map, mapping _to_ users to the number of times our original _from_ user tweeted to them that day.  In an explicitly typed language it looks like this (OCaml):

	type user    = string
	type day     = int
	type reps    = (user,int) Hashtbl.t
	type adjlist = (day,reps) Hashtbl.t
	type graph   = (user,adjlist) Hashtbl.t

We store our graph in a key-value database, with the key being the user (string) and the value as his/her adjacency list in JSON, as shown above.  We use Tokyo Cabinet as our binary key-value database for the great speed it achieves.  

We supply the graph as one file, `dreps`, and its subsets -- the first 100,000 pairs and the first 1,000,000 million pairs, reflected with `100K` and `1M` after `dreps/dments`.  The suffix `.json.hdb` means that the value is an adjacency list in JSON, as described above, and the whole file is a Tokyo Cabinet `HDB` storage.  The files are then compressed with `p7zip`, the best-rate data compressor currently available.  It is in `p7zip` package on Ubuntu and is present on all dictributions, and Windows and Mac.

Clojure's versions are Tokyo Cabinets where keys are twitter @nicks and values are Google Protobuffers, as implemented by [clojure-protobuf](http://github.com/ninjudd/clojure-protobuf) package.  You can get [cake](http://github.com/ninjudd/cake) to build Clojure systems using them easily, with `cake proto`.