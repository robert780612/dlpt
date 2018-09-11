
# State-value function

## Notation 1

$$
\begin{align}
v_\pi (s) &= E \left[ G_t | S_t = s \right] \\

&= E \left[ r_{t+1} + \gamma G_{t+1} | S_t = s \right]\\

&= \sum_{a,r,s'} r\pi(a|s) p(s',r|s,a) + \gamma \sum_{a,r,s'} E \left[ G_{t+1} | S_{t+1} = s' \right] p(s',r|s,a) \pi(a|s)\\

&= \sum_a \pi(a|s) \lbrace{ \sum_{r,s'} p(s',r|s,a) \lbrack r + \gamma v_\pi(s')\rbrack \rbrace}
\end{align}
$$

## Notation 2

$$
\begin{align}
&R^a_{ss'} = E \lbrack r_{t+1} | S_t=s, S_{t+1}=s', A_t=a \rbrack \\
&P^a_{ss'} = P(S_{t+1} | S_t=s, A_t=a)
\end{align}
$$


$$
\begin{align}
v_\pi(s) &= E \left[ G_t | S_t = s \right] \\

&= E \left[ r_{t+1} + \gamma G_{t+1} | S_t = s \right] \\

&= \sum_a \pi(a|s) \sum_{r,s'}rp(s',r|s,a) + \gamma E \left[ G_{t+1} | S_t = s \right]\\

&= \sum_a \pi(a|s) \sum_{r,s'}rp(r|s',s,a)p(s'|s,a) + \gamma E \left[ G_{t+1} | S_t = s \right]\\

&= \sum_a \pi(a|s) \sum_{s'}R^a_{ss'}P^a_{ss'} + \gamma E \left[ G_{t+1} | S_t = s \right]\\



\end{align}
$$


















