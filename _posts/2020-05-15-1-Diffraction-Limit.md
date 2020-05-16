---
layout:     post
title:      Diffraction Limit
author:     Guotao Pang
tags: 	   Original 欢迎转载
subtitle:  	衍射极限
published:  true
category:  articles
---
<!-- Start Writing Below in Markdown -->

在学习光学的过程中，我们经常会遇到衍射极限的问题，同时会提到瑞利判据，这个问题在电子显微镜中同样存在，只是从光的衍射成像变成了电子的衍射成像。弄清楚衍射极限的来源有助于我们理解电镜的工作原理。
首先介绍一个概念，瑞利判据：

$$\theta=1.22\frac{\lambda}{D}\qquad(1)$$

式（1）为瑞利判据的数学表达式，也是我们在学习过程中常见的式子。经常地，我们只是知道这个公式的存在，但是不知道它是怎么来的，所以会令很多小伙伴感到困惑。最基本的问题就是 $\theta$ 是什么？
$\theta$ 其实是衍射角， $\lambda$ 是光波或者电子束的波长， $D$ 是光阑直径（这里的光阑可以是透镜，也可以是光孔）。式（1）直观地表示的波长为 $\lambda$ 的电子束的角分辨率，可以看到 $\lambda$ 越小，可以分辨的衍射角 $\theta$ 越小，这代表电子束的分辨率越高。在电镜中，我们知道加速电压越高，电镜的分辨率也越高，这一现象可以用式（2）来解释

$$qU=E_{K}=\frac{p^{2}}{2m}=\frac{h^2k^2}{4\pi^2\cdot2m}=\frac{h^2}{2m}\frac{1}{\lambda^2}\qquad(2)$$

其中 $U$ 为加速电压， $q$ 为电子电荷量， $h$ 为普朗克常数， $m$ 为电子质量。可以看到，加速电压 $U$ 越大，电子束波长 $\lambda$ 越小，最后 $\theta$ 越小，即角分辨率较高。那么式（1）是怎么来的呢？这就得从衍射理论说起。式（1）直接来源于圆孔的夫琅禾费衍射理论，在该条件下，接受屏上是一系列同心圆环，中心是亮斑，即我们常说的艾里斑，其强度分布可以用式（3）来表示

$$I=I_0\left[ \frac{2J_1(ka\theta)}{ka\theta} \right]^2\qquad(3)$$

这里的 $a$ 是指衍射孔的半径，具体的推导过程可以参考高等光学衍射理论部分，或者直接参考[[工程光学（三）——光的衍射](https://zhuanlan.zhihu.com/p/47622756)]这篇文章。 $J_1$ 为一阶贝塞尔函数， $\theta$ 为衍射角。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/1-Diffraction-Limit/1-1.png" width="50%">
</p>
<p align="center">图1 衍射过程示意图</p>

如图1所示即为衍射过程示意图。夫琅禾费衍射的一个假设就是接收屏距离圆孔的距离远远大于接受屏幕上成像范围，即 $f \gg x$ ， $f$ 为透镜的焦距，这里假设接收屏在透镜的焦平面上。如果衍射屏为一个小孔，那么在接受屏上就是艾里斑。衍射极限指的是一个衍射斑的极大值的空间位置与另外一个衍射斑的第一个极小值所在空间位置重合，这种情况我们认为是可以分辨这两个衍射斑的极限情况，当两个艾里斑距离更近时则无法分辨，如图2所示。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/1-Diffraction-Limit/1-2.png" width="300">
  <br>图2 衍射极限示意图
</p>

<p align="center">图2 衍射极限示意图</p>

> http://hyperphysics.phy-astr.gsu.edu/hbase/phyopt/Raylei.html

根据式（3）得到艾里斑第一极小条件为 $ka\theta=1.22\pi$ ，最后得到了

$$\theta=\frac{1.22\pi}{ka}=\frac{1.22\lambda}{d}\qquad(4)$$

如果衍射孔的直径比透镜要大，即透镜在衍射过程中其主要作用，则可以得到

$$\theta=\frac{1.22\pi}{ka}=\frac{1.22\pi}{D}\qquad(5)$$

这就是瑞利判据的来源。
根据图1，有

$$\sin\theta\approx\frac{x}{f}\approx\theta\qquad(6)$$

这里用到了两个近似，一个是 $f\gg x$ ，另一个就是认为 $\theta$ 很小，导致 $\sin\theta\approx\theta$ 。将式（6）代入到式（5）得到

$$x=\frac{1.22\lambda f}{D} \qquad (7)$$

这就是所谓的分辨力，即系统可以分辨的最小距离。
可能会有小伙伴困惑，从图1可知 $x$ 不是接收屏上的像的距离吗？为什么不是两个光源之间最小距离叫做分辨力，而要用接受屏上的距离？这里我们需要弄清楚相关逻辑。一般而言我们只讨论角分辨力，所关心的其实只有 $\theta$ ，而 $\theta$ 只与 $\lambda$ 和 $D$ 有关，所以一旦 $\lambda$ 和 $D$ 确定了，那么系统的角分辨率也就确定了。这里 $\theta$ 也是两个光源与透镜之间的夹角，如图1中 $\theta_1$ 所示。所以两个光源 $O_1$ 和 $O_2$ 能否分辨开与它们之间的距离无关，而与它们和透镜形成的夹角有关，只要夹角不低于瑞利判据所规定的夹角，它们总是可以被系统分辨开的。这里 $x$ 表示在该系统中，物体可以被分辨的空间距离恰好是 $x$ ，距离再小系统就无法很好的分辨了。
这里我们用眼睛举一个例子
一般人的虹膜直径约为5 mm，肉眼对波长555 nm的光最敏感，可以得到：

$$\theta\approx1.220\frac{555\times10^{-9}}{5\times10^{-3}}=0.000135\ rad$$

在眼科医生或配眼镜时所用的斯内伦视力表，一般正常的肉眼视力，应在6m的距离看到8.8mm的图像。

$$\theta\approx\tan\theta=\frac{d}{L}=\frac{8.8\times10^{-3}}{6}=0.00147\ rad$$

该结果大于瑞利判据所要求的的最小分辨角。

> https://zh.wikipedia.org/wiki/%E8%A7%92%E5%88%86%E8%BE%A8%E7%8E%87

在公式中我们涉及到了透镜的直径 $D$ ，而没有用小孔的直径，这是因为衍射光线在各个角度都有，但只有入射到透镜范围内的衍射光线会重新在接受屏上成像。这里我们可以用数值孔径来形容透镜收集光线的能力，其表达式如下

$$NA=n\sin\alpha\qquad(8)$$

式中 $\alpha$ 为物体与透镜形成的最大夹角的一半，即半角， $n$ 为周围环境折射率，如图3所示。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/1-Diffraction-Limit/1-3.png" width="50%">
</p>
<p align="center">
  图3 数值孔径示意图
</p>

根据图2，

$$\sin\alpha=\frac{D/2}{f}=\frac{D}{2f}\qquad(9)$$

最终得到

$$x=\frac{0.61\lambda}{n\sin\alpha}=\frac{0.61\lambda}{NA}\qquad(10)$$

可以看到空间分辨力与透镜的数值孔径有关系，数值孔径越大，意味着 $\alpha$ 越大，即 $D$ 越大，得到的 $x$ 越小，即分辨力越高。这说明，透镜尺寸越大，得到的像分辨率越高。而透镜尺寸越大带来的影响首先就是可以收集到更多的衍射光线（高角度衍射光线，即衍射光的高频成分），说明衍射光高频成分对于像分辨率有很重要的作用。在衍射成像中，空间频率可以表示为

$$f_x=\frac{x}{\lambda d}=\frac{\sin\theta_x}{\lambda}\qquad(11)$$

$\theta_x$ 即为图3中的 $\alpha$ ，可以看到， $\theta_x$ 大的衍射光具有较高的空间频率，即这些光为所有衍射光中的高频成分。由式（10）可知， $\theta_x$ 越大，像分辨率越高，即像的细节更加清晰，这说明在衍射成像过程中，衍射光的高频成分决定细节是否清晰，而通常低频成分可以用来得到像的轮廓。在电镜电子束成像过程中，这一规律同样适用。

<span id="busuanzi_container_page_pv">本文总阅读量<span id="busuanzi_value_page_pv"></span>次
