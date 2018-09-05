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

At each time step $$t \in \{0,1,2,...\}$$, the agent receives some representation of the environment's state, $$S_t \in \boldsymbol{S}$$, and on that basis selects an action, $$A_t \in A(s)$$, which depends on the states. The agent receives a numerical rewards, $$R_{t+1} \in R$$.

MDP sequence is like this:
$$
S_0, A_0, R_1, S_1, A_1, R_2, S_2, A_2, R_2,...
$$

The conditional probability of $$s,r$$ at time $$t$$ is like:
$$
p(s',r|s,a)
=P(S_{t}=s', R_{t}=r|S_{t-1}=s,A_{t-1}=a)
$$

State-transition probability
$$
p(s'|s,a)
=P(S_{t}=s'|S_{t-1}=s,A_{t-1}=a)
=\sum_{r \in R}p(s',r|s,a)
$$

Expected rewards for state-action pairs
$$
r(s,a)
=\mathbb{E}[R_t|S_{t-1}=s,A_{t-1}=a]
=\sum_{r \in R}r\sum_{s' \in S}p(s',r|s,a)
$$

Expected rewards for state-action-next-state triples
$$
r(s,a,s')
=\mathbb{E}[R_t|S_{t-1}=s,A_{t-1}=a,S_t=s']=
\sum_{r \in R}r\sum_{s' \in S}p(s',r|s,a)
$$


































