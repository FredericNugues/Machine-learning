# Context
The game, named "Pyrat", is a two-player-game, and consists in computing the best path for our player (a python or a rat) to do in order to eat the most possible cheeses, distributed randomly into the maze.
To do so, we can use deterministic algorithms using djikstra in order to know the actions that our player as to do in order to win the game. 
For instance, we can make our player eaten the closest cheese and repeat this until there is no more cheese on the maze (greedy algorithm).

# Use of Machine Learning
Nonetheless, it's also possible to use machine learning to predict the best route in order to win the game given only the initial condition of the round ie : the cheese distribution in the maze.

Hence, the objective was to combine supervised, unsupervised or reinforcement learning (knowing the opponent's strategy) to win the game.

# Main steps
First, we decided to train our player strategy with a reinforcement learning in order to have a better strategy compare to the greedy one but not far from him (even with a good model, sometimes the greedy opponent won the game).

Then, we generated our input data by generating a spreadsheet including all the wining-games for our player and the corresponding features of the maze (cheese distribution, cheese density, cheese localisation, ...) and also the order by which there were eaten. 
The list of orders is used as the label of our data.

The next step was to process these data by using an unsupervised model and by lonly keeping the essential features : Normalisation, Principal Component Analysis, etc...

Afterwards, we constructed a neural network with different layers, features and try to obtain a good prediction.

After many attempts, our NN trained quite well (80%) but unfortunately he couldn't generalise properly .

# Input
Excel spreadsheet whose the number of rows (10000 rows) corresponds to the number of game generated AND where our player has won.

# Output
We want our network to return the order by which cheeses have been eaten by our player.

