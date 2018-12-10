# Selecting the Right Jobs

#### The non-overlapping movie scheduling problem

Problem: Highy-in-demand actor has been presented with offers to n different movies
Only able to take one job at a time & we want to make max money doing it.
As all of them offer the same amount \$, we seek the largest possible set of jobs (intervals) such that no two conflict w/ each other
Input: a set _I_ of n intervals on the line
Output: Largest subset of mutually non-overlapping intervals selected from _I_

**Approaches:**

- EarliestJobFirst:
  - Accept earliest starting job (j from _I_) w/ does not overlap
- ShortestJobFirst:
  - Accept shortest starting job (j from _I_) which does not overlap
- ExhaustiveScheduling:
  - enumerate all possible subsets of intervals in _I_, determine the best

**ALL** of the above are seriously flawed. 1 & 2 are incorrect and 3 - while correct - is extremely slow for input > 20

**Actual algorithm:**

```
OptimalScheduling(I):
    While (*I* != 0):
        Accept job j from I w/ earliest completion date
        Delete j and any interval which intersects j from I
```

**Take Home Lesson:**
_Reasonable-looking algorithms can easily be incorrect!_
_Algorithm correctness is a property that must be carefull demonstrated!_
