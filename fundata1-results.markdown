* the full dynamic replier graph is loaded in the fastest way your language can make it
* it's inverted for the algorithm to have both from and to versions
* users are clustered by the first day they got on Twitter
* 35 days are iterated, updating the Karmic Social Capital
* the results are written to disk in the fastest way fathomable
* all times are for each stage in seconds; user tally is mashed together with the first day for Haskell and OCaml


point      | Clojure | Haskell | OCaml |
-----------|---------|---------|-------|
load graph | 164 |  52 |   6
invert it  | 148 |  66 |  55
user tally | 200 |  32 |  42
 1  |  11  |     |	
 2  |  16  |  5  |	10
 3  |  18  |  9  |	16
 4  |  22  |  9  |	20
 5  |  24  |  7  |	13
 6  |  25  | 12  |	15
 7  |  28  | 13  |	20
 8  |  29  | 24  |	23
 9  |  29  | 13  |	27
10  |  31  | 14  |	19
11  |  93  | 15  |	19
12  |  37  | 19  |	20
13  | 100  | 15  |	21
14  | 101  | 16  |	24
15  | 118  | 20  |	35
16  | 103  | 15  |	31
17  | 103  | 16  |	21
18  |  38  | 20  |	23
19  |  40  | 41  |	24
20  |  43  | 17  |	25
21  | 119  | 12  |	35
22  |  46  | 18  |	42
23  | 131  | 20  |	30
24  | 124  | 22  |	26
25  | 140  | 19  |	28
26  | 140  | 22  |	27
27  | 159  | 24  |	28
28  |  48  | 24  |	39
29  |  54  | 23  |	46
30  | 148  | 24  |	37
31  | 159  | 24  |	29
32  |  55  | 24  |	31
33  |  58  | 24  |	30
34  | 179  | 25  |	35
35  |  33  | 13  |	31
save | N/A | 228 |	41
total | 2808 [a][] | 1034 [b][] | 1046 [c][]

* [a]: Clojure result write time is Not Acceptable and is not included in its total
* [b]: Haskell uses IntMap and interns strings in a Trie, hence writes/reads a dictionary
* [c]: OCaml does not compress its dump at  the same time as its output, while Haskell does


Memory Results
--------------

* Clojure is the best, running in -Xmx30g with -XX:+UseCompressedOops
* OCaml fits in about 45 GB
* Haskell fits in about 50 GB.  Now.