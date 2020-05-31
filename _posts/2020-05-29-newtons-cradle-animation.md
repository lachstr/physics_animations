---
layout: post
title: "Newton's Cradle Animation"
categories: misc
---
Newton's Cradle has been animated before. However, traditionally it has often been achieved via a keyframe method or relying on a complicated physics engine. In this post we will animate Newton's Cradle by implementing our own minimalist physics engine. We will use the following guiding statement to develop our phyiscs engine;

``Newton's Cradle can be modelled as mutilple pendulums confined to swing along a single axis which undergo elastic collisions with one another. The pendulums rest such that there is a small amount of horizontal displacement between them.''

Here a pendlum means a mass on attached to a massless, rigid, fixed-length l which obeys differential equation 
...

Here "elastic" means the collisions occur conserving energy and momentum.

For a more precise mathematical description please see this [white paper]({{ site.baseurl }}/report.pdf).

We will use the [Runge–Kutta](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods) numerical integration technique.

```python
def bessj(n, x, N):
    partial_sum = 0
    
    from math import factorial 
    for l in range(N+1):
        partial_sum += (-1)**l/(2**(2*l+n)*factorial(l)*factorial(n+l))*x**(2*l+n)
    
    return partial_sum
``` 

