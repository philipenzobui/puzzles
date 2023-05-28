# Jane Street Capital Puzzles

Disclaimer: This document does not contain full solutions, rather than insight as to how the problem was approached. I suggest reading in parallel to the official solution or [Gareth Owen's solutions repository](https://github.com/gowen100/Jane-Street-Solutions).

### May 2023: Game Night! <br>
https://www.janestreet.com/puzzles/twenty-four-seven-four-in-one-index/

Answer: sieve <br>
Insight: Interesting puzzle with a pretty accessible difficulty (no math or programming needed). Simply map the board into binary and index to the alphabet (starting from 1 so 00001 = a). The first clue was "SCRABBLESUMODD". Taking the odd Scrabble scores of each word and mapping similarly to the first step, the second clue was "LONGERTHANFIVE". Again, map words with a length longer than fiver to get "MIDDLELETTEROF". This last clue confused me a bit (and robbed me from a top spot) as I was trying to get another step from this clue. In reality, taking the middle letter of every row resulted in a real word ("SIEVE") only for the last row.

### April 2023: Arc-edge Acreage <br>
https://www.janestreet.com/puzzles/twenty-four-seven-four-in-one-index/

Answer: 89,519,144 <br>
Insight: Key for this problem was generalizing "curves" into straight lines. Then, an area of 32 is simply 16 shapes of size 2. Thus, compute all the configurations for removing 2 squares out of the 18 that can fit in a 7x7 grid. Be careful when choosing which squares to remove make an illegal shape (e.g., shape with a hole in the middle). This computation can be done by code (implementing the shape as a matrix) or by hand. Every specific configurations needs to have an equal number of "outwards" and "inwards" curves (because "outwards" + "inwards" = 1) so the number of shapes for a specific configuration is (n choose n/2) where n is the number of outside lines. Don't forget to multiply final result by 2 to account for mirrorization of 18 squares shape.

### March 2023: Robot Long Jump <br>
https://www.janestreet.com/puzzles/twenty-four-seven-four-in-one-index/

Answer: 0.114845886 <br>
Insight: My favourite and, in my opinion, hardest JS problem that I've done so far (supported by low number of solvers). Optimal strategy was my first intuition (run until threshold and then jump). Solution to actually get the probability involved writing an equation for probability of winning given X's and Y's thresholds P(x,y). Then, using Mathematica, solved using high precision settings and solving for P(x,y) > P(x, y+epsilon) & P(x,y) > P(x, y-epsilon). In other words, find the threshhold x where X wins more than Y if y is just over or under x. 

Edit: Not sure how JS arrived at the equation in their solution, would have loved a full solution.

### February 2023: Twenty Four Seven (Four-in-One)<br>
https://www.janestreet.com/puzzles/twenty-four-seven-four-in-one-index/

Answer: 74649600 <br>
Insight: Had to learn Z3 Theroem Prover for this one, an interesting tool for problems of this nature. Took a few hours and a bit of guidance. In retrospect, knowing Z3 makes this extremly easy. Simply declare the rules and debug to get final answer.

### January 2023: Lesses More<br>
https://research.ibm.com/haifa/ponderthis/challenges/May2023.html

Answer: 8646064;3945294;1389537;0 (submitted a wrong answer by accident, so leaderboard under Bao Bui)<br>
Insight: Initially tried to solve this using genetic algorithms optimization to compute final answer. It was 
an interesting approach, but not appropriate for this problem. Real solution involved reducing search space similarly to what is seen in the official solution.

### December 2022: Die Agony<br>
https://www.janestreet.com/puzzles/die-agony-index/

Answer: 1935 (submitted a wrong answer by accident, so leaderboard under Bao Bui)<br>
Insight: Solved by hand on first try with educated trial-and-error. Simply created a dice and computed path
iteratively. I say educated trial becaused the trick was to navigate the board in the best way possible (i.e.,
it's extremly unlikely that the first move would be go right into 77 as that would grealty restraint the next
possibles moves).
