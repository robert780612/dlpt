---
description: 'http://incompleteideas.net/book/bookdraft2017nov5.pdf'
---

# Reinforcement learning

## Markov decision process

![](/.gitbook/assets/agent.png)  
_The agent-environment interaction in a Markov Decision Process._

* Agent: decision maker
* Action: agent's decision which impacts the environment \($$A_t$$\)
* State: the observation of the environment \($$S_t$$\)
* Reward: a special numerical values \($$R_t$$\)
* Environment: comprising everything outside the agent

At each time step $$t \in \{0,1,2,...\}$$, the agent receives some representation of the environment's state, $$S_t \in \boldsymbol{S}$$, and on that basis selects an action, $$A_t \in A(s)$$, which depends on the states. The agent receives a numerical rewards, $$R_{t+1} \in R$$.

The history is the sequence of states, actions, rewards:


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
=\mathbb{E}[R_t|S_{t-1}=s,A_{t-1}=a,S_t=s']
=\sum_{r \in R}r \dfrac{p(s',r|s,a)}{p(s'|s,a)}
$$


---

* Return: the total reward an agent can get. \($$G_t$$\)
* Policy: a probability distribution of actions under some states. \($$\pi(a|s)$$\)
* Value: the expected return of a state under a policy. \($$v_\pi(s)$$\)

Return or discounted return


$$
G_t = \sum_{k=0}^{\infty}\gamma^k R_{t+k+1}, \qquad 0\le\gamma\le 1
$$


The state-value function for policy $$\pi$$


$$
v_\pi(s)=\mathbb{E}_\pi \left[ G_t | S_{t}=s \right]
$$


The action-value function for policy $$\pi$$


$$
q_\pi(s,a)=\mathbb{E}_\pi \left[ G_t | S_{t}=s , A_{t}=a \right]
$$


The Bellman equation for $$v_\pi(s)$$


$$
v_\pi(s)=\sum_a \pi(a|s) \sum_{r,s'}p(r,s'|s,a) \left[ r + \gamma v_\pi(s') \right]
$$


The Bellman equation for $$q_\pi(s,a)$$


$$
q_\pi(s,a) = \sum_{r,s'} p(r,s'|s,a) 
\left[ r + \gamma \sum_{a'} \left[ \pi(a'|s')q_\pi(s',a') \right] \right]
$$


---

Optimal state-value function

$$
v_*(s) = \max_\pi v_\pi(s)
$$

---

## Prediction & Control
* Prediction: estimating the value function for a given policy $$\pi$$
* Control: finding the optimal policy

---

---

---

---

---



