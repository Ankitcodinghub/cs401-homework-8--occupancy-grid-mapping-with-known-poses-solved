# cs401-homework-8--occupancy-grid-mapping-with-known-poses-solved
**TO GET THIS SOLUTION VISIT:** [CS401 Homework 8- Occupancy Grid Mapping With Known Poses Solved](https://www.ankitcodinghub.com/product/cs401-homework-8-occupancy-grid-mapping-with-known-poses-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;99134&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS401 Homework 8- Occupancy Grid Mapping With Known Poses Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
# Homework 8 – Occupancy Grid Mapping With Known Poses

**Coding Homeworks.** Your final submission should be a compressed package with extension .zip, which includes your codes and explanations (you need to know how to write the manuscript with Markdown or LATEX). Your code should be run step-by-step without any error. Real-time animation is also recommended.

—-

## Overview

Occupancy grid maps (Hans Moravec, A.E. Elfes: High resolution maps from wide angle sonar, Proc. IEEE Int. Conf. Robotics Autom. (1985)) are a popular approach to represent the environment of a mobile robot given known poses. The grid is basically discrete representation of the environment, which stores the posterior probability that the corresponding area in the environment is occupied or not, and each grid cell is considered independently from all others. Occupancy grid maps can be learned efficiently using a probabilistic approach. Reflection maps are an alternative representation. They store in each cell the probability that a beam is reflected by this cell. In this homework, we focus on the usage of probabilistic approach.

## Occupancy Mapping

A robot has to build an occupancy grid map (cells c0, . . . cn) of a simple one-dimensional environment using a sequence of measurements from a range sensor:

&lt;div align=center&gt; &lt;img src=images/demo.png width=50%/&gt; &lt;/div&gt;

Assume a very simple sensor model: every grid cell with a distance (based on its coordinate) smaller than the measured distance is assumed to be occupied with p = 0.3. Every cell behind the measured distance is occupied with p = 0.6. Every cell located more than 20cm behind the measured distance should not be updated.

## Task 1

Please calculate the resulting occupancy grid map using the inverse sensor model using Python.

Assign the cell coordinates, which span from 0 to 200 (both endpoints included) with increments of 10, to one array c and the belief values to another array m. Use matplotlib.pyplot.plot(c,m) to visualize the belief.

&lt;div align=center&gt; &lt;img src=images/belief_task1.png width=50%/&gt; &lt;/div&gt;

The measurements and the prior belief are given in the follow table:

| Grid resolution | 10cm |

|——————————|——————————————–|

| Map length (1D only) | 2m |

| Robot position | c0 |

| Orientation (of th e sensor) | heading to cn (see figure) |

| Measurement (in cm) | 101, 82, 91, 112, 99, 151, 96, 85, 99, 105 |

| Prior | 0.5 |

In order to solve this exercise we will use log-odds, as they provide a very simple update formula, with only one addition and one subtraction.

Recall the log-odds update formula:

&lt;img src=”https://latex.codecogs.com/svg.image?l(m_i|z_{1:t},&amp;space;x_{1:t})&amp;space;=&amp;space;l(m_i|z_t,x_t)&amp;space;&amp;plus;&amp;space;l(m_i|z_{1:t-1},x_{1:t-1})&amp;space;-&amp;space;l(m_i)” title=”https://latex.codecogs.com/svg.image?l(m_i|z_{1:t}, x_{1:t}) = l(m_i|z_t,x_t) + l(m_i|z_{1:t-1},x_{1:t-1}) – l(m_i)” /&gt;

From the exercise we know that the prior:

&lt;img src=”https://latex.codecogs.com/svg.image?p(m_i)=0.5&amp;space;\Rightarrow&amp;space;l(m_i)&amp;space;=&amp;space;log\frac{p(m_i)}{1-p(m_i)}&amp;space;=&amp;space;0″ title=”https://latex.codecogs.com/svg.image?p(m_i)=0.5 \Rightarrow l(m_i) = log\frac{p(m_i)}{1-p(m_i)} = 0″ /&gt;

We also know that the inverse sensor model is the following:

&lt;img src=”https://latex.codecogs.com/svg.image?p(m_i/z_t,x_t)&amp;space;=&amp;space;\left\{\begin{matrix}0.3&amp;space;&amp;&amp;space;if&amp;space;position(m_i)&amp;space;\leq&amp;space;z_t&amp;space;\\0.6&amp;space;&amp;&amp;space;if&amp;space;position(m_i)&amp;space;&gt;&amp;space;z_t&amp;space;\wedge&amp;space;position(m_i)\leq&amp;space;z_t&amp;plus;20&amp;space;cm&amp;space;\\0.5&amp;space;(unused)&amp;space;&amp;&amp;space;if&amp;space;position(m_i)&amp;space;&gt;&amp;space;z_t&amp;space;&amp;plus;&amp;space;20&amp;space;cm&amp;space;\\\end{matrix}\right.” /&gt;

The log-odds ratio should be applied to this function in order to obtain &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;l(m_i|z_t,x_t)” title=”https://latex.codecogs.com/svg.image?\inline l(m_i|z_t,x_t)” /&gt;. Note

that unused in this context means we should not update the corresponding &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;m_i” title=”https://latex.codecogs.com/svg.image?\inline m_i” /&gt; cells. Doing

an update with &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;p(m_i|z_t,x_t)&amp;space;=&amp;space;0.5″ title=”https://latex.codecogs.com/svg.image?\inline p(m_i|z_t,x_t) = 0.5″ /&gt; would be equivalent, since &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;l(0.5)&amp;space;=&amp;space;0″ title=”https://latex.codecogs.com/svg.image?\inline l(0.5) = 0″ /&gt;, but computationally more expensive.

The solution of this exercise will thus involve applying for each measurement and for each cell the log-odds update formula. Once we are done with that we convert from log-odds to probability and display the output. Note that the inverse transformation is the unique solution w.r.t. p of the log-odds definition:

&lt;img src=”https://latex.codecogs.com/svg.image?l&amp;space;=&amp;space;log&amp;space;\frac{p}{1-p}&amp;space;\Rightarrow&amp;space;exp&amp;space;\,&amp;space;l&amp;space;=&amp;space;\frac{p}{1-p}” title=”https://latex.codecogs.com/svg.image?l = log \frac{p}{1-p} \Rightarrow exp \, l = \frac{p}{1-p}” /&gt;

&lt;img src=”https://latex.codecogs.com/svg.image?(1-p)&amp;space;exp&amp;space;\,&amp;space;l&amp;space;=&amp;space;p\Rightarrow&amp;space;exp&amp;space;\,&amp;space;l&amp;space;=&amp;space;p(1&amp;plus;exp&amp;space;\,&amp;space;l)&amp;space;” title=”https://latex.codecogs.com/svg.image?(1-p) exp \, l = p\Rightarrow exp \, l = p(1+exp \, l) ” /&gt;

&lt;img src=”https://latex.codecogs.com/svg.image?p&amp;space;=&amp;space;\frac{exp&amp;space;\,&amp;space;l}{1&amp;plus;exp&amp;space;\,&amp;space;l}&amp;space;=&amp;space;\frac{exp&amp;space;\,&amp;space;l&amp;space;&amp;plus;&amp;space;1&amp;space;-1}{1&amp;plus;exp&amp;space;\,l}&amp;space;=&amp;space;1&amp;space;-&amp;space;\frac{1}{1&amp;plus;exp&amp;space;\,&amp;space;l}&amp;space;” title=”https://latex.codecogs.com/svg.image?p = \frac{exp \, l}{1+exp \, l} = \frac{exp \, l + 1 -1}{1+exp \,l} = 1 – \frac{1}{1+exp \, l} ” /&gt;

## Task 2

Prove that in the occupancy grid mapping framework the occupancy value of a grid cell &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;P(m_j|x_{1:t};z_{1:t})” title=”https://latex.codecogs.com/svg.image?\inline P(m_j|x_{1:t};z_{1:t})” /&gt; is independent of the order in which the measurements are integrated.

Let us consider the log-odds update formula and let us recursively unwrap it:

&lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;l(m_i|z_{1:t},&amp;space;x_{1:t})&amp;space;=&amp;space;l(m_i|z_t,&amp;space;x_t)&amp;space;&amp;plus;&amp;space;l(m_i|z_{1:t-1},&amp;space;x_{1:t-1})&amp;space;-&amp;space;l(m_i)&amp;space;\\=&amp;space;&amp;space;l(m_i|z_t,&amp;space;x_t)&amp;space;&amp;plus;&amp;space;l(m_i|z_{1:t-1},&amp;space;x_{1:t-1})&amp;space;&amp;plus;&amp;space;l(m_i|z_{1:t-2},&amp;space;x_{1:t-2})&amp;space;-&amp;space;2.l(m_i)&amp;space;\\=&amp;space;…&amp;space;=&amp;space;&amp;space;\sum_{k=1}^{t}l(m_i|z_k,x_k)&amp;space;-&amp;space;t.l(m_i)” title=”https://latex.codecogs.com/svg.image?\inline l(m_i|z_{1:t}, x_{1:t}) = l(m_i|z_t, x_t) + l(m_i|z_{1:t-1}, x_{1:t-1}) – l(m_i) \\= l(m_i|z_t, x_t) + l(m_i|z_{1:t-1}, x_{1:t-1}) + l(m_i|z_{1:t-2}, x_{1:t-2}) – 2.l(m_i) \\= … = \sum_{k=1}^{t}l(m_i|z_k,x_k) – t.l(m_i)” /&gt;

It is clear that &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;l(m_i|z_{1:t},&amp;space;x_{1:t})” title=”https://latex.codecogs.com/svg.image?\inline l(m_i|z_{1:t}, x_{1:t})” /&gt; is simply a sum of the log-odds form of the inverse measurements. Suppose that we exchange a measurement at time i with the measurement at a different time j. Since the sum is a commutative operator we will still obtain the same value of &lt;img src=”https://latex.codecogs.com/svg.image?\inline&amp;space;l(m_i|z_{1:t},&amp;space;x_{1:t})” title=”https://latex.codecogs.com/svg.image?\inline l(m_i|z_{1:t}, x_{1:t})” /&gt;. Hence, we can repeat exchanging measurements to obtain any order permutation of the measurements without changing the result. Finally, since the log-odds value does not change, neither will the corresponding probability.

## Code instructions for tasks

**Note1** [task1.py](code/task1.py) give the implememtation framework of the task1.

**Note2** [task2.py](code/task2.py) give the implememtation framework of the task2.
