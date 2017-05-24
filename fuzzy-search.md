# Fuzzy Search Algorithms
## Context matters
### Entity resolution (us vs usa)
## Common algorithms
### Soundex (phonetic algorithm)
* Doesn't take numbers into account
* Homophones map to same key
#### `jellyfish` package
#### Can search directly when using postgres
#### Pros
* Fast computationally
#### Cons
* Limited languages/dialect
* Letters only
### Levenshtein Distance
 * Deletion
 * Insertion
 * Substitution
 * Damerai-Levenshtein distance
 * Bad for comparing addresses [have to weight numbers a bit more to compensate]
 * Longer strings
#### Pros
* Fast
#### Cons
* Need to customize
* Pairwise customization
### N-gram/Trigram
* Scoring similarity: Jaccard similarity (intersection over the union)
* Postgres has this built-in [slow for larger tables]
* Gist and git indexes in postgres for speeding up
#### Pros
* More context
#### Cons
* Slower - need to calc n-gram for each string
## Semantic Analysis
### NLTK - Wordnet
### Word2Vec (from Google in TensorFlow, train a corpus to create model then create word vectors)
### Word analogy
