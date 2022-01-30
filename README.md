# Trustpilot challenge
Solution to the challenge: https://followthewhiterabbit.trustpilot.com/

The solution has 3 parts:
1. Filter out irrelevant words form the word list, in order to speed up the algorithm
2. Assign a numeric value to each word. A phrase then has the value corresponding to the sum of the word values
3. Look for combinations of words that sum up to the phrase value of the given anagram phrase: "poultry outwits ants"

## Finding anagrams
Finding the correct words that make up ana angram is based on two steps:
1. For 2 words, the word list is iterated through only once, by having a sorted list of word values. Words are paired by looking at a low and high value word sum, and then moving the iterative index correspondingly
2. For more than 2 words, the word list is iterated through word by word, and then when only two words remain, the algorithm described in 1. is called

## Further optimization
This approach is not really feasible with more than 4 words, as each additional word increases the time complexity by a factor of n.
Steps to increase effeciency:
1. in each word iteration one could filter out words that are no longer valid in terms of too high values
2. in each word iteration one could filter out words that are no longer valid in terms of invalid character composition in terms of what is missing between the current word selection and the anagram character set
