# problem3.12

## 本次主要是要研究混沌现象。以下是我通过百度查询的一些有关混沌现象的资料：

#### 混沌现象是指发生在确定性系统中的貌似随机的不规则运动，一个确定性理论描述的系统，其行为却表现为不确定性一不可重复、不可预测，这就是混沌现象。

#### 简介： 混沌现象是指发生在确定性系统中的貌似随机的不规则运动，一个确定性理论描述的系统，其行为却表现为不确定性一不可重复、不可预测，这就是混沌现象。进一步研究表明，混沌是非线性动力系统的固有特性，是非线性系统普遍存在的现象。牛顿确定性理论能够充分处理的多为线性系统，而线性系统大多是由非线性系统简化来的。因此，在现实生活和实际工程技术问题中，混沌是无处不在的。“ 混沌”是近代非常引人注目的热点研究，它掀起了继相对论和量子力学以来基础科学的第三次革命。科学中的混沌概念不同于古典哲学和日常语言中的理解，简单地说，混沌是一种确定系统中出现的无规则的运动。混沌理论所研究的是非线性动力学混沌，目的是要揭示貌似随机的现象背后可能隐藏的简单规律，以求发现一大类复杂问题普遍遵循的共同规律。

#### 研究起源： 1963年，Lorenz（中文名译作洛伦兹）在《大气科学》杂志上发表了“决定性的非周期流”一文，指出在气候不能精确重演与长期天气预报者无能为力之间必然存在着一种联系，这就是非周期与不可预见性之间的联系。他还发现了混沌现象“对初始条件的极端敏感性” 。这可以生动的用“蝴蝶效应”来比喻：在做气象预报时，只要一只蝴蝶扇一下翅膀，这一扰动，就会在很远的另一个地方造成非常大的差异，将使长时间的预测无法进行。在60年代研究的基础上，混沌学的研究开始进入高潮。1971年，科学家在耗散系统中正式的引入了奇异吸引子的概念。1975年，李天岩和J.A.Yorke和提出了混沌的科学概念。整个70年代中期，人们不但在理论上对混沌做更深层次的研究，而且努力在实验室中找寻奇异吸引子。李天岩和J.A.Yorke在他们的著名论文“周期3意味着混沌”中，指出：在任何一维系统中，只要出现周期3，则该系统也能出现其他长度的周期，也能呈现完全的混沌。在确定性的系统中发现混沌，改变了人们过去一直认为宇宙是一个可以预测的系统的看法。用决定论的方程，找不到稳定的模式，得到的却是随机的结果，彻底打破了拉普拉斯决定论式的可预测性的幻想。但人们同时发现到过去许多曾被认为是噪声的信号，其实是一些简单的规则生成的。这些包含内在规则的“噪声”不同于真正的噪声，它们的这种规则是完全可以应用的。


## 用Euler-Cromer方法模拟计算如下驱动力下的混沌现象：

![](https://github.com/zhaozhanyi0804/computationalphysics_N2015301020052/blob/master/Homework_7/7-6.jpg)

#### 将上式转化为两个一阶线性常微分方程：
      dω/dt=-g/l*sinθ-q*dθ/dt+FD*sin(ΩD*ti)
      
      dω/dt=ω

## 由此可得具体的数值计算方法

    ωi+1=ωi-[(g/l)sinθi-q*ωi+FD*sin(ΩD*ti)]*∆t
   
    θi+1=θi+ωi+1*∆t
   
    ti+1=ti+∆t
   
   
 #### 取g=9.8   l=9.8
   
 ## 驱动力变化时摆的运动情况变化如下图所示：
 
 ![](https://github.com/zhangsheng999/1111/blob/master/d.png?raw=true)
 
 [代码](https://github.com/zhangsheng999/1111/blob/master/d.1.txt)
 
 
 
 ## 参数q变化时摆的运动情况变化如下图所示：
 
 ![](https://github.com/zhangsheng999/1111/blob/master/e.png?raw=true)
 
 [代码](https://github.com/zhangsheng999/1111/blob/master/e.1.txt)
 
 
 ### 以上即为线性驱动力下的混沌现象
 
 
 ### 题3.12 In constructing the Poincaré section in Figure 3.9 we plotted points only at times that were in phase with the drive force; that is, at times t≈2πn/ΩD , where n is an integer. At these values of t the driving force passed through zero [see (3.18)]. However, we could just as easily have chosen to make the plot at times corresponding to a maximum of the drive force, or at times π/4  out-of-phase with this force, etc. Construct the Poincaré sections for these cases and compare them with Figure 3.9.
 
 ### 以下即为非线性驱动力下的图像（可与上面的图像做比较）
 ## FD=1.2时
 
 ![](https://github.com/zhangsheng999/1111/blob/master/f.png?raw=true)
 
 
 [代码](https://github.com/zhangsheng999/1111/blob/master/f.1.txt)
 
 
 
 ## 当只选取 t≈2πn/ΩD 时
 
 ![](https://github.com/zhangsheng999/1111/blob/master/g.png?raw=true)
 
 
 [代码](https://github.com/zhangsheng999/1111/blob/master/g.1.txt)
 
 ### 在比较线性驱动力和非线性驱动力所得的图像后，我们可以很容易的得到在非线性驱动力下可以得到混沌现象，也侧面解释了开头百度的得到的研究表明：“进一步研究表明，混沌是非线性动力系统的固有特性，是非线性系统普遍存在的现象。牛顿确定性理论能够充分处理的多为线性系统，而线性系统大多是由非线性系统简化来的。因此，在现实生活和实际工程技术问题中，混沌是无处不在的。”
 
 
 
 > * 致谢夏海峰学长提供的参考代码
 
