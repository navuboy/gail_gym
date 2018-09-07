# gail_tf4gym
TensorFlow implementation of Generatve Adversarial Imitation Learning (GAIL) and Behavioural Cloning (BC) for classic CartPole-v0 environment from OpenAI Gym. 

## Dependencies
- python: 3.5.2
- mujoco-py: 0.5.7
- tensorflow: 1.1.0 (with GPU)
- gym: 0.9.3

## Gym environment 
CartPole-v0  State: Continuous ; Action: Discrete 

## Implementation of GAIL:

### Step: 1 Generate expert trajectory data  
Reinforcement Learning algorithm: PPO, is used for generating the expert trajectory data for the CartPole-v0 environment.  

python3 run_ppo.py
<p align= "center">
  <img src="walker_controller/src/training_1.gif/">
</p>

### Step: 2 Sample the expert trajectory data from the PPO generated trajectories. 

python3 sample_trajectory.py

### Step: 3.1 Execute GAIL.  

python3 run_gail.py  

### Step: 3.2 Run Behavioral Cloning  

python3 run_behavior_clone.py 

### Step: 4 Test trained policy 

python3 test_policy.py  

Default policy is trained with gail  

***--alg=bc*** or ***--alg=ppo*** allows you to change test policy  

If you want to test bc policy, specify the _number_ of model.ckpt-_number_ in the directory trained_models/bc  
For example to test behavioral cloning:  
python3 test_policy.py --alg=bc --model=1000
