## Formulating search problem

**How did we formulate the search problem?**

Local search, greedy approach is used to find new state.

**Initial State**:

Initial state we use is where all the students are in different individual team.

**Goal State**:

Code runs on infinite loop, so the last output will be the goal state.

**Successor Function**:

  This function takes the input of one set of team and returns all the possible successors of that set of team. Our successor function returns the combinations of one team
to every other single team. For example: Successor of (a,b,c) will be (a-b,c), (a-c,b), (a, b-c). This three state will be returned.

**Set of states**

Set of all possible combinations of every student.

**Cost function**:

Total time taken to grade all the teams with the given conditins is our Cost. There are 4 factors: 

1) Cost will be Total number of teams * 5 (As every team takes 5 minutes to get graded)
2) Someone got a wrong team than asked for, Cost will be increased by 3 for every cases.
3) If the team size different than requested, Cost will increase by 2 for every same cases.
4) If someone got assigned to someone they do not want to work with, Cost will increase by 10 for every same cases.

                                                                                                                         
## Working of the search algorithm
**Following is the working of the algorithm**
-Initialize the values, add initial state to the fringe.
Our first step is to perform local search and get local optimum
First step will end when the last state is reached
-First step:
  -If the Cost of the element in fringe is lower than previous team, yield.
  -Successors of the team in fringe is called, and Cost of every successor is calculated.
  -Only successor with the minimum Cost is stored in the fringe

In the second step, will take random elements and perform local search from that element.
This second step will run local search continusly with random initial state until ended manually
-Second step:
  -It will take random element from our closed list and a random successor of that element as our Initial state.
  -Same steps as the first step will be performed
 
 
 Calculation of Cost is done as below:
 For all the teams,
  -Cost will be increased by number of teams * 5
  -Cost will be increased by 3 for every condition where required teammate is not assigned
    For this, team requested and team allocated will be checked
  -Cost will be increased by 2 if length of teams will be different then requested.
    This will be checked by compering the length of both the allocated team and requested team.
 
