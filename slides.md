## Genetic Algorithms: A Concrete Example Using Checkers
Explaining the basics with checkers

---

## What Is A Genetic Algorithm?
* **Given** A list of candidate solutions
* **Apply** Natural Selection
* **Output** A better candidate solution

note:
Use natural selection to "breed" a better solution to the problem

---

## Components Of A Genetic Algorithm
1. `Fitness Function` to determine how it performed
2. `Chromosomes` define the particular behavior of the candidate

note:
* (1) is really easy - compare the win/loss/tie rate against itself and other solutions
* (2) is the tricky part

--

## Chromosomes
Describe the strategy of the particular candidate player. Provide "weights" to prioritize certain board states or piece movements

Examples:
* Piece Count
* Piece Position
* Board Control

note:
* Chromosomes will describe the values used in evaluating board state
* Based upon high-level players strategies

---

## How To Change/Evolve Iterations?
* **Mutation**
* **Crossover**
* **Selection**

note:
Based on natural selection/evolution. "Evolves" a solution over time/iterations
* Mutation - Tweak traits from previous iteration for new iteration to see if they perform better/worse
* Crossover - Combine traits from two solutions into a new iteration/candidate
* Selection - Filtering the current list of iterations to only the "best" ones

---

## Basic Checkers Algorithm
1. Makes all valid moves from current state
2. For each move, analyze the resulting state with the given chromosomes/weights
3. Select the "best" move given the results from 2

note:
* Assume we have a general algorithm that is capable of making only valid moves in checkers and interacting with whatever server/code handles the game.
* For simplicity ignore move databases, built-in openings/closings, looking more than one move ahead, etc

---

## Put It All Together
1. Create a random pool of candidates
2. Have them play against each other and themselves
3. After `n` iterations, determine the "best" candidates examining win/loss/tie scores
4. Select, Mutate, Crossover
5. `goto` 2

note:
* (1) can be pre-loaded with particular candidates if there is a known "good" starting point to save time

---

## End Results
You have a solution or solutions that have performed better than past candidates

--

## Advantages
* Always have a solution
* Distribute the work

note:
Very easy to parallelize problem

--

## Disadvantages
* There is no stop/end point
* Can get stuck in local optimal solution, rather than find the overall optimal solution

note:
* You need to pick an arbitrary end point - minimum performance met, time/money constraint
