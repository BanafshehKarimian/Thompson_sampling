# Thompson_sampling
The thompson sampling is implemented for a 10 armed bandit with rewards similar to sutton barto's figure 2.1.
* Reward class: 
    * The Reward class inherits from RewardBase class and adds mean and variance of the reward distribution along with sum of all rewards received from this distribution and the number of times we got a sample of this reward. 
    * The Update method is used for agent defined rewards which needs to update the rewards mean and variance after each sample. 
* NArmedBanditEnvironment class:
    * The NArmedBanditEnvironment class adds the achieved regrets, percent of selecting the optimal action, number of arms (arm_count), the real rewards of the environment (real_rewards) and the guest reward features of the Thompson sampling agent (TS_rewards) to the EnvironmentBase class.
    * The sample_all_rewards method samples random from each action and returns the maximum's index
    * The calculate_reward metod gets a reward from selected action's reward.
    * The update_selected_arm method updates the selected arm based on Thompson Sampling.
* Agent class:
    * The take_action method samples for all arm sample (theta), gets the action which has the max sample (At = max theta), receives the reward of doing the selected action and updates the reward features based on the achieved reward.
* The start_trials method receives the number of trials needed and calls the take_action method of the agent and calculates the regret and return percent of optimal action selection. In addition, for every trial in the plot_trial, this method plots the guessed reward distribution of the action.

## result
Plotting the rewards distribution for few trials in addition to percent of optimal action selection and regret.
<p align="center">
  <img src="https://github.com/BanafshehKarimian/Thompson_sampling/blob/master/result.png" />
</p>
