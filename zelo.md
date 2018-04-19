# (Alpha) Zero to Elo

- Add mosc logo

## Outline
* The math behind Go
* From Crazy Stone -> AlphaGO
* AlphaGo vs AlphaZero
* AlphaZero as Policy improvement
* Code and demo

## Game of Go

- add image game of go

Note:
- Each player put a stone on the goban (19 x 19), black first
- A stone can be captured if sorrounded from two stones
- The winner is the one who conquer the larger region


- add game of go in numbers

Note:
- state_space complexity 10^170 (estimated numer of possible board config)
- search complexity in time 10^360 (the number of games that can be played for each starting state)
- branch ~ 250 av of legal moves
- depth ~ 150 av. lenght of the game




## From CrazyStone to AlphaGo

- add image of prediction that a computer will beat a human in go

Note;
- Go is constructive instaed of destructive
- Go is hard because is difficult to build an evaluation function of each board position
thus alpha-beta search doesn't work.
- Even humans describe as intuition
- MCTS with deep neural network works very well because of the averaging of the errors, while alpha_beta search propagates the largest approximation error up in the tree.

## AlphaGo Zero vs AlphaZero

- Exploit simmetries in board position as rotation and reflection
- Value function optimize the expected outcome and not the probability of winning
- No update threshold update
- Exploration Noise from a dirchlet.

Note:
for which if alpha -> 0 the area under the curve becomes conconcetrade, while alpha -> it flattens out, ensuring a larger exploration. Is like a multivariate of the beta (in go we have the smallest noise, while in chess the largest) 
The reason for this could actually be the fact that the local shift of board position is small in go, and could be very large in chess.


- add image AlphaGoZero vs AlphaZero and AlphaZero vs Stockfish
- add table computational resources

## AlphaZero as Policy Iteration 

### Reinforcement Learning
  - add image
  - add equation of the objective

### Value functions
  - add equation
  - add image of a simple gridworld...

### Policy Iteration
  - add image

### Policy Improvement
  - add equation
  
#### Bandits
  - Setting
  - Regret minimization
  - UCB1
  - PUCB (Context UCB)

#### MCTS
  - Selection
  - Expansion and Evaluate (notice that while usually we have a random policy that continues the rollout, here we have a neural network which taka transformation of the state and output a value of the leaf node) (why this actually make any fucking sense?)
  - Backup

### Policy Evaluation
  - self-play

### Training
  - Deep Learning
  - Loss function
    - value function estimation and cross entropy maximizaiton between the MCTS policy and the actual policy, note this loss has 3 functions:
      - stabilize improvement
      - keep samples on-policy
      - monotically improve policy following the action selection from the MCTS
        - which we already showed offer a better policy
      - the learning signal is in the value tho!

### Architecture
### Demo
