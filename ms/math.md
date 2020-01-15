
## Thoughts

I've been looking at the document, and made some suggestions. But I wanted to share some broader ideas with you at this point.

The more I look at this, the more that I feel the math could be much simpler. All of the interesting math can be driven through the basic ideas from S4. Most of what's currently in S2 and S3 belongs in our notebooks (making sure we're right, not in the paper).

A way to make this briefer version interesting, and possibly easier to follow, could be to have two different diagrams. One is the biological diagram, similar to what we already have. The biological diagram has $p_d$, $p_\ell$, $p_e$, $p_v$.  (I'm suggesting $p_v$ to replace $p_o$ as standing for ovulation, just because o looks like zero.) The other would be a computational (or censusing) diagram, based on what we actually measure (in our model world). We would replace the larvae, pupae and eclosee with one box showing where we measure (we somehow make it clear that the position of this box can vary). $p_d$, $p_e$ and $p_v$ would thus be replaced by $p_c$ and $p_m$ (probability from loop completion to producing something that is censused, and probability from being censused to becoming “mature” (entering the loop)).

In my mind, there is also a math (or dynamical) diagram, but I think this diagram can be incorporated into the computational diagram. We just show an arrow that skips the census box and has $p_r = p_c p_m$.

I feel it would be helpful to do the main geometric sum when we introduced the generating function. Almost everything follows from that. I'm not sure why we need specific citations for our solutions for the two basic equations, since they seem pretty straightforward.

Another idea that might help the exposition would be the talk a bit more about odds. For me, $\cal R$ is just equal to $p_r \sigma_\ell$, where $p_r$ is the probability of recruitment (above) and $\sigma_\ell$ is the _odds_ of completing the loop. I think we can come up with a nice explanation of why the odds come in there. I also think we can simplify conceptually by talking about $p_b$ and $\sigma_b$ as the probability and odds of giving birth before dying from the loop.

[I'm also struggling with notation for odds. I would love to use a script
small o, but don't know how to do that. For now, I'm using σ because it looks a little like that.]

It will also be interesting to discuss how best to parameterize the biological model.  This can be done largely in parallel with the computational model. The big question in my mind is at what point do we think we know the sex of a fly? In other words, what kind of counting and sexing are people actually doing in the field?

## Math 

Since I've been doing math to try to get things straight, I thought I should outline the skeleton here. I'm sure it's mostly or entirely consistent with what you're doing, but I would like to boil it down to the simplest components (and to rely more on odds, if you agree).

An invidual at the census point: 

* reaches the loop with probability $p_m$
* goes around the loop producing offspring that will be counted or else dying
	* the probability of producing before dying $p_b$ has _odds_ of $\sigma_b = \frac{p_b}{1-p_b} = \frac{p_\ell p_c}{1-p_\ell} = \sigma_\ell p_c$

The total number of censused individuals produced by a censused individual is:

* 0, if it doesn't reach the loop (probability $1-p_m$)
* $k$, which could also be 0, if it reaches the loop and then fails after $k$ successes, with probability $p_m p_b^k (1-p_b)$

The generating function is:

$$G(s) = 1-p_m + p_m (1-p_b) \sum_k p_b^k s^k = 1-p_m 
	+ \frac{p_m (1-p_b)}{1-p_b s} $$

We get $\cal R$ by calculating $G'(1)$:

* $G'(s) = \frac{p_m p_b (1-p_b)}{(1-p_b s)^2}$ 
* $\cal R = G'(1) = \frac{p_m p_b}{(1-p_b)}  = p_m \sigma_b = p_m p_c \sigma_\ell = p_r \sigma_\ell$

Note that $p_c$ and $p_m$ disappear here, as they have to for the framework to make sense.

I really like how simple this comes out (and how we can calculate it without ever calculating $p_b$!).

We get the extinction probability $y$ by solving $G(y) = y$. The slick way to do this is by saying $G(1-z) = 1-z$, where $z$ is the non-extinction probability, and then factoring out a $z$. This gives:

$$ z = p_m(1-1/\cal R).$$

So we see that everything is very slick and sensible. The only messiness we can't get rid of comes from calculating $z$ from $y$. We should connect to how people are really counting in tsetse populations, and note that a real population has individuals at different life stages.
