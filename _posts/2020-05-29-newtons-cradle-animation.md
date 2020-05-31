---
layout: post
title: "Newton's Cradle Animation"
categories: misc
---
Newton's Cradle has been animated before. However, traditionally it has often been achieved via a keyframe method or relying on a complicated physics engine. In this post we will animate Newton's Cradle by implementing our own minimalist physics engine. We will use the following guiding statement to develop our phyiscs engine;

"Newton's Cradle can be modelled as mutilple pendulums confined to swing along a single axis which undergo elastic collisions with one another. The pendulums rest such that there is a small amount of horizontal displacement between them.''

Here a pendlum means a mass on attached to a massless, rigid, fixed-length l which obeys differential equation 
...

Here "elastic" means the collisions occur conserving energy and momentum.

For a more precise mathematical description please see this [white paper]({{ site.baseurl }}/report.pdf).

We will use the [Runge–Kutta](https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods) numerical integration technique.

```python

``` 

<video width="800" height="428" controls>
	  <source src="{{ site.baseurl }}/cradle/2_masses_1_raised.mp4" type="video/mp4">
</video> 


<video width="800" height="428" controls>
	  <source src="{{ site.baseurl }}/cradle/3_masses_1_raised.mp4" type="video/mp4">
</video> 

<video width="800" height="428" controls>
	  <source src="{{ site.baseurl }}/cradle/5_masses_3_raised.mp4" type="video/mp4">
</video> 

One of the most striking results of this simulation is we have appeared to recreated the effect where the internal balls begin to move. Note how in this [video]() of a real pendulum we see the same effect.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0LnbyjOyEQ8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
