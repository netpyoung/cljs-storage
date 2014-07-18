# WebStorage for cljs

* HTML5 webstorage for clojurescript


## Feature
* provide wrapper for localStorage, sessionStorage

```clojure
(ns cljs-storage.test
  (:require
   [cljs-storage.core :as storage]))

(def x (storage/local-storage))
;; (def x (storage/session-storage))

(assoc! x :a 10)
;=> #<localStorage{":a" "10"}>

(get x :a)
;=> "10"

(for [[k v] x] [k v])
;=> ([":a" "10"])

(dissoc! x :a)
;=> #<localStorage{}>

(assoc! x :a 10)
;=> #<localStorage{":a" "10"}>

(storage/clear! x)
;=> #<localStorage{}>

(reset! x {:a 1 :b 2})
;=> #<localStorage{":a" "1", ":b" "2"}>
```
