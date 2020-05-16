---
layout:     post
title:      Contrast Transfer Function
author:     Guotao Pang
tags: 	   Original 欢迎转载
subtitle:  	Contrast transfer function/衬度传递函数 
published:  true
category:  articles
---
<!-- Start Writing Below in Markdown -->


在电子显微镜中，我们看到的像是散射电子在探测器上形成的衬度（contrast），探测器上接收到的电子越多，形成的像越亮，接收到的电子越少，形成的像越暗。从波的角度讲，探测器上接收到的信号是直接透射电子束和不同频率散射电子束在像平面干涉的结果，像的衬度和不同频率光在像平面上的相位有关。这里我们用一个函数来描述不同频率分量在像平面的强度——衬度传递函数（Contrast transfer function，CTF）或者强度传递函数（Intensity transfer function，ITF）。

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture1.png" width="50%">
  <br>图1
</p>

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture2.png" width="50%">
  <br>图2
</p>

<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture3.png" width="50%">
  <br>图3
</p>

图1所示为TEM成像示意图。电子束到达样品表面后绝大部分直接透射（电子束$a$），其余被散射（电子束$b$，$c$，$d$），并且散射角度越大，代表空间频率越高，高频成分越多，所成像分辨率越高。每一束散射电子束都会与直接透射电子束在像平面产生干涉，干涉的结果与这两束电子束的相位有关。以直接透射电子束的相位为参照点，当电子被散射时，首先会出现 $\pi/2$的相位差（散射电子与直接透射电子在样品出射面就已经存在的相位差），这里暂且称之为相位滞后 $\pi/2$。除了这一部分相位差，由于不同电子束传播路径的不同，会在空间形成另一个相位差。例如，$b$电子束由于比$a$电子束多走了一段距离，相位滞后$\pi/2$，那么这两束电子束总的相位差为 $\pi$，我们可以用$\phi$表示。在图2中表示出了这两束电子束的振幅以及他们的相位关系，通过简单的向量运算，我们可以知道光束b所代表的空间分量在像平面的强度，也就是总向量模的平方。我们将这个过程叫做衬度传递函数（Contrast transfer function，CTF），并且用$CTF = sin(\phi)$来描述这个过程。在图3中，我们将b向量所对应的空间频率与CTF的关系表示出来，如 $b$ 点所示，在空间频率为 $b$ 所在位置时，该分量在像平面所对应的的强度最小，为 $-1$ 。同理，我们可以大致表示出其他空间频率分量所对应的CTF，如 $a$ ， $c$ 和 $d$ 点所示。
这里我们只考虑了不同散射分量与直接透射光的干涉，实际上，不同透射光之间的干涉过程非常复杂，通常我们可以用下面的公式来表示：

$$CTF=sin⁡(\phi)=sin⁡(πΔfλu^2+1/2 πC_s λ^3 u^4)$$

这里，$\phi$ 是相位，$Δf$ 是Defocus，λ 是电子束的在样品中的波长，$u$ 是空间频率（Spatial Frequency）， $C_s$ 是透镜的球差（Spherical Aberration）。
在透射电镜中，当Electron Gun的电压确定了，那么电子束的波长也就确定了。Defocus    $Δf$ 和 $C_s$  是可以人为控制的参量。所以，在CTF中，实际上只有一个自变量 $u$ 。那么Defocus $Δf$ 和球差 $C_s$ 如何影响CTF呢？

假设高压 $HV=200kV$ ，所对应的电子束波长 $λ$为 $2.508\ pm$。
我们先固定$Δf$，并且令 $Δf= -60$，改变$C_s$（$C_s=1mm,2mm,3mm$），对应的CTF~u曲线如下图所示。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture4.png" width="50%">
  <br>图4
</p>

图中 $u_1$ 为除了0点以外第一个和横轴的交点，可以用来表示该条件下透镜的分辨能力，因为在该点，CTF从负变为正，这个变化过程是非常明显的。从图中可以看到，当球差$C_s$越大时，$u_1$ 越小，表明可以分辨的频率极限越小，最终所成像的分辨率越小。所以实际应用中，我们希望球差越小越好。
实际的入射电子束很难保证完全平行，总会有一定的倾角，不同传播方向的电子束具有一定的空间相干(Partial spatial coherence)；另外，电子束中电子的能量并不完全是一样的，会有一定的色散，即电子束具有一定的能量分布。在透镜强度一定的情况下，能量较小的电子更容易发生会聚，能量较大的电子不易发生会聚，不同能量电子到达会聚点时的时间不一样，这样又会引入一定的时间相干（Temporal coherence）。由于这两个因素的存在，真正的CTF曲线并不是像图4所示一直是震荡，而是随着空间频率增大逐渐衰减为0，如图5所示，这时衬度最低，这也是为什么透镜是有分辨率极限的。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture5.png" width="50%">
  <br>图5
</p>

同样我们可以固定 $C_s$ ，并且令 $C_s=2 mm$ ，改变 $Δf$（$Δf=-50 nm,-100 nm,-200 nm$），对应的CTF~u曲线如图6所示。$u_1$ 的位置随 $Δf$ 不一定是线性变化的，而是有一个最佳值。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture6.png" width="50%">
  <br>图6
</p>

$Δf$ 可以为正值也可以为负值，但是 $Δf$ 最佳值不一定是0，因为最佳的 $Δf$ 往往会受到 $C_s$ 的影响。这里介绍一个概念——Scherzer defocus（$Δf_{Sch}$）,并且

$$Δf_{Sch}=-1.2(C_s λ)^{1/2}$$

当Defocus为 $Δf_{Sch}$ ，可以实现最佳的分辨率，可以说，$Δf_{Sch}$代表设备的分辨极限。图7为Defocus取不同值时，样品物函数（Objective Function）的傅里叶变换（Fourier Transformation），左图为 $0.5Δf_{Sch}$ ，右图为 $Δf_{Sch}$ 。这里我们可以看到，我们之前讲的CTF其实就是图7倒空间图案某个方向的截线。尽管右图的圆环更加模糊，但实际上这时TEM光路恰好具有最高的分辨率。左图圆环更加清楚，但是Defocus太大，光路偏离最佳工作状态较远。在实际操作中，有时候我们会故意调大Defocus，使圆环更加清楚，这时我们可以很方便看到是否存在像散（Astigmatism）并通过调节光路将其消除。
 
<p align="center">
  <img src="https://emfollower.github.io/EMFollower/img/3-Contrast_transfer_function/Picture7.png" width="50%">
  <br>图7
</p>
