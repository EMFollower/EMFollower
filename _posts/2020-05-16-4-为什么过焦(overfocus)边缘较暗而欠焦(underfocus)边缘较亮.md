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

电子显微镜和光学显微镜一样，只有当散射电子束或者反射光恰好聚焦在像平面上时（在电子显微镜中是CCD的共轭面，在光学显微镜中是人眼的视网膜），才能成清晰的像，如果聚焦不到这个平面上，那么探测器接收到的就是一个模糊的像。根据散射电子束是否能聚焦到像平面上一般有三种情况：过焦（Overfocus），欠焦（Underfocus）和恰好聚焦到像平面（In focus）。图1和图2为这三种聚焦情况示意图。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture1.png" width="50%">
  <br>图1
</p>

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture2.png" width="50%">
  <br>图2
</p>

图1和图2均为三种不同聚焦情况示意图，但是其形成的原因不同。图1中是通过改变加在透镜上的电流从而改变透镜的聚焦强度来实现不同的聚焦情况。图中透镜颜色越深代表透镜强度越大，聚焦效果越强。可以看到，在Overfocus情况下，透镜聚焦强度最大，In focus情况下，透镜聚焦强度次之，在Underfocus情况下，透镜聚焦强度最小。
图2是通过改变样品高度实现不同的聚焦情况。在In focus情况下，如果将样品高度减小，则散射电子束会聚在像平面下方，为Underfocus；如果将样品高度增加，则散射电子束会聚在像平面上方，为Overfocus。
在操作透射电镜的过程中，我们会发现，在Overfocus情况下，样品边缘较暗；在Underfocus情况下，样品边缘较亮；在恰好对焦到像平面的情况下，样品边缘衬度最低，如图3所示。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture3.png" width="50%">
  <br>图3
</p> 

不论是调节透镜聚焦强度还是改变样品高度都会引起图3中的变化。因此我们可以通过观察样品边缘细微结构的明暗来判断样品是否处于合适的高度或者透镜是否为合适的强度。我们知道透镜会存在球差，在没有球差校正器的情况下，球差对成像分辨率影响很大。所以，当我们在对焦时，主要是改变样品的高度来对焦，而不是改变透镜的强度。当样品处于合适的高度时再改变透镜强度进行微调。微调也会再次引入球差的影响，但由于改变很小，基本不影响拍照。
现在我们知道什么是Overfocus、Underfocus和In focus，那么为什么不同的对焦情况下样品边缘细微结构具有不同的衬度呢？这还得从衬度传递函数（Contrast transfer function， CTF）说起。在文章“Contrast transfer function”中，我们已经介绍了衬度传递函数，它是样品在像平面的衬度随空间频率的分布。
空间频率u与样品的结构有密切关系，从样品中散射出来的电子束既有高频成分，也有低频成分，当我们将高频成分滤掉时，所成像只是一个模糊的轮廓；如果只有高频成分而将低频成分滤掉，所成像只有一些锐利的细节而没有轮廓，如图4所示为HRTEM的滤波情况。这两种情况哪种都不能完整再现样品的信息。所以在成像过程中，我们既要接收高频信号，也要接收低频信号，低频信号散射角较小，很容易被相机接收到；但是高频成分散射角较大，鉴于电镜腔体的大小和相机的尺寸，不可避免的会丢失一些高频信号，这也是阻碍提高电镜分辨率的一个原因。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture4.png" width="50%">
  <br>图4
</p> 

现在我们回到衬度传递函数（CTF）。
衬度传递函数的表达式如下式所示：

$$CTF=sin⁡(χ)=sin⁡(πΔfλu^2+1/2 πC_s λ^3 u^4)$$

我们可以看到在相位中有两项，第一项和样品的高度有关，有时候 ∆f 也可以用z（样品高度）来表示。第二项和透镜有关，由于我们使用电镜时会尽量避免改变透镜参数，所以这里不同的聚焦情况我们都是针对样品高度而言的。
Δf>0 表示样品升高，Overfocus；Δf<0 表示样品降低，Underfocus.
图5为CTF在Δf从-200nm~200nm变化的曲线图。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture5.png" width="50%">
  <br>图5
</p> 

样品明暗程度与其对应的空间频率密切相关。为了方便说明，这里我们在图3中将样品的细节标出来，如图6（c）。样品的边缘由于积碳或者氧化的原因，往往会有一层很细微的结构（非晶层），其尺寸与块体样品比起来小得多，因而其对应的空间频率高很多。例如图6（c）中的边缘大约为1nm，这里我们取1.3nm，没有太大差别，但是计算方便。1.3nm对应的空间频率约为0.75 nm-1（空间频率或倒空间尺度与正空间样品尺度互为倒数关系，因为是对低频和高频进行比较，我们不需要考虑2pi这个系数），在图5中对应0.75 nm-1处的竖直虚线。从这条虚线与各CTF曲线的交点，我们便可知道不同Δf所对应的CTF。很明显可以看到，当Δf>0 时，CTF< 0，对应像的区域较暗，为Overfocus；Δf<0时，CTF>0，对应相的区域较亮，为underfocus。Δf=0时，CTF接近于0。看完这个细微的边缘结构，我们再看整个样品。只考虑图中的区域，样品也有130nm大小，对应的空间频率约为0.0077nm-1，与1.5nm-1相比小得多，从图中能看到无论Δf怎么变，CTF都基本为0。这就在操作电镜的过程中为我们提供了一个标准，整个样品的CTF基本一直为0，而边缘等细微结构在Δf=0时CTF也为0，说明Δf=0，CTF=0是边缘CTF变化的一个分界线，其亮暗程度都是相对整个样品低频成分的CTF变化的。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture6.png" width="50%">
  <br>图6
</p>  

以上就是Overfocus边缘较暗，Underfocus边缘较亮的原因。上面的讨论用到了CTF，有一些抽象，下面我们可以用较为直观的方法进行解释。
如图7所示，橙黄色电子束为恰好聚焦在像平面时的情况。在左图中，将样品抬升一些，此时散射电子束用蓝色箭头表示。由于样品是不变的，所以散射规律是不变的，所有的散射电子束将和样品一样向上平移。由于透镜尺寸不变，那么最终处于两侧的电子束无法有效被透镜收集到，如a2最终丢失。处于两侧的电子束属于高频成分，由于高频成分丢失，也就是收集的电子数变少，所以对应正空间中很细微的结构看上去将会变暗，对应Overfocus。如果将样品从In focus的高度向下降一些，如图7中右图所示，与左图刚好相反，不仅原本的散射电子束都被收集到，更高频的电子束也会被收集到，如原本收集不到的a3现在也被收集到，那么样品边缘部分所对应的像收集到的电子数变多了，所以显得较亮，此时对应Underfocus。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/4-Overfocus_and_underfocus/Picture7.png" width="50%">
  <br>图7
</p> 

>图3和图6引用自:
Brown, Paul D. "Transmission Electron Microscopy-A Textbook for Materials Science, by David B. Williams and C. Barry Carter." Microscopy and Microanalysis 5.6 (1999).
