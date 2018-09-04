---
description: 'http://incompleteideas.net/book/bookdraft2017nov5.pdf'
---

# Reinforcement learning

## Markov decision process

![](/.gitbook/assets/agent.png)
*The agent-environment interaction in a Markov Decision Process.*

* Agent: decision maker
* Action: agent's decision which impacts the environment
* State: the environment situation
* Reward: a special numerical values that the agent seeks to maximize
* Environment: comprising everything outside the agent

At each time step $$t \in \{0,1,2,...\}$$, the agent receives some representation of the environment's state, $$S_t \in S$$, and on that basis selects an action, $$A_t \in A(s)$$[^1]

[1]: action set depends on the states.

