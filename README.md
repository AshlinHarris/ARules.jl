# ARules

[![Docs](https://img.shields.io/badge/docs-stable-blue.svg)](https://juliahealth.org/ARules.jl/stable) [![Build Status](https://travis-ci.org/JuliaHealth/ARules.jl.svg?branch=master)](https://travis-ci.org/JuliaHealth/ARules.jl) [![codecov.io](http://codecov.io/github/JuliaHealth/ARules.jl/coverage.svg?branch=master)](http://codecov.io/github/JuliaHealth/ARules.jl?branch=master) [![DOI](https://zenodo.org/badge/95671564.svg)](https://zenodo.org/badge/latestdoi/95671564)

This package is not actively maintained.
For data mining in Julia, see <https://github.com/JaredSchwartz/RuleMiner.jl>.

## 1. Installation
```julia
julia> Pkg.add("https://github.com/bcbi/ARules.jl")
```

## 2. Frequent Itemset Generation
The `frequent()` function can be used to obtain frequent itemsets using the
_a priori_ algorithm. The second and third arguments allow us to control the
minimum support threshold (either as a count or proportion) and the maximum
size of itemset to consider, respectively.
```julia
julia> using ARules

julia> transactions = [["milk", "eggs", "bread"],
                       ["butter", "milk", "sugar", "flour", "eggs"],
                       ["bacon", "eggs", "milk", "beer"],
                       ["bread", "ham", "turkey"],
                       ["cheese", "ham", "bread", "ketchup"],
                       ["mustard", "hot dogs", "buns", "hamburger", "cheese", "beer"],
                       ["milk", "sugar", "eggs"],
                       ["hamburger", "ketchup", "milk", "beer"],
                       ["ham", "cheese", "bacon", "eggs"]]

julia> frequent(transactions, 2, 6)				# uses a-priori algorithm
```

## 3. Association Rule Generation
The `apriori()` function can be used to obtain association rules.
```julia
julia> using ARules

julia> transactions = [["milk", "eggs", "bread"],
                       ["butter", "milk", "sugar", "flour", "eggs"],
                       ["bacon", "eggs", "milk", "beer"],
                       ["bread", "ham", "turkey"],
                       ["cheese", "ham", "bread", "ketchup"],
                       ["mustard", "hot dogs", "buns", "hamburger", "cheese", "beer"],
                       ["milk", "sugar", "eggs"],
                       ["hamburger", "ketchup", "milk", "beer"],
                       ["ham", "cheese", "bacon", "eggs"]]


julia> rules = apriori(transactions, supp = 0.01, conf = 0.1, maxlen = 6)
```


