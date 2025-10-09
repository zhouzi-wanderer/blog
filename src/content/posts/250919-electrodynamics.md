---
title: 电动力学
published: 2025-09-19
description: ''
image: '../../assets/images/studying.png'
tags: [notes, electrodynamics]
category: 'Notes'
draft: false 
lang: 'cn'
---

<style>
p {
  line-height: 1.5;
}
</style>

> 该笔记主要参考《电磁学与电动力学（下册）》（胡秋友 程福臻），以及《电动力学》（郭硕鸿）。

# 第0章 数学准备

# 第1章 电磁现象的基本规律

## 1.1电磁场的数学描述

### 1.1.1 麦克斯韦方程组

+ 电磁场用电场强度矢量$\bm{E}(\bm{r},t)$和磁场强度矢量$\bm{B}(\bm{r},t)$描述，它们满足
  
  $$\nabla \times \bm{E} = - \frac{\partial{\bm{B}}}{\partial{t}}$$

  $$\nabla \cdot \bm{E} = \frac{\rho}{\varepsilon_0}$$

  $$\nabla \times \bm{B} = \mu_0 \bm{j} + \varepsilon_0 \mu_0 \frac{\partial{\bm{E}}}{\partial{t}}$$
  
  $$\nabla \cdot \bm{B} = 0$$

  其中，$\varepsilon_0$和$\mu_0$分别为真空介电常数和真空磁导率；$\rho$为电荷密度，$\bm{j}$为电流密度。
  
### 1.1.2 关于场源

+ 称$\rho$与$\bm{j}$为场源，给定场源可唯一确定电磁场分布。由电荷守恒，两场源间有约束关系

  $$\frac{\partial}{\partial{t}} \iiint \rho dV = - \iint \bm{j} \cdot d\bm{S}$$

  可得

  $$\frac{\partial{\rho}}{\partial{t}} + \nabla \cdot \bm{j} = 0$$

  上式成为电荷守恒方程。

### 1.1.3 电磁性能方程

+ 在介质中，通常讲场源分为两个部分：自由电荷$\rho_0$和束缚电荷$\rho'$，以及它们运动产生的传导电流$\bm{j_0}$和束缚电流$\bm{j'}$，即

  $$\rho = \rho_0 + \rho'$$

  $$\bm{j} = \bm{j_0} + \bm{j'}$$

  两个部分分别满足电荷守恒方程，即

  $$\frac{\partial{\rho_0}}{\partial{t}} + \nabla \cdot \bm{j_0} = 0$$

  $$\frac{\partial{\rho'}}{\partial{t}} + \nabla \cdot \bm{j'} = 0$$

+ 引入极化强度$\bm{P}$与磁化强度$\bm{M}$用以分别对束缚电荷和舒服电流进行宏观描述。二者与场源有如下关系：

  $$\rho' = - \nabla \cdot \bm{P}$$

  $$\bm{j'} = \nabla \times \bm{M} + \frac{\partial{\bm{P}}}{\partial{t}}$$

  类似于麦克斯韦方程组的其中两项，其中$\partial{\bm{P}} / \partial{t}$称之为极化电流，$\nabla \cdot \bm{P}$则称为磁化电流。代入麦克斯韦方程组后得

  $$\nabla \cdot \bm{D} = \rho_0$$

  $$\nabla \times \bm{H} = \bm{j_0} + \frac{\partial{\bm{D}}}{\partial{t}}$$

  其中

  $$\bm{D} = \varepsilon_0 \bm{E} + \bm{P}$$

  $$\bm{H} = \frac{1}{\mu_0} \bm{B} - \bm{M}$$

  为辅助矢量，分别成为电位移矢量和磁场强度。对于宏观静止的均匀介质有

  $$\bm{D} = \varepsilon \bm{E}, ~~~~ \bm{H} = \frac{1}{\mu} \bm{B}$$

  其中，$\varepsilon$为介电常数，$\mu$是磁导率。引入辅助矢量后，麦克斯韦方程组可被改写为

  $$\nabla \times \bm{E} = - \frac{\partial{\bm{B}}}{\partial{t}}$$

  $$\nabla \cdot \bm{D} = \rho_0$$

  $$\nabla \times \bm{H} = \bm{j_0} + \frac{\partial{\bm{D}}}{\partial{t}}$$
  
  $$\nabla \cdot \bm{B} = 0$$

### 1.1.4 导体中的自由电荷和传导电流

+ 对各向同性导体内部，传到电流和电场之间满足欧姆定律

  $$\bm{j_0} = \sigma \bm{E}$$

  其中$\sigma$为电导率。对于稳恒电场情况，带入电荷守恒方程得(假设$\varepsilon = \varepsilon_0$)

  $$\frac{\partial{\rho_0}}{\partial{t}} + \sigma \nabla \cdot \bm{E} = \frac{\partial{\rho_0}}{\partial{t}} + \frac{\sigma}{\varepsilon_0} \rho_0 = 0$$

  解得

  $$\rho_0(\bm{r},t) = \rho_0(\bm{r}) e^{-t / \tau}, ~~~~ \tau = \varepsilon_0 / \sigma$$

  其中，$\rho_0(\bm{r})$为初始自由电荷密度分布。上式表面，导体中的自由电荷密度将随时间指数衰减。对稳恒电场情况，平衡时导体内无自由电荷分布，电荷值分布于导体表面。

+ 对于交变电磁场情况将在后续章节中讨论。

## 1.2 边值关系

+ 假设介质边界上的法向量为$\bm{n}$(由介质1指向介质2)，麦克斯韦方程对边界处做出了以下要求

  $$\bm{n} \cdot (\bm{B_2} - \bm{B_1}) = 0$$

  $$\bm{n} \times (\bm{E_2} - \bm{E_1}) = 0$$

  $$\bm{n} \cdot (\bm{D_2} - \bm{D_1}) = \sigma_0$$

  $$\bm{n} \times (\bm{H_2} - \bm{H_1}) = \bm{i_0}$$

  其中$\sigma_0$为自由电荷面密度，$i_0$为传导电流面密度

## 1.3 电磁场的能量、动量和角动量

### 1.3.1 电磁场对带电体的力和功率

+ 微观上，在电荷密度为$\rho$,电流密度为$\bm{j}$处的电磁作用力密度$\bm{f}$可以表示为

  $$\bm{f} = \rho \bm{E} + \bm{j} \times \bm{B}$$

  电磁力的功率密度为

  $$p = \bm{f} \cdot \bm{v} = \bm{j} \cdot \bm{E} ~~~~ \bm{v}与\bm{j}同向$$ 

  可见仅有电场对运动的电荷做工，且不区分场源种类。

### 1.3.2 电磁场的能量及能量守恒定理

+ 根据麦克斯韦方程组，可得
  
  $$\bm{j} = \frac{1}{\mu_0} \nabla \times \bm{B} - \varepsilon_0 \frac{\partial{\bm{E}}}{\partial{t}}$$

  于是可将功率密度化为

  $$
  \begin{align*}
  \bm{j} \cdot \bm{E} &= \frac{1}{\mu_0} (\nabla \times \bm{B}) \cdot \bm{E} - \varepsilon_0 \frac{\partial{\bm{E}}}{\partial{t}} \cdot \bm{E}\\
  &= \frac{1}{\mu_0} \nabla \cdot (\bm{B} \times \bm{E}) + \frac{1}{\mu_0} (\nabla \times \bm{E}) \cdot \bm{B} - \varepsilon_0 \frac{\partial{\bm{E}}}{\partial{t}} \cdot \bm{E}\\
  &= - \frac{1}{\mu_0} \nabla \cdot (\bm{E} \times \bm{B}) - \frac{\partial}{\partial{t}} (\frac{\varepsilon_0 E^2}{2} + \frac{B^2}{2 \mu_0})\\
  &= - \nabla \cdot \bm{S} - \frac{\partial{\mathcal{w}}}{\partial{t}}
  \end{align*}
  $$

  其中

  $$\bm{S} = \frac{1}{\mu_0} \bm{E} \times \bm{B}, ~~~~ \mathcal{w} = \frac{\varepsilon_0 E^2}{2} + \frac{B^2}{2 \mu_0}$$

  分别称为电磁能流密度(坡印廷矢量)和电磁能量密度。将上式改写为

  $$- \frac{\partial{\mathcal{w}}}{\partial{t}} = \nabla \cdot \bm{S} + \bm{j} \cdot \bm{E}$$

  称之为电磁场能量守恒定理，又称为坡印廷定理。物理含义为：单位体积、单位时间内电磁场能量的减小量等于单位时间内流出的电磁能量与对带电体做功之和。

  
### 1.3.3 电磁场对带电体的力和功率小结

+ 电磁场同样存在动量和角动量以及它们的守恒定律，限于篇幅不再推导，后续将以表格形式展示。

  |                  | 真空中                                                                                              | 辅助矢量形式 （满足$D_i = \varepsilon_{ij} E_i ~~~~ B_i = \mu_{ij} H_i$）           |
  | :--------------- | :-------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------- |
  | 电磁能量密度     | $\mathcal{w} = \frac{1}{2} \varepsilon_0 E^2 + \frac{1}{2} \frac{B^2}{\mu_0}$                       | $\mathcal{w_0} = \frac{1}{2} \bm{D} \cdot \bm{E} + \frac{1}{2} \bm{B} \cdot \bm{H}$ |
  | 电磁能流密度     | $\bm{S} = \frac{1}{\mu_0} \bm{E} \times \bm{B}$                                                     | $\bm{S_0} = \bm{E} \times \bm{H}$                                                   |
  | 电磁动量密度     | $\bm{g} = \varepsilon_0 \bm{E} \times \bm{B}$                                                       | $\bm{g_0} = \bm{D} \times \bm{B}$                                                   |
  | 电磁动量流密度   | $\mathbf{T} = \mathcal{w} \mathbf{I} - \varepsilon_0 \bm{E} \bm{E} - \frac{1}{\mu_0} \bm{B} \bm{B}$ | $\mathbf{T_0} = \mathcal{w_0} \mathbf{I} - \bm{D} \bm{E} - \bm{B} \bm{H}$           |
  | 电磁角动量密度   | $\bm{l} = \bm{r} \times \bm{g}$                                                                     | $\bm{l_0} = \bm{r} \times \bm{g_0}$                                                 |
  | 电磁角动量流密度 | $\mathbf{R} = - \mathbf{T} \times \bm{r}$                                                           | $\mathbf{R_0} = - \mathbf{T_0} \times \bm{r}$                                       |

+ 守恒关系

  |            | 守恒定理                                                                                  |
  | :--------- | :---------------------------------------------------------------------------------------- |
  | 能量守恒   | $- \frac{\partial{\mathcal{w}}}{\partial{t}} = \nabla \cdot \bm{S} + \bm{j} \cdot \bm{E}$ |
  | 动量守恒   | $- \frac{\partial{\bm{g}}}{\partial{t}} = \nabla \cdot \mathbf{T} + \bm{f}$               |
  | 角动量守恒 | $- \frac{\partial{\bm{l}}}{\partial{t}} = \nabla \cdot \mathbf{R} + \bm{r} \times \bm{f}$ |