Haskell and OCaml collect timings into a list, which can then be saved or output separately; they do it in a fairly monadic way and carrying along the timing list can be abstracted into a state monad.  

* TODO monadify timings in Haskell and OCaml

These timings are absolute for the process.  Clojure uses the `time` macro and emits durations.

* TODO implement absolute in-process timing in a companion list in Clojure

* for all three languages, unify timing output and assemble teh resulting three files into the markdown results table