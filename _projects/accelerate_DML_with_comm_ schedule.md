---
title: "Accelerate_DML_with_Comm_Schedule"
collection: projects
permalink: /projects/accelerate_DML_with_comm_schedule
excerpt: 'This project is about accelerating DML with communincation schedule.'
---
## Overview
At present, communication overhead has become the bottleneck of distributed machine learning(DML) training. DML usually adopts a centralized parameter server(PS) architecture, which easily leads to unreasonable utilization of network resources. 

We design a network priority scheduling method to accelerate distributed machine learning by analyzing lots of communication track of DML based on PS.Through experiments, DML with priority scheduling was accelerated by 30% on average.

## Experiment Topology

<img class="img-responsive" src="/images/Accelerate_DML_with_Comm_Schedule/topology.png">

> Due to the current technical limitations of the implementation, scheduling is only effective through the switch, so there are seemingly superfluous 10g links and switch1 above. We are actively looking for ways to implement scheduling on the host.

## Current Results

|   model    | param mem |   flops    |     no schedule(imgs/sec)      |    with schedule(imgs&#47;sec)     | speed up |
| :--------: | :-------: | :--------: | :---------------------------------: | :---------------------------------: | :------: |
|  alexnet   |  233 MB   | 727 MFLOPs |                0.24                 |                0.34                 |  41.67%  |
| googlenet  |   51 MB   |  2 GFLOPS  | 2.06+2.11+2.14+<br>2.22+2.15=2.136 | 2.66+2.84+2.78+<br>2.87+2.84=2.798 |  30.99%  |
| inception3 |   91 MB   |  6 GFLOPS  | 0.63+0.62+0.62+<br>0.64+0.63=0.628 | 0.79+0.78+0.79+<br>0.83+0.75=0.788 |  25.48%  |
|  resnet50  |  107 MB   |  4 GFLOPS  |  0.6+0.6+0.59+<br>0.6+0.58=0.594   | 0.78+0.78+0.76+<br>0.76+0.77=0.77  |  29.63%  |

<!-- | mobilenet  |   16 MB   | 579 MFLOPs |  2.31+2.3+2.3+2.33+2.34=2.316  | 2.31+2.36+2.34+2.36+2.36=2.346  |  1.30%   |  -->

<!-- <img class="img-responsive" src="/images/ECCV2018_architecture.jpg">

## Publication:
Y. Huang, <u>M. Cai</u>, Z. Li and Y. Sato, &quot;Predicting Gaze in Egocentric Video by Learning Task-dependent Attention Transition,&quot; <i>European Conference on Computer Vision (**ECCV**)</i>, 2018. (<font color="blue">oral presentation, acceptance rate: 2.4%</font>)  
[[Arxiv preprint]](/files/HCLS_eccv_arxiv2018.pdf)
[[Code]](https://github.com/hyf015/egocentric-gaze-prediction)

### Demo video (Youtube)
<iframe width="560" height="315" src="https://www.youtube.com/embed/TiFz-LP3LW4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe> -->
