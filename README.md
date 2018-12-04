# Advanced Artificial Intelligence - Homework 4 #


## Problem 1: Mountain Car

Task: Implement an explicit policy for the mountain car environment without using any learning algorithm. Explain in detail your reasoning behind your policy and run several test episodes to measure its performance.

The code is in [01_mountain_car_policy.ipynb](01_mountain_car_policy.ipynb). 
The algorithm in the code: In order to let the car drive up to the flag on the top of the right mountain, we need to push the car in the same direction as its moving velocity, where we can obtain from the *observation*. We set 10 episodes for our experiment and timestamp of 200 in each episode. It's considered as a win if the car can reach the flag within 200 timestamp.

## Problem 2: Cart-pole

Task: Implement an explicit policy for the cartpole environment without using any learning algorithm. Explain in detail your reasoning behind your policy and run several test episodes to measure its performance.

The code is in [02_cart_pole_policy.ipynb](02_cart_pole_policy.ipynb). 
The algorithm in the code: Our goal is to balance the pendulum and prevent the pole from falling aside. From the OpenAI gym [Wiki](https://github.com/openai/gym/wiki/CartPole-v0), we can find out the *observation* includes [cart position, cart velocity, pole angle, pole tip velocity]. Intuitively, the cart position doesn't affect the pole falling trend. As to velocity, the pole tip velocity is more decisive than the cart velocity itself. Furthermore, the pole angle is the most important factor in deciding the pole balance. Therefore, we take the pole angle and the pole tip velocity into account for action determination. After trying different weights for the pole tip velocity, it turned out to be the best when its weight is much smaller than the weight for pole angle. Once we figure out which action to take to push the cart, we can keep the pole balanced on the string. Here, we set 10 episodes for our experiment and timestamp of 200 in each episode. It's considered as a win if the cart can stay balanced over 200 timestamp.

## Cross-entropy method to mountain car

Task: Apply the cross-entropy method to mountain car. Explain how many episodes are needed to learn a good policy. Explain which reward you use (original, modified).

The code is in [03_mountain_car_policy.ipynb](03_mountain_car_policy.ipynb). 
With the limitation of the computing power, the program was terminated after 211 iterations of training the model. The cross entropy used the original reward method and 211 episodes didn't conduct a good policy. I assume more episodes could bring up the policy performance.


## Problem 4: Algorithm Summaries

Task: List all algorithms and methods that we have covered in this course. Write 3 sentences to describe what each algorithm and method solves etc.

Please see [04_algorithms_methods_overview.ipynb](04_algorithms_methods_overview.ipynb)
