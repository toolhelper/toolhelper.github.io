---
layout: post
title: 信号与系统（一）
categories: [复习, 信号与系统]
description: 信号与系统复习记录
excerpt: 信号与系统复习记录
keywords: 信号与系统, 复习 
---

## 第二章

### KCL和KVL

1. KCL
   
   - 所有进入某节点的电流的总和等于所有离开这节点的电流的总和。
   
   - **沿着闭合回路所有元件两端的电势差（电压）的代数和等于零。** $ \sum_{k=1}^ni_k=0 $

2. KVL
   
   - 沿着闭合回路的所有电动势的代数和等于所有电压降的代数和。
   
   - **沿着闭合回路所有元件两端的电势差（电压）的代数和等于零。**$\sum_{k=1}^mv_k=0$

> 从时域来求解系统数学模型（对于系统，一般运用KCL和KVL等方法将其抽象成为一个数学模型进行求解），有微分方程法（经典法求解）和卷积积分法（零状态响应）。

### 微分方程的经典解法

1. 齐次微分方程
   
   - 非齐次线性方程组：常数项不全为零的线性方程组
   
   - 齐次线性方程组：常数项全部为零的线性方程组

2. 特征方程

3. 特征根（求解特征方程）

4. 齐次解形式

5. 特解（输入信号的形式对应着不同的特解）

6. 全解（=齐次解+特解）

> 全响应=零输入响应+零状态响应

### 零输入响应和零状态响应

1. 零输入响应
   
   零输入响应就是激励$x(t)=0$，仅由系统初始条件引起的响应（对应齐次解）

2. 零状态响应
   
     零状态响应就是将系统初始状态为零状态，$y^p(0)=0$（对应特解）  

### 不同的响应

- 自然响应 vs 受迫响应 （齐次解 vs 特解）

- 瞬态响应 vs 稳态响应  
  
  *自然响应是系统的固有频率的体现，不会产生新的频率*

> 换路期间，电容器两端电压和电感中的电流不会发生突变（电荷不会突然消失，自感电势、自感电流）。

### 单位冲激响应

*单位冲激响应是系统在单位冲击信号$\delta(t)$作用下的零状态响应，代表系统本身的固有性质。*

### 单位阶跃响应

*单位阶跃响应$s(t)$是系统在单位阶跃激励$u(t)$作用下的零状态响应，可以借此确定系统的稳定性。*

> 用冲激函数可以表示任意信号

### 卷积积分的性质

- 交换律

- 结合律

- 分配律
  
  *结合一个信号连续通过三个系统（卷积三次）来理解，可以交换次序或者把某两个系统看做一个系统*

- 微分积分性质

### 根据`h(t)`判断系统性质

- 稳定性
  
  输入有界，输出也有界

- 因果性
  
  输出只取决于现在和过去的输入，与未来的输入无关。

- 非记忆性
  
  非记忆性系统（即时系统）输出仅取决于同时刻的输入，而与别的时刻输入值无关。
  
  > 当系统为`u(t)`时，相当于对系统进行积分。为$\delta(t)$时，系统为恒等系统。