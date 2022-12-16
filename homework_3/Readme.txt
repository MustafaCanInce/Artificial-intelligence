Q1) evaluationFunction:
The goal of the agent to maximize this score by collecting as much food as possible and minimizing the distance to the nearest piece of food. The value 1.0 is divided by the minimum food distance to create a score that increases as the minimum food distance decreases. 
min distance is calculated using the manhattanDistance function, which appears to calculate the Manhattan distance between two points. Manhattan distance is between two points measured along the axes at right angles, and is calculated as the sum of the horizontal and vertical distances between the points.
function returning a score for the given game state that is based on the current score of the game and the proximity of the agent to the nearest piece of food. 

Q2) MinimaxAgent function:
The value function  It takes in the current state, the index of the agent , the remaining depth of the search,
and the alpha-beta pruning bounds a and b. If the game has ended , it returns the evaluation score for the current game state using the evaluationFunction.
Otherwise, it calls either max_value or min_value recursively with the updated game state, agent index, and depth.

Q3) AlphaBetaAgent:
The value function takes in a game state gameState, the index of the current agent agentIndex, the current depth depth, and the alpha-beta pruning values a and b. It returns the minimax value of the given game state.
max_value and min_value functions both perform a depth-first search through the game tree to find the optimal value. They also use alpha-beta pruning to efficiently eliminate branches of the tree that cannot affect the final result.
min_value function returns the minimum value among all the legal actions for the current agent. It does this by iterating through all the legal actions, generating the successor game state for each action, and finding the maximum value of the successor game state . 
getAction function calls the value function to get the minimax value of the current game state, and returns the action that corresponds to the maximum value.

Q4) ExpectimaxAgent:
The expectimax algorithm is  makes their moves randomly, rather than choosing the action that maximizes their score. In this case, the expectimax algorithm estimates the expected value of each action, rather than the maximum value as in the minimax algorithm.
The expectimax algorithm works by recursively evaluating the game tree, starting from the current game state. The value() function is a recursive function that takes as input the current game state, the index of the current agent, and the current depth of the search.

Q5) betterEvaluationFunction:
The function starts by initializing the value to be returned to 0.0. It then checks if the current game state represents a win or a loss, and sets the value to positive or negative infinity accordingly. If the game is not won or lost, the function adds 5 times the current score of the game to the value.
function looks at the distances to ghosts and edible ghosts. If there is at least one non-edible ghost in the game, the function adds a negative value to the score based on the distance to the nearest ghost. This value is inversely proportional to the distance, meaning that the score decreases as the distance to the ghost increases. 
If there is at least one edible ghost in the game, the function adds a positive value to the score based on the distance to the nearest edible ghost. The value is also multiplied by a term that decreases with the number of ghosts present in the game, which means that the effect of the distance to the edible ghost on the score is less significant when there are more ghosts.
Finally, the function returns the value as the score of the current game state. 