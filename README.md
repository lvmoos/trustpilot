# Trustpilot challenge
Solution to the challenge: https://followthewhiterabbit.trustpilot.com/

The solution has 3 parts:
1. Filter out irrelevant words form the word list, in order to speed up the algorithm
2. Assign a numeric value to each word. A phrase then has the value corresponding to the sum of the word values
3. Look for combinations of words that sum up to the phrase value of the given anagram phrase: "poultry outwits ants"

## Finding anagrams
Finding the correct words that make up ana angram is based on two steps:
1. For 2 words, the word list is iterated through only once, by having a sorted list of word values. Words are paired by looking at a low and high value word sum, and then moving the iterative index correspondingly. This has a time complexity of O(n) as the list of words is only passes once.
2. For more than 2 words, the word list is iterated through word by word, and then when only two words remain, the algorithm described in 1. is called. Each word addition to the phrase will increase the time complexity with an order of n.

## Further optimization
This approach is not really feasible with more than 4 words, as eas the general time complexity of finding an anagram phrse consisting of N words from a word list of n possible words: O(n^(N-1)) for N >= 2.

Steps to increase effeciency:
1. The word list could be further reduced to not include anagram words, which will provide the same value score: ex. pins, spin, snip. This will require an expansion of words later on though, but it would be much faster.
1. In each word iteration filter out words that are no longer valid in terms of too high values.
2. In each word iteration filter out words that are no longer valid in terms of invalid character composition relative to what is missing between the current word selection and the anagram characters.
