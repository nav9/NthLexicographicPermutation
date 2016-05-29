# NthLexicographicPermutation

I created this algorithm at around August 2008.
Also posted on my blog: http://nrecursions.blogspot.in/2014/02/nth-permutation-without-swapping.html

You'd get many programs for finding the N'th lexicographic (alphabetical order) permutation of a string. They're done with recursion and swapping.
I present you a completely unique algorithm which I've devised myself. It makes use of no recursion or swapping. Besides, the algorithm is WAY shorter than the others.

Consider you have a string with 'e' elements. You're asked to find the N'th lexicographic permutation.
The sequence for three elements would be:
abc, acb, bac, bca, cab, cba

But my algorithm won't even have to generate this list. It directly reaches the Nth permutation. How? Read on...


The Algorithm
---
 
1. e=number of elements in string. [Store them in an array as 'abc', where a is in the zero'th position of the array]
2. n=n'th permutation of the string.
3. division=(e!)/e [This divides the list into equal sections](where e! is 'e factorial'. If e=3, e!=3*2*1)
4. Calculate pos=ceil(n/division) to find where the n'th string would be in the list.
5. Find the pos-1 element in the array.
6. Concatenate the element found from step 5, in the final output string.
7. e=e-1 [decrease the number of elements]
8. Remove the pos-1 element from the array and reinitialize the array with only the leftover characters.
9. oldDivision=division [store temporarily]
10. n=n-(oldDivision*(pos-1))
11. Goto step 3 if you haven't iterated 'length of the original string' times.
12. Print the output string.
