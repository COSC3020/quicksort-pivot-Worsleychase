# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

# Solution

As seen on the slides, the probability of choosing a good (first-element) pivot is 1/2 or 50%.

With the median-of-three strategy, we assume that all three elements (first, middle, and last) are independent and randomly distributed. Following similar logic to the first-element method, we want a pivot that lie within the middle half of the array. This means that our elements need to have a median that lies within this range, there are 8 total permutations possible:

1 All poor - All elements lead to a poor median outside the middle half. (PPP)

3 Some poor - Two elements (in any order) lead to poor median, but one element leads to a good median. This means there is a $\frac{1}{2}$ probability, or 50% chance the median is good. (PPG, PGP, GPP)

3 Most good - Two elements (in any order) lead to a good median, but one element leads to a bad median. The two good medians mean there is a $\frac{3}{3}$ probability, or 100% chance of a good median. (GGP, GPG, PGG)

1 All good - All elements lead to a good meadian. (GGG)

We now use these to find the probability of a good median:

$$ P_{good} = \frac{(\text{1 All poor} * \text{Probability of Good Median}) + (\text{3 Some poor} * \text{Probability of Good Median}) + (\text{3 Most good} * \text{Probability of Good Median}) + (\text{1 All good} * \text{Probability of Good Median})}{\text{Num of Permutations}}$$

$$ P_{good} = \frac{(1 \cdot 0)+(3 \cdot \frac{1}{2})+(3 \cdot \frac{3}{3})+(1 \cdot 1)}{8} = \frac{0+1.5+3+1}{8}=\frac{5.5}{8} = 0.6875$$

This means that there is a 68.75% chance that the median method finds a good pivot, which is a higher chance than the first-element method. Therefore, median-of-three is a better pivot choice method.

# Disclaimer

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
