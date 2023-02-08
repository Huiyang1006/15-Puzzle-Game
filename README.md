# Artificial Intelligence Game

### 15-Puzzle-Game
15 puzzle is a sliding puzzle game with numbered squares arranged in 4X4 grid with one tile missing.\
Implement different search techniques of agents, find solutions for 15-puzzle with bfs, dfs, iterative deepening depth first search, iterative deepening a-star search with Manhattan Distance heuristic.

### MDP problem for a generic grid world
Write a program to define an MDP problem for a generic grid world and use value iteration to print the values of states in each iteration.\
An example output is attached below.

### Decision Tree
Implement the decision tree learning algorithm using information gain as the importance function and prune the resulting decision tree.

### MDP Example
size : 5 4<br>
walls : 2 2 , 2 3<br>
terminal_states : 5 3 -3 , 5 4 +2 , 4 2 +1<br>
reward : -0.04<br>
transition_probabilities : 0.8 0.1 0.1 0<br>
discount_rate : 0.85<br>
epsilon : 0.001<br>

******Value iteration Algorithm******<br>
____________1th iteration____________<br>
-0.0400	-0.0400	-0.0400	+1.5920	    0<br>
-0.0400	------  -0.0400	+0.4960	    0<br>
-0.0400	------  +0.7920	    0	+0.4960<br>
-0.0400	-0.0400	-0.0400	+0.7920	-0.0400<br>
____________2th iteration____________<br>
-0.0740	-0.0740	+1.0358	+1.7695	    0<br>
-0.0740	------  +0.5373	+0.7432	    0<br>
-0.0740	------  +0.7852	    0	+0.4926<br>
-0.0740	-0.0740	+0.5625	+0.7852	+0.5373<br>
......<br>
____________16th iteration____________<br>
+0.8458	+1.1163	+1.4214	+1.8332	    0<br>
+0.6447	------  +1.1060	+1.0046	    0<br>
+0.4799	------  +0.9480	    0	+0.5815<br>
+0.4087	+0.5489	+0.7288	+0.9125	+0.6884<br>
____________17th iteration____________<br>
+0.8458	+1.1163	+1.4214	+1.8332	    0<br>
+0.6447	------  +1.1060	+1.0046	    0<br>
+0.4800	------  +0.9480	    0	+0.5816<br>
+0.4088	+0.5489	+0.7288	+0.9125	+0.6884<br>
_____________Final Policy_____________<br>
E  E  E  E  T  
N  -  N  N  T  
N  -  E  T  S  
E  E  N  N  W  

******Policy iteration Algorithm******<br>
Policy<br>
N  W  N  N  T  
N  -  W  E  T  
W  -  N  T  S  
N  N  N  W  W  
Policy Number<br>
2  0  2  2  0  
2  0  0  1  0  
0  0  2  0  3  
2  2  2  0  0  
......<br>
Policy<br>
N  W  N  N  T  
N  -  W  E  T  
W  -  N  T  S  
N  N  N  W  W  
Policy Number<br>
1  1  1  1  0  
2  0  2  2  0  
2  0  1  0  3  
1  1  2  2  0  
Final Policiy<br>
E  E  E  E  T  
N  -  N  N  T  
N  -  E  T  S  
E  E  N  N  W  

### Decision Tree Example<br>
------------Decision Tree Implementation Starts------------<br>
|Reservation: 0.02|Type: 0.00|Price: 0.20|Alternate: 0.00|Hungry: 0.20|Bar: 0.00|Patrons: 0.54|WaitEstimate: 0.21|Raining: 0.00|FriorSat: 0.02<br>
->Attribute with highest IMPORTANCE: Patrons<br>
|Reservation: 0.25|Type: 0.25|Price: 0.25|Alternate: 0.11|Hungry: 0.25|Bar: 0.00|WaitEstimate: 0.25|Raining: 0.11|FriorSat: 0.11<br>
->Attribute with highest IMPORTANCE: WaitEstimate<br>
|Reservation: 0.00|Type: 1.00|Price: 0.00|Alternate: 0.00|Hungry: 0.00|Bar: 1.00|Raining: 0.00|FriorSat: 1.00<br>
->Attribute with highest IMPORTANCE: Bar<br>
|Reservation: 1.00|Type: 1.00|Price: 1.00|Alternate: 0.00|Hungry: 0.00|Bar: 1.00|Raining: 0.00|FriorSat: 0.00<br>
->Attribute with highest IMPORTANCE: Reservation<br>
------------Decision Tree Implementation Ends------------<br>

------------Print the Resulting Decision Tree------------<br>
Patrons-><br>
--|Some: Yes<br>
--|None: No<br>
--|Full: WaitEstimate<br>
--WaitEstimate-><br>
----|10-30: Reservation<br>
----Reservation-><br>
------|No: Yes<br>
------|Yes: No<br>
----|>60: No<br>
----|0-10: No<br>
----|30-60: Bar<br>
----Bar-><br>
------|No: No<br>
------|Yes: Yes<br>
