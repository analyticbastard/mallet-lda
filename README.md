# mallet-lda

This project is a minimal Clojure wrapper over the LDA topic modeling
implementation from [MALLET], the MAchine Learning for LanguagE
Toolkit.

[MALLET]:http://mallet.cs.umass.edu/

## Installation

The latest stable release is 0.1.1.

Add this `:dependency` to your Leiningen `project.clj`:

```clojure
["marcliberatore.mallet-lda" "0.1.1"]
```

Feedback and pull requests welcome!

## Usage

```clojure
(ns example
  (:require [marcliberatore.mallet-lda :refer [make-instance-list lda]]
            [marcliberatore.mallet-lda.misc :refer [load-sample-documents]]))

...

;; for example:

(let [data [[1 ["a" "little" "lamb"]]  
            [2 ["row" "your" "boat"]]
            ...]
      instance-list (make-instance-list data)]
  (lda instance-list))
  
;; or, if you're working in a cloned copy of this repository:
(lda (make-instance-list (load-sample-documents))) 
;; (the above won't work with the JAR, as it does not include the sample documents.)
```

## Changelog

- *0.1.1*
  - Added `mallet-lda.misc` namespace, which contains functions to load data into the format expected by `mallet-lda`.
  - Added sample data in `resources`; see `mallet-lda.misc/load-sample-data` for an example of how to load this data.

- *0.1.0*
  - Initial release.

## Sample Documents

The data in `resources/sample-data` is the `web` dataset from MALLET.

> This sample data includes the text of 24 "featured articles" from
> Wikipedia, 12 from the English version, and 12 from the German
> version. They were retrieved in December 2008. The text is in UTF-8
> encoding.

## TODO

Write an idiomatic wrapper over the return value of `(lda)`.

## License

Copyright © 2013 Marc Liberatore

Distributed under the Eclipse Public License, the same as Clojure.
