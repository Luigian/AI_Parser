# Project 6a: Parser

## Highlights

* Write an AI to parse sentences, print their syntax tree and extract noun phrases

* A common task in natural language processing is parsing, the process of determining the structure of a sentence. 

* Knowing the structure of a sentence can help a computer to extract information out of it, like the noun phrases, which is useful to get an understanding for what the sentence is about.

* The context-free grammar formalism allow us to parse English sentences via a technique called Rewriting Rules: to replace one symbol with other symbol or symbols.

## Non-terminal symbols Table

By defining a set of rules, I was able to run the CYK algorithm using the 'parse' method from the nltk library. This algorithm takes a sentence (terminal symbols) and figure out the syntax tree (the structure of the non-terminal symbols).

This algorithm can also detect non-well formed sentences according to the grammar rules, but it can´t detect non-sense sentences.

The more rules are implemented, the more complex sentences it can parse.

Since there is ambiguity in language, the same sentences can have more than one syntax structure.

## Implementation

### Preprocessor 

The preprocess function accept a string as input and return a lowercased list of its words. It use the following methods: 
* nltk’s word_tokenize - to perform tokenization (split the string into words).
* lower - to convert all characters to lowercase.
* isalpha - to remove any word that does not contain at least one alphabetic character.

### The NONTERMINALS global variable

A set of context-free grammar rules that, when combined with the rules in TERMINALS, allow the parsing of all sentences in the sentences/ directory.

It’s to be expected that the parser may generate some sentences that may not be syntactically or semantically well-formed. Also it’s to be expected that the parser may generate multiple ways to parse a sentence, since english grammar is inherently ambiguous.

Constraints: 
* Avoid over-generation of sentences, sentences like "Armchair on the sat Holmes." are meant to not be accepted by the parser.
* Avoid  under-generation of sentences. A very long and specific rule like (S -> N V Det Adj Adj Adj N P Det N P Det N) that would technically successfully generate sentence 10, but not in a way that is particularly useful or generalizable.
* To try to be as general as possible without over-generating. The parser should accept the sentence “Holmes sat in the armchair.” (and “Holmes sat in the red armchair.” and “Holmes sat in the little red armchair.”), but not the sentence “Holmes sat in the the armchair.”


### np_chunk

 




