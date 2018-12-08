# Correctness

- correct algos usually come with proof of correctness
  - i.e. explanation of _why_ we know the algorithm works
  - && must take every instance of the problem to desired result

_It's obvious_ never suffices and is often just **wrong**

#### First Problem: Robot Tour Optimization

- robot solders chips to the circuit-board && does this in a loop, board after board
- task is to optimize the loop in order to minimize time spent per board

Problem: Robot Tour Optimization
Input: Set _S_ of _n_ points in the plane
Output: Shortes cycle tour that visits each point in the set _S_

**Algo ideas:**

####Nearest-neighbour heuristic:

- next node = closest unvisited points
- return to _P0_ when out of points

**Positives:**

- Simple to understand and implement
- makes sense to visit nearby points before visiting faraway points to reduce total _t_
- Works perfectly for simple structures
- reasonably efficient with O(2n) runtime

**Negative:**

- **completely** wrong
  - always finds a tour
  - can be off the shortest _significantly_
  - imagine all points in a line with equal distances
    - w/o a way to break ties we might jump from left to right to left a lot, using way more time than necessary
    - in this case starting at the left (right) most point would be optimal as we only visit each point once
    - while you could make this algo work by starting on the left most point, this would stop working if you rotated the board again

#### Closest Pair:

Pseudo Code:
```
_ClosestPair(P)_
    _n_ = number of points in set _P_
    // Starting at the first point, going to the second to last point
    for i = 1 < n-1
        d = inf
    for each pair of endpoints(s,t) from distincts vertex chains
        if dist(s,t) <= d then sm = s, tm = t & d = dist(s,t)
        Connect (sm, tm) by an edge
    Connect two endpoints by an edge
```

- While less, has similar problems as closest point and can be off by >20% compared to an optimal solution for the problem (which is huge, imagine 20% more output on 1 million units)

#### A correct approach to this problem: 
```
OptimalTSP(P)
    d = inf
    For each of the n! permutations of *P*i of point set P
        if(cost(*Pi*) <= d) then d = cost(*P*i) and *P*min = *P*i
    Return *P*min
```

**Positives:**
- Garuanteed to end up with a correct solution as we are looking at *all* possible path the robot can take

**Negative:**
- extremely slow!
    - with even just 20 points we'd have to enumerate 20! orderings
    - this would equate to 2 432 902 008 176 640 000 orderings or in words: a **whole** lot
    - even todays super computers would take a long time to come up with a solution
    - for real circuit boards w/ n = 1000, we'd never reach a solution

**This is called *the traveling salesman problem* (TSP)**

**In general, there  is a fundamental difference between algorithms - wich *always* produce a correct result - and *heuristics*, which may usually do a good job but without providing any guarantee.** 

