# Intro to Algorithm Design

#### What is an algorithm??

- procedure to accomplish a specific task
- the idea behind any computer program (do x, solve y)
- in order to be interesting, has to solve a general & well-specified problem

- defined by describing the complete set of instances it must work on & of it's output after running on either instance
  - distinction btw problem & instances of problem is important here

**Ex algorithmic problem definition of sorting**
Problem: Sorting
Input: sequence of _n_ keys a1, ...., 1*n*
Output: permutation (reordering) of input sequence so that

**a1 <= a2 <= ... <= a*n*-1 <= a*n***

Instances of sorting might be arr of names ['Mykeal', 'James', 'Arthur', 'Peter'] or numbers [1,2,3,4,5,6].

**The first step:** determining that we are dealing w/ a general problem

**An _algorithm_ is a procedure that takes any of the possible inputs (problem instances) and transforms it to the desired output!**

3 desirable properties for algos:

- correct
- efficient
- easy to implement

Of course, not all 3 are achievable every time. Especially 2 and 3 are difficult to combine.
Often, correct & fast enough to not slow down the application is ok in the industry
