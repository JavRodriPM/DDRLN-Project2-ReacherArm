[//]: # (Image References)

[image1]: https://raw.githubusercontent.com/JavRodriPM/DDRLN-Project2-ReacherArm/master/Videos/Continuous_Control_Trained_Agent_FS.gif "Trained Agent"


# Project 2: Continuous Control

### Introduction

The purpose of this project is to train a double-jointed robotic arm to move to a target location (Marked with a green ball). A reward of +0.1 is provided for each step that the robotic arm hand (“The agent” onwards) is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

For this project, we will work with the Unity Reacher environment.

![Trained Agent][image1]

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the robotic arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Introduction

The algorithm is an implementation of the DDPG (Deep deterministic policy gradient) algorithm with soft updates. This algorithm is an Actor-critic method, these methods main characteristics are: 
-	The reduction the high-variance commonly associated to policy-based agent,
-	It learns faster than policy-based methods and 
-	have more consistent convergence than value-based agents

For this agent to be an Actor-critic, we have two learning neural networks: 
-	In a standard Actor-critic method, the Actor network will learn the probabilities of good and bad actions. Will take in states and outputs a distribution over the possible actions. But in the case of DDPG, the algorithm used in this project, the Actor will give us the best possible action based on the policy learnt, not a probability distribution.
-	The Critic network will learn how to estimate good actions and bad actions to help on the actor decisions. Technically it will learn to evaluate the state value function (Vpi), will take in states and outputs an expectation of the state value function of the policy, this state value function will update the actor network.

### Set up your environment

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_One agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `DDRLN-Project2-ReacherArm/` folder,  unzip (or decompress) the file and change the path in the `Continuous_Control.ipynb` file in the following line: `env = UnityEnvironment(file_name='.\Reacher_Windows_x86_64\Reacher.exe')`

3. Install the requirement defined in the requirements.txt via `pip` 

```
pip install -r requirements.txt

```
or follow the course instructions at: (https://github.com/udacity/deep-reinforcement-learning#dependencies).
.

### Code instructions

Follow the instructions in `Continuous_Control.ipynb` to get started with training your own agent or just seeing the already trained agent!  
