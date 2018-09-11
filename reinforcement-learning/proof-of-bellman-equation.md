$$
\begin{align}
E \left[ G_t | S_t = s \right] &= E \left[ r_{t+1} + \gamma G_{t+1} | S_t = s \right]\\

&= \sum_{a,r,s'} r\pi(a|s) p(s',r|s,a) + \gamma \sum_{a,r,s'} E \left[ G_{t+1} | S_{t+1} = s' \right] p(s',r|s,a) \pi(a|s)\\

&= \sum_a \pi(a|s) \lbrace{ \sum_{r,s'} p(s',r|s,a) \lbrack r + \gamma \rbrack \rbrace}
\end{align}
$$