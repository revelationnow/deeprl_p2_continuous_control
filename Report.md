[//]: # (Image References)

[image1]: average_score.png "Score history"

# Project 2: Continuous Control

## Implementation
The implementation for this project started from the recommendations from the benchmark implementation. The Replay buffer was updated with information from all 20 agents and the update periodicity was reduced to ten updates every 5 time steps.
In addition to this, the gradient clipping aspect was added to the update equation.
The model used for the project was modified from the one used in the classroom examples. The actor was given 3 hidden layers, with all layers being fully connected layers, each having 256 nodes. The same architecture was  used for the critic, with the only difference being that the critic has 256 + action size as the size of second hidden layer, to allow the actions to be provided in the forward step.
With this architecture, it took the agents 193 episodes to reach the required score. The history of the scores is shown in the following image:

![Score history][image1]

## Future Work
The research paper mentioned in the project benchmark introduces several interesting algorithms that might be used to improve this implementation. Particularly, TNPG and TRPO seem to get significantly higher average return than other algorithms studied, when looked at across tasks. This seems to indicate, as the authors state, that constraining the variation to the policy distribution can help ensure stable learning.
Between TRPO and TNPG, the main advantage of TRPO appears to be that it allow slightly faster learning by being able to robustly enforce constraints with larger delta_KL values.
