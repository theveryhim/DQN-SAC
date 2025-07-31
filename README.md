# Deep Q-Network --- Soft Actor Critic

## DQN

### Develop the model of nueral network for training agent.
In this section, We’ll embark on implementing a Deep Q-Network (DQN) agent from scratch, one of the fundamental algorithms in deep reinforcement learning. DQN revolutionized the field by successfully combining deep neural networks with Q-learning, enabling agents to learn directly from high-dimensional sensory inputs. We’ll build each component systematically - starting with the neural network architecture that approximates Q-values, then implementing the experience replay buffer that breaks correlations in training data, followed by the epsilon-greedy policy for balancing exploration and exploitation, and finally bringing it all together in the DQN agent class. This hands-on implementation will deepen our understanding of how value-based reinforcement learning algorithms work under the hood.
Below is the schema for DQN implementation
<center><img width="70%" src="figures\3.png"></center>
The CartPole-v1 environment serves as our testing ground - a classic control problem where an agent must balance a pole on a moving cart. Through this implementation, we’ll gain practical experience with key concepts like target networks for stable learning, batch sampling from replay memory, and the temporal difference learning update rule. Pay special attention to how each component interacts with others: how the neural network processes states to output Q-values, how the replay buffer stores and samples experiences, and how the epsilon-greedy policy uses these Q-values to select actions. The visualization at the end will show our agent’s learning progress across multiple random seeds, demonstrating the effectiveness of our implementation. The conceptual questions following the implementation will help solidify our understanding of where DQN fits in the broader landscape of reinforcement learning algorithms.

### Implement Models
- Develop the replay buffer for adding experiences in buffers.
- Policy module for selecting best action in given states. (Note: we can add the update_epsilone function to update the epsilone for each iteration)
- Develop Agent for DQN alghorithm. This module is reponsbile for training, testing, fill the buffer and optimize the learning.
<center><img width="70%" src="figures\1.png"></center>

## SAC
This section challenges we to implement the Soft Actor-Critic (SAC) algorithm, representing a significant shift from the value-based approach of DQN to a state-of-the-art actor-critic method. SAC belongs to the family of maximum entropy reinforcement learning algorithms, which explicitly balance reward maximization with maintaining stochastic policies for better exploration. Unlike DQN’s discrete action selection, SAC can naturally handle continuous action spaces while incorporating entropy regularization to encourage exploration and prevent premature convergence to suboptimal policies. we’ll need to architect multiple neural networks - an actor network that outputs actions, critic networks that evaluate state-action pairs, and potentially a value network depending on wer implementation choice.

Implementing SAC requires understanding several advanced concepts including the reparameterization trick for gradient computation through stochastic nodes, soft value functions that incorporate entropy bonuses, and the careful orchestration of multiple function approximators. The algorithm’s elegance lies in its ability to automatically tune the temperature parameter that balances exploration and exploitation. As we build wer implementation, consider how SAC differs fundamentally from DQN in its approach to the exploration-exploitation trade-off and its ability to maintain a stochastic policy throughout training. The comparison questions at the end will help we articulate these differences and understand when each algorithm might be preferred. wer implementation will again be tested on CartPole-v1, allowing direct comparison with wer DQN results and highlighting the distinct characteristics of policy-based versus value-based methods.
<center><img width="70%" src="figures\2.png"></center>
