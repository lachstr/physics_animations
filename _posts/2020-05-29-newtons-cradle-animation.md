---
layout: post
title: "Newton's Cradle Animation"
categories: misc
---
Newton's Cradle has been animated before. However, traditionally it has often been achieved via a keyframe method or relying on a complicated physics engine. In this post we will animate Newton's Cradle by implementing our own minimalist physics engine. We will use the following guiding statement to develop our phyiscs engine;

"Newton's Cradle can be modelled as mutilple pendulums confined to swing along a single axis which undergo elastic collisions with one another. The pendulums rest such that there is a small amount of horizontal displacement between them.''

Here a pendlum means a mass on attached to a massless, rigid, fixed-length <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\ell" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\inline&space;\ell" title="\ell" /></a> which obeys differential equation 

<a href="https://www.codecogs.com/eqnedit.php?latex=\ddot{\theta}&space;=&space;-\frac{g}{\ell}\sin(\theta)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\ddot{\theta}&space;=&space;-\frac{g}{\ell}\sin(\theta)" title="\ddot{\theta} = -\frac{g}{\ell}\sin(\theta)" /></a>

Here "elastic" means the collisions occur conserving energy and momentum.

For a more precise mathematical description please see this [white paper]({{ site.baseurl }}/cradle/cradle_report.pdf).

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

One of the most striking results of this simulation is we have appeared to recreated the effect where the internal balls begin to move. Note how in this video of a real pendulum we see the same effect.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0LnbyjOyEQ8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The explanation I can come up with for this originates from what we meant by the sepertion between pendulums being "small." 

"If the pendulums ever collide such that atleast one of them is non-perpendicular to the horizontal then there will be a runaway feedback loop where the internal ones begin to move."

A possible explanation for why a real pendulum exhibits this behavior is because the masses either touch on one another or have some non-zero seperation between them - in either case collisions will occur at an angle non-perpendicular to the horizontal and the aforementioned runaway feedback loop will occur. 

With our simulated system we can place the pendulums closer together fairly easily, observe how this increases the time before the motion of the internal masses becomes obvious. 

Original seperation between pendulums
<video width="800" height="428" controls>
	  <source src="{{ site.baseurl }}/cradle/3_masses_1_raised.mp4" type="video/mp4">
</video> 
1/10th of original seperation between pendulums
<video width="800" height="428" controls>
	  <source src="{{ site.baseurl }}/cradle/3_masses_1_raised_closer_at_rest.mp4" type="video/mp4">
</video> 

We could continue placing the masses closer and closer together, yet this comes at the cost of computation time. I thought this was a very interesting observation.  