Proximal Policy Optimization (PPO) is a reinforcement learning algorithm, and as such, it does not rely on a pre-existing "dataset" in the traditional supervised learning sense. Instead, PPO learns through interaction with an environment.
Here's how data is generated and used in PPO:
Interaction with Environment: An "agent" (powered by the PPO algorithm) interacts with a simulated or real-world environment. This interaction involves:
States: The agent observes the current state of the environment.
Actions: Based on its current policy, the agent selects an action to take in that state.
Rewards: The environment provides a reward signal, indicating the quality of the chosen action.
Next States: The environment transitions to a new state.
Trajectory Collection: This sequence of (state, action, reward, next state) forms a "trajectory" or "episode." PPO collects a batch of these trajectories by running the agent in the environment for a certain number of steps or episodes.
Experience Replay (Optional but Common): While PPO can learn directly from newly collected trajectories, some implementations might use a small, fixed-length memory buffer to store recent experiences. This allows for multiple updates on the same data, improving sample efficiency.
Batch Processing for Policy and Value Updates: The collected trajectories are then used to update the agent's policy (which dictates action choices) and value function (which estimates the value of states). This typically involves:
Advantage Estimation: Calculating the advantage of each action taken, which measures how much better an action was compared to the average expected outcome in that state.
Clipped Surrogate Objective: PPO utilizes a clipped surrogate objective function to ensure that policy updates are not too large and disruptive, maintaining stability.
Value Function Loss: The value function is updated to more accurately predict the value of states.
