# Report 
## Author Mateusz Zatylny
## About Deep Q-Learning
In this project we use Deep Q-Learning, here the original paper [paper](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf)

In deep Q-learning, we use a neural network to approximate the Q-value function. The state is given as the input and the Q-value of all possible actions is generated as the output. The comparison between Q-learning & deep Q-learning is wonderfully illustrated below:
<img src="https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2019/04/Screenshot-2019-04-16-at-5.46.01-PM.png" alt="Deep Q-Learning" width="600" height="400">

So, what are the steps involved in reinforcement learning using deep Q-learning networks (DQNs)?

 - 1) All the past experience is stored by the user in memory
 - 2) The next action is determined by the maximum output of the Q-network
 - 3) The loss function here is mean squared error of the predicted Q-value and the target Q-value – Q*. This is basically a     regression problem. However, we do not know the target or actual value here as we are dealing with a reinforcement learning problem. Going back to the Q-value update equation derived fromthe Bellman equation. we have:
 <img src="https://i1.wp.com/s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2019/04/Screenshot-2019-04-16-at-6.02.08-PM.png?resize=447%2C46&ssl=1" alt="Bellman equation">
### The Q-Network is shown below

    Q-Network(
      (Fully connected layer1): Linear(in_features=37, out_features=128, bias=True)
      (Fully connected layer2): Linear(in_features=128, out_features=64, bias=True)
      (Fully connected layer3): Linear(in_features=64, out_features=4, bias=True)
    ) 
### hyper-parameter

    BUFFER_SIZE = int(1e5)  # replay buffer size
    BATCH_SIZE = 64  # minibatch size
    GAMMA = 0.99  # discount factor
    TAU = 1e-3  # for soft update of target parameters
    LR = 5e-4  # learning rate
    UPDATE_EVERY = 4  # how often to update the network
    
  ### performance
  
This implementation "solved" the environment (gaining a score of >15 averaged over 100 consecutive episodes) after 679 episodes. The console output and a plot of the scores are displayed below.

![c](https://lh3.googleusercontent.com/vC8FO4nkIc8CtJm5fso5txzNA-Fy0Hl8G8r9b8AzwfZ8N7xxsKjlqoWBarGvcqlDnEmfAv8tPAn5 "Plot")
###
### Future Improvements

- Double DQN
- Dueling DQN
- PER 
