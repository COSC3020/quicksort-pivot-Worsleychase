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

With the median-of-three strategy, we assume that all three elements (first, middle, and last) are independent and randomly distributed. For three elements there are 6 total possible arrangments:

First, middle, last

Middle, last, first

Last, first, middle

First,  last, middle

Middle, first, last

Last, middle, first

This meanst that there are only two arrangments where the middle is near the actual median, meaning a good pivot choice (Last, middle, first and First, middle, last). This leads to a simple probability of $\frac{2}{6}=\frac{1}{3}$. Comparing this to a first-element pivot:

$\frac{1}{2} ? \frac{1}{3} \rightarrow \frac{1}{2} > \frac{1}{3} \therefore \text{First element method is better than median-of-three}$


# Disclaimer

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
