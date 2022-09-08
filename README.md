```clojure
(require '[clojure.spec.alpha :as s])

(s/def ::name string?)
(s/def ::align #{:law :neutral :chaos})
(s/def ::level pos-int?)
(s/def ::magic (s/coll-of string?))

(s/def ::profile
  (s/keys :req-un [::name ::align ::level ::magic]))

(s/conform ::profile
           {:name "r6eve"
            :align :neutral
            :level 4
            :magic ["Functional Programming"
                    "Object-oriented Programming"
                    "Perl-like Programming"
                    "Pulinpa (against Linux Kernel)"]})
```
