```clojure
(require '[clojure.spec.alpha :as s])

(s/def ::name string?)
(s/def ::align #{:law :neutral :chaos})
(s/def ::lvl pos-int?)
(s/def ::str pos-int?)
(s/def ::int pos-int?)
(s/def ::mag pos-int?)
(s/def ::vit pos-int?)
(s/def ::spd pos-int?)
(s/def ::luk pos-int?)
(s/def ::magic (s/coll-of string?))

(s/def ::profile
  (s/keys :req-un [::name ::align ::lvl ::str ::int ::mag ::vit ::spd ::luk ::magic]))

(s/conform ::profile
           {:name "r6eve"
            :align :neutral
            :lvl 2
            :str 1
            :int 3
            :mag 3
            :vit 1
            :spd 2
            :luk 1
            :magic ["Functional Programming"
                    "Object-oriented Programming"
                    "Perl-like Programming"
                    "Pulinpa (against Linux Kernel)"]})
```
