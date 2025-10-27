---
title: 电动力学
published: 2025-09-19
description: ''
image: '../../assets/covers/studying.png'
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

# 第1章 电磁现象的基本规律

## 1.1电磁场的数学描述

### 1.1.1 麦克斯韦方程组

+ 电磁场用电场强度矢量$\bm{E}(\bm{r},t)$和磁场强度矢量$\bm{B}(\bm{r},t)$描述，它们满足
  
  $$
  \nabla \times \bm{E} = - \frac{\partial{\bm{B}}}{\partial{t}}
  $$

  $$
  \nabla \cdot \bm{E} = \frac{\rho}{\varepsilon_0}
  $$

  $$
  \nabla \times \bm{B} = \mu_0 \bm{j} + \varepsilon_0 \mu_0 \frac{\partial{\bm{E}}}{\partial{t}}
  $$
  
  $$
  \nabla \cdot \bm{B} = 0
  $$

  其中，$\varepsilon_0$和$\mu_0$分别为真空介电常数和真空磁导率；$\rho$为电荷密度，$\bm{j}$为电流密度。
  
### 1.1.2 关于场源

+ 称$\rho$与$\bm{j}$为场源，给定场源可唯一确定电磁场分布。由电荷守恒，两场源间有约束关系

  $$
  \frac{\partial}{\partial{t}} \iiint \rho dV = - \iint \bm{j} \cdot d\bm{S}
  $$

  可得

  $$
  \frac{\partial{\rho}}{\partial{t}} + \nabla \cdot \bm{j} = 0
  $$

  上式成为电荷守恒方程。

### 1.1.3 电磁性能方程

+ 在介质中，通常讲场源分为两个部分：自由电荷$\rho_0$和束缚电荷$\rho'$，以及它们运动产生的传导电流$\bm{j}_0$和束缚电流$\bm{j}'$，即

  $$
  \rho = \rho_0 + \rho'
  $$

  $$
  \bm{j} = \bm{j}_0 + \bm{j}'
  $$

  两个部分分别满足电荷守恒方程，即

  $$
  \frac{\partial{\rho_0}}{\partial{t}} + \nabla \cdot \bm{j}_0 = 0
  $$

  $$
  \frac{\partial{\rho'}}{\partial{t}} + \nabla \cdot \bm{j}' = 0
  $$

+ 引入极化强度$\bm{P}$与磁化强度$\bm{M}$用以分别对束缚电荷和舒服电流进行宏观描述。二者与场源有如下关系：

  $$
  \rho' = - \nabla \cdot \bm{P}
  $$

  $$
  \bm{j}' = \nabla \times \bm{M} + \frac{\partial{\bm{P}}}{\partial{t}}
  $$

  类似于麦克斯韦方程组的其中两项，其中$\partial{\bm{P}} / \partial{t}$称之为极化电流，$\nabla \cdot \bm{P}$则称为磁化电流。代入麦克斯韦方程组后得

  $$
  \nabla \cdot \bm{D} = \rho_0
  $$

  $$
  \nabla \times \bm{H} = \bm{j}_0 + \frac{\partial{\bm{D}}}{\partial{t}}
  $$

  其中

  $$
  \bm{D} = \varepsilon_0 \bm{E} + \bm{P}
  $$

  $$
  \bm{H} = \frac{1}{\mu_0} \bm{B} - \bm{M}
  $$

  为辅助矢量，分别成为电位移矢量和磁场强度。对于宏观静止的均匀介质有

  $$
  \bm{D} = \varepsilon \bm{E}, ~~~~ \bm{H} = \frac{1}{\mu} \bm{B}
  $$

  其中，$\varepsilon$为介电常数，$\mu$是磁导率。引入辅助矢量后，麦克斯韦方程组可被改写为

  $$
  \nabla \times \bm{E} = - \frac{\partial{\bm{B}}}{\partial{t}}
  $$

  $$
  \nabla \cdot \bm{D} = \rho_0
  $$

  $$
  \nabla \times \bm{H} = \bm{j}_0 + \frac{\partial{\bm{D}}}{\partial{t}}
  $$

  $$
  \nabla \cdot \bm{B} = 0
  $$

### 1.1.4 导体中的自由电荷和传导电流

+ 对各向同性导体内部，传到电流和电场之间满足欧姆定律

  $$
  \bm{j}_0 = \sigma \bm{E}
  $$

  其中$\sigma$为电导率。对于稳恒电场情况，带入电荷守恒方程得(假设$\varepsilon = \varepsilon_0$)

  $$
  \frac{\partial{\rho_0}}{\partial{t}} + \sigma \nabla \cdot \bm{E} = \frac{\partial{\rho_0}}{\partial{t}} + \frac{\sigma}{\varepsilon_0} \rho_0 = 0
  $$

  解得

  $$
  \rho_0(\bm{r},t) = \rho_0(\bm{r}) e^{-t / \tau}, ~~~~ \tau = \varepsilon_0 / \sigma
  $$

  其中，$\rho_0(\bm{r})$为初始自由电荷密度分布。上式表面，导体中的自由电荷密度将随时间指数衰减。对稳恒电场情况，平衡时导体内无自由电荷分布，电荷值分布于导体表面。

+ 对于交变电磁场情况将在后续章节中讨论。

## 1.2 边值关系

+ 假设介质边界上的法向量为$\bm{n}$(由介质1指向介质2)，麦克斯韦方程对边界处做出了以下要求

  $$
  \bm{n} \cdot (\bm{B}_2 - \bm{B_1}) = 0
  $$

  $$
  \bm{n} \times (\bm{E}_2 - \bm{E}_1) = 0
  $$

  $$
  \bm{n} \cdot (\bm{D}_2 - \bm{D_1}) = \sigma_0
  $$

  $$
  \bm{n} \times (\bm{H}_2 - \bm{H_1}) = \bm{i}_0
  $$

  其中$\sigma_0$为自由电荷面密度，$i_0$为传导电流面密度

## 1.3 电磁场的能量、动量和角动量

### 1.3.1 电磁场对带电体的力和功率

+ 微观上，在电荷密度为$\rho$,电流密度为$\bm{j}$处的电磁作用力密度$\bm{f}$可以表示为

  $$
  \bm{f} = \rho \bm{E} + \bm{j} \times \bm{B}
  $$

  电磁力的功率密度为

  $$
  p = \bm{f} \cdot \bm{v} = \bm{j} \cdot \bm{E} ~~~~ \bm{v}与\bm{j}同向
  $$ 

  可见仅有电场对运动的电荷做工，且不区分场源种类。

### 1.3.2 电磁场的能量及能量守恒定理

+ 根据麦克斯韦方程组，可得
  
  $$
  \bm{j} = \frac{1}{\mu_0} \nabla \times \bm{B} - \varepsilon_0 \frac{\partial{\bm{E}}}{\partial{t}}
  $$

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

  $$
  \bm{S} = \frac{1}{\mu_0} \bm{E} \times \bm{B}, ~~~~ \mathcal{w} = \frac{\varepsilon_0 E^2}{2} + \frac{B^2}{2 \mu_0}
  $$

  分别称为电磁能流密度(坡印廷矢量)和电磁能量密度。将上式改写为

  $$
  - \frac{\partial{\mathcal{w}}}{\partial{t}} = \nabla \cdot \bm{S} + \bm{j} \cdot \bm{E}
  $$

  称之为电磁场能量守恒定理，又称为坡印廷定理。物理含义为：单位体积、单位时间内电磁场能量的减小量等于单位时间内流出的电磁能量与对带电体做功之和。

  
### 1.3.3 电磁场对带电体的力和功率小结

+ 电磁场同样存在动量和角动量以及它们的守恒定律，限于篇幅不再推导，后续将以表格形式展示。

  |                  | 真空中                                                                                              | 辅助矢量形式 （满足$D_i = \varepsilon_{ij} E_j ~~~ B_i = \mu_{ij} H_j$）            |
  | :--------------- | :-------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------- |
  | 电磁能量密度     | $\mathcal{w} = \frac{1}{2} \varepsilon_0 E^2 + \frac{1}{2} \frac{B^2}{\mu_0}$                       | $\mathcal{w}_0 = \frac{1}{2} \bm{D} \cdot \bm{E} + \frac{1}{2} \bm{B} \cdot \bm{H}$ |
  | 电磁能流密度     | $\bm{S} = \frac{1}{\mu_0} \bm{E} \times \bm{B}$                                                     | $\bm{S}_0 = \bm{E} \times \bm{H}$                                                   |
  | 电磁动量密度     | $\bm{g} = \varepsilon_0 \bm{E} \times \bm{B}$                                                       | $\bm{g}_0 = \bm{D} \times \bm{B}$                                                   |
  | 电磁动量流密度   | $\mathbf{T} = \mathcal{w} \mathbf{I} - \varepsilon_0 \bm{E} \bm{E} - \frac{1}{\mu_0} \bm{B} \bm{B}$ | $\mathbf{T}_0 = \mathcal{w}_0 \mathbf{I} - \bm{D} \bm{E} - \bm{B} \bm{H}$           |
  | 电磁角动量密度   | $\bm{l} = \bm{r} \times \bm{g}$                                                                     | $\bm{l}_0 = \bm{r} \times \bm{g}_0$                                                 |
  | 电磁角动量流密度 | $\mathbf{R} = - \mathbf{T} \times \bm{r}$                                                           | $\mathbf{R}_0 = - \mathbf{T}_0 \times \bm{r}$                                       |

+ 守恒关系

  |            | 守恒定理                                                                                  |
  | :--------- | :---------------------------------------------------------------------------------------- |
  | 能量守恒   | $- \frac{\partial{\mathcal{w}}}{\partial{t}} = \nabla \cdot \bm{S} + \bm{j} \cdot \bm{E}$ |
  | 动量守恒   | $- \frac{\partial{\bm{g}}}{\partial{t}} = \nabla \cdot \mathbf{T} + \bm{f}$               |
  | 角动量守恒 | $- \frac{\partial{\bm{l}}}{\partial{t}} = \nabla \cdot \mathbf{R} + \bm{r} \times \bm{f}$ |

&nbsp;

&nbsp;

&nbsp;

# 第2章 静电场

## 2.1 静电场的基本方程

### 2.1.1 基本方程

+ 静电场的基本方程为

  $$
  \nabla \times \bm{E} = 0
  $$

  $$
  \nabla \cdot \bm{D} = \rho_0
  $$

  $$
  \bm{D} = \varepsilon \bm{E}
  $$

  其中$\bm{E}$为电场强度，$\bm{D}$为电位移，$\rho_0$为自由电荷密度，$\varepsilon$为介电常数。各区域的介电常数均匀，但不同区域的介电常数可取不同数值。

### 2.1.2 静电势及其微分方程

+ 由于静电场$\bm{E}$为无旋场，可将其表示为某个标量场$\varphi$的梯度，即

  $$
  \bm{E} = - \nabla \varphi
  $$

  其中$\varphi$为静电势。代入基本方程可得

  $$
  \nabla^2 \varphi = - \frac{\rho_0}{\varepsilon}
  $$

  上式称为泊松方程。若$\rho_0 = 0$，则称之为拉普拉斯方程。

### 2.1.3 边值关系

+ 将1.2节中的边值关系等价地转化为电势$\varphi$的边值条件

  $$
  \varphi_2 = \varphi_1
  $$

  $$
  \varepsilon_1 \frac{\partial{\varphi_1}}{\partial{n}} - \varepsilon_2 \frac{\partial{\varphi_2}}{\partial{n}} = \sigma_0
  $$

### 2.1.4 定解条件

+ 在给定求解区域$V$的自由电荷分布和介电常数分布后，还需要加上适当的约束条件，才能保证静电场的解存在且唯一。这些条件被称为定解条件，解的唯一性有数学保障。

  1. **第一类边值条件**：在边界上给定电势$\varphi$的值。

    $$
    \left.{\varphi} \right|_{\partial V} = f(\bm{r})
    $$

  2. **第二类边值条件**：在边界上给定电势$\varphi$的法向导数。

    $$
    \left.{\frac{\partial{\varphi}}{\partial{n}}} \right|_{\partial V} = g(\bm{r})
    $$

  3. **第三类边值条件**：在边界上给定电势$\varphi$的线性组合。

    $$
    \left.{(\alpha \varphi + \beta \frac{\partial{\varphi}}{\partial{n}})} \right|_{\partial V} = h(\bm{r})
    $$

  4. **无穷远处电势条件**：当求解区域为无限大时，相应边界条件为无限远处的渐进条件。

  5. **解域内存在导体**：对给定电势的导体，其各处电势均为给定常数。对给定电量的导体，其满足
  
    $$
    \oiint_S \varepsilon \frac{\partial{\varphi}}{\partial{n}} dS = Q
    $$

    其中$S$为导体表面，$Q$为导体电量。导体内部视为解域外部，$n$为法向量，由解域指向导体内部。

## 2.2 分离变量法

### 2.2.1 由泊松方程到拉普拉斯方程

+ 我们需要求解的方程为电势$\varphi'$所满足的泊松方程和对应的定解条件

  $$
  \nabla^2 \varphi' = - \frac{\rho_0}{\varepsilon}
  $$

  $$
  \left.{(\alpha \varphi' + \beta \frac{\partial{\varphi'}}{\partial{n}})} \right|_{\partial V} = f(\bm{r})
  $$

  方程为线性方程，可将解$\varphi$分为两部分，令$\varphi' = \varphi_0 + \varphi$，其中$\varphi_0$满足

  $$
  \nabla^2 \varphi_0 = - \frac{\rho_0}{\varepsilon}
  $$

  无论边界条件为何，$\varphi_0$均可由电磁学结果给出

  $$
  \varphi_0(\bm{r}) = \frac{1}{4 \pi \varepsilon} \iiint_V \frac{\rho_0(\bm{r}')}{|\bm{r} - \bm{r}'|} dV'
  $$
  
  $\varphi$满足

  $$
  \nabla^2 \varphi = 0
  $$

  其边值条件为

  $$
  \left.{(\alpha \varphi + \beta \frac{\partial{\varphi}}{\partial{n}})} \right|_{\partial V} = f(\bm{r}) - \left.{(\alpha \varphi_0 + \beta \frac{\partial{\varphi_0}}{\partial{n}})} \right|_{\partial V}
  $$

  由此可见，$\varphi$满足拉普拉斯方程及其边值条件。由于拉普拉斯方程的解唯一性，$\varphi$可唯一确定。

### 2.2.2 直角坐标下的分离变量解

+ 在直角坐标系下，拉普拉斯方程为：
  $$
  \frac{\partial^2{\varphi}}{\partial{x^2}} + \frac{\partial^2{\varphi}}{\partial{y^2}} + \frac{\partial^2{\varphi}}{\partial{z^2}} = 0
  $$

  假设解可表示为各变量的乘积形式：

  $$
  \varphi(x,y,z) = X(x) Y(y) Z(z)
  $$

  代入方程并分离变量后，我们得到三个独立的常微分方程。通常，我们根据边界条件的周期性来选择分离常数的符号。例如，如果在 x 和 y 方向上是周期性边界，我们设：

  $$
  \frac{1}{X} \frac{d^2{X}}{dx^2} = -k_x^2, \quad \frac{1}{Y} \frac{d^2{Y}}{dy^2} = -k_y^2, \quad \frac{1}{Z} \frac{d^2{Z}}{dz^2} = k_z^2
  $$

  其中分离常数必须满足关系：

  $$
  -k_x^2 - k_y^2 + k_z^2 = 0 \quad \implies \quad k_z = \sqrt{k_x^2 + k_y^2}
  $$

  各个方向上方程的通解为：

  $$
  X(x) = A_x e^{ik_x x} + B_x e^{-ik_x x} \quad (\text{或 } A_x \cos(k_x x) + B_x \sin(k_x x))
  $$

  $$
  Y(y) = A_y e^{ik_y y} + B_y e^{-ik_y y} \quad (\text{或 } A_y \cos(k_y y) + B_y \sin(k_y y))
  $$

  $$
  Z(z) = A_z e^{k_z z} + B_z e^{-k_z z} \quad (\text{或 } A_z \cosh(k_z z) + B_z \sinh(k_z z))
  $$

  其中 $k_x$ 和 $k_y$ 的值由边界条件决定，它们可能是一系列离散的本征值，我们用 $k_{xn}$ 和 $k_{ym}$ 表示。

  因此，拉普拉斯方程的通解是这些分离变量解的线性叠加：

  $$
  \varphi(x,y,z) = \sum_{n,m} X_{n}(x) Y_{m}(y) Z_{nm}(z)
  $$

  其中 $X_n(x)$, $Y_m(y)$ 和 $Z_{nm}(z)$ 是对应于本征值 $k_{xn}$ 和 $k_{ym}$ 的解。系数由边界条件通过傅里叶分析等方法确定。

### 2.2.3 柱坐标下的分离变量解

+ 在柱坐标系 $(\rho, \phi, z)$ 下，拉普拉斯方程为：
+ 
  $$
  \frac{1}{\rho} \frac{\partial}{\partial{\rho}} \left(\rho \frac{\partial{\varphi}}{\partial{\rho}}\right) + \frac{1}{\rho^2} \frac{\partial^2{\varphi}}{\partial{\phi^2}} + \frac{\partial^2{\varphi}}{\partial{z^2}} = 0
  $$

  设解的形式为 $\varphi(\rho, \phi, z) = R(\rho) \Phi(\phi) Z(z)$，分离变量后得到三个常微分方程：

  $$
  \frac{d^2{Z}}{dz^2} - k^2 Z = 0
  $$

  $$
  \frac{d^2{\Phi}}{d\phi^2} + m^2 \Phi = 0
  $$

  $$
  \frac{d^2{R}}{d\rho^2} + \frac{1}{\rho} \frac{d{R}}{d\rho} + \left(k^2 - \frac{m^2}{\rho^2}\right) R = 0
  $$

  这里 $k^2$ 和 $m^2$ 是分离常数。为了保证解在绕 z 轴旋转 $2\pi$ 后是单值的，**$m$ 必须是整数**。

  上述方程的通解分别为：

  *   $Z(z)$ 的解是指数函数或三角函数，取决于 $k$ 是实数还是虚数：
     
      $$
      Z(z) = A e^{kz} + B e^{-kz}
      $$

  *   $\Phi(\phi)$ 的解是三角函数：
    
      $$
      \Phi(\phi) = C \cos(m\phi) + D \sin(m\phi) \quad (\text{或 } C e^{im\phi} + D e^{-im\phi})
      $$

  *   $R(\rho)$ 的解是 **$m$ 阶贝塞尔函数**。如果 $k$ 是实数，方程为标准的贝塞尔方程，解为：
     
      $$
      R(\rho) = E J_m(k\rho) + F Y_m(k\rho)
      $$

      其中 $J_m$ 是第一类贝塞尔函数，$Y_m$（或记作 $N_m$）是第二类贝塞尔函数（诺依曼函数），它在 $\rho=0$ 处是奇异的。

  最终，电势的通解是这些特解的线性叠加：

  $$
  \varphi(\rho, \phi, z) = \sum_{m,k} (E_{mk} J_m(k\rho) + F_{mk} Y_m(k\rho)) (C_m \cos(m\phi) + D_m \sin(m\phi)) (A_k e^{kz} + B_k e^{-kz})
  $$

  其中求和是对所有满足边界条件的本征值 $m$ 和 $k$ 进行的。

+ 轴对称情况（与 $\phi$ 无关）
  当问题具有轴对称性时，电势与角 $\phi$ 无关，这意味着分离常数 $m=0$。此时方程简化为：
  *   $\Phi(\phi)$ 是一个常数。
  *   $R(\rho)$ 的方程变为 **0 阶贝塞尔方程**，解为：
      $$
      R(\rho) = E J_0(k\rho) + F Y_0(k\rho)
      $$
  *   特别地，如果电势也与 $z$ 无关（$k=0$），$R(\rho)$ 的方程变为 $\frac{1}{\rho} \frac{d}{d\rho}(\rho \frac{dR}{d\rho}) = 0$，其解为：
      $$
      \varphi(\rho) = A \ln \rho + B
      $$
      这对应于无限长直导线的电势。

### 2.2.4 球坐标下的分离变量解

+ 在球坐标系 $(r, \theta, \phi)$ 下，拉普拉斯方程为：
  
  $$
  \frac{1}{r^2} \frac{\partial}{\partial{r}} \left(r^2 \frac{\partial{\varphi}}{\partial{r}}\right) + \frac{1}{r^2 \sin{\theta}} \frac{\partial}{\partial{\theta}} \left(\sin{\theta} \frac{\partial{\varphi}}{\partial{\theta}}\right) + \frac{1}{r^2 \sin^2{\theta}} \frac{\partial^2{\varphi}}{\partial{\phi^2}} = 0
  $$

  设解的形式为 $\varphi(r, \theta, \phi) = R(r) P(\theta) \Phi(\phi)$，分离变量后得到：

  1.  **径向方程**:
    
      $$
      \frac{d}{dr} \left(r^2 \frac{dR}{dr}\right) - l(l+1)R = 0
      $$

  2.  **角向方程**:
    
      $$
      \frac{1}{\sin\theta} \frac{d}{d\theta} \left(\sin\theta \frac{dP}{d\theta}\right) + \left(l(l+1) - \frac{m^2}{\sin^2\theta}\right)P = 0
      $$

      $$
      \frac{d^2\Phi}{d\phi^2} + m^2\Phi = 0
      $$

  其中分离常数被写为 $l(l+1)$ 和 $m^2$。为了保证解的物理意义（在极点处有限且在绕轴旋转后单值），**$l$ 必须为非负整数**，**$m$ 为整数且满足 $|m| \le l$**。

  这些方程的通解是众所周知的：

  1.  $R(r)$ 的解是幂函数：
     
      $$
      R_l(r) = A_l r^l + B_l r^{-(l+1)}
      $$
      
  2.  $P(\theta)$ 的解是 **连带勒让德函数**：
      
      $$
      P_l^m(\cos\theta)
      $$

  3.  $\Phi(\phi)$ 的解是三角函数：
      
      $$
      \Phi_m(\phi) = C_m \cos(m\phi) + D_m \sin(m\phi)
      $$
  
  通常将两个角向的解合并为 **球谐函数** $Y_{lm}(\theta, \phi) \propto P_l^m(\cos\theta) e^{im\phi}$。

  最终，电势的通解是这些特解的线性叠加：
  
  $$
  \varphi(r, \theta, \phi) = \sum_{l=0}^{\infty} \sum_{m=-l}^{l} \left(A_{lm} r^l + \frac{B_{lm}}{r^{l+1}}\right) Y_{lm}(\theta, \phi)
  $$
  
  系数 $A_{lm}$ 和 $B_{lm}$ 由边界条件确定。

+ 轴对称情况（与 $\phi$ 无关）

  当问题具有关于 z 轴的旋转对称性时，电势与角 $\phi$ 无关，这意味着只有 $m=0$ 的项有贡献。

  1. 此时，连带勒让德函数 $P_l^m(\cos\theta)$ 简化为 **$l$ 阶勒让德多项式** $P_l(\cos\theta)$。

  2. 球谐函数 $Y_{l0}$ 正比于 $P_l(\cos\theta)$。

  因此，轴对称情况下拉普拉斯方程的通解简化为：

  $$
  \varphi(r, \theta) = \sum_{l=0}^{\infty} \left(A_l r^l + \frac{B_l}{r^{l+1}}\right) P_l(\cos\theta)
  $$

  这是一个在处理电偶极子、均匀外电场中的导体/介质球等问题时非常有用的形式。

## 2.3 格林函数法

### 2.3.1 格林函数

+ 定义格林函数$G(\bm{r},\bm{r}')$为满足

  $$
  \nabla^2 G(\bm{r},\bm{r}') = - \frac{1}{\varepsilon} \delta(\bm{r} - \bm{r}')
  $$

  和相应边值条件的函数。

  1. 若满足第一类边值条件

    $$
    \left.{G(\bm{r},\bm{r}')} \right|_{\partial V} = 0
    $$

    则称之为第一类格林函数。

  2. 若满足第二类边值条件
    $$
    \left.{\frac{\partial{G(\bm{r},\bm{r}')}}{\partial{n}}} \right|_{\partial V} = 0
    $$

    则称之为第二类格林函数。

  其物理意义为：在边界上满足相应边值条件的、位于$\bm{r}'$处的单位点电荷在解域内产生的电势。

+ 格林函数的对称性

  $$
  G(\bm{r},\bm{r}') = G(\bm{r}',\bm{r})
  $$

  证明如下。由第二格林公式

  $$
  \iiint_V (\psi \nabla^2 \varphi - \varphi \nabla^2 \psi) dV = \oiint_{\partial V} (\psi \frac{\partial{\varphi}}{\partial{n}} - \varphi \frac{\partial{\psi}}{\partial{n}}) dS
  $$

  取$\psi = G(\bm{r},\bm{r}'), \varphi = G(\bm{r},\bm{r}'')$，则有

  $$
  \begin{align*}
  \text{左边} &= \iiint_V [G(\bm{r},\bm{r}') \nabla^2 G(\bm{r},\bm{r}'') - G(\bm{r},\bm{r}'') \nabla^2 G(\bm{r},\bm{r}')] dV \\ &= - \frac{1}{\varepsilon} \iiint_V [G(\bm{r},\bm{r}') \delta(\bm{r} - \bm{r}'') - G(\bm{r},\bm{r}'') \delta(\bm{r} - \bm{r}')] dV \\ &= - \frac{1}{\varepsilon} [G(\bm{r}'',\bm{r}') - G(\bm{r}',\bm{r}'')]
  \end{align*}
  $$

  由边值条件可得

  $$
  \text{右边} = \oiint_{\partial V} [G(\bm{r},\bm{r}') \frac{\partial{G(\bm{r},\bm{r}'')}}{\partial{n}} - G(\bm{r},\bm{r}'') \frac{\partial{G(\bm{r},\bm{r}')}}{\partial{n}}] dS = 0
  $$

  故有$G(\bm{r}'',\bm{r}') = G(\bm{r}',\bm{r}'')$, 得证。格林函数的对称性体现了电磁学的互易定理。

### 2.3.2 格林函数法

+ 由格林函数的对称性，将2.3.1节中定义的格林函数的$\bm{r}$与$\bm{r}'$对调，同时将微分算符由$\nabla^2$改为$\nabla'^2$，两者分别仅作用在$\bm{r}$与$\bm{r}'$上，则有

  $$
  \nabla'^2 G(\bm{r}',\bm{r}) = - \frac{1}{\varepsilon} \delta(\bm{r}' - \bm{r})
  $$

  $$
  \left.{G(\bm{r}',\bm{r})} \right|_{\partial V} = 0
  $$

  $$
   \left.{\frac{\partial G(\bm{r}',\bm{r})}{\partial{n'}}} \right|_{\partial V} = 0
  $$

  设$\varphi(\bm{r})$为待求解的电势，将第二格林公式写为

  $$
  \iiint_V [G(\bm{r}',\bm{r}) \nabla'^2 \varphi(\bm{r}') - \varphi(\bm{r}') \nabla'^2 G(\bm{r}',\bm{r})] dV' = \oiint_{\partial V} [G(\bm{r}',\bm{r}) \frac{\partial{\varphi(\bm{r}')}}{\partial{n'}} - \varphi(\bm{r}') \frac{\partial{G(\bm{r}',\bm{r})}}{\partial{n'}}] dS'
  $$

  对两边进行化简可得

  $$
  \begin{align*}
  \text{左边} &= \frac{1}{\varepsilon} \iiint_V [- G(\bm{r}',\bm{r}) \rho_0(\bm{r}') + \varphi(\bm{r}') \delta(\bm{r}' - \bm{r})] dV' \\ &= \frac{1}{\varepsilon} \varphi(\bm{r}) - \frac{1}{\varepsilon} \iiint_V G(\bm{r}',\bm{r}) \rho_0(\bm{r}') dV'
  \end{align*}
  $$

  右边可写为

  $$
  \text{右边} = \oiint_{\partial V} [G(\bm{r}',\bm{r}) \frac{\partial{\varphi(\bm{r}')}}{\partial{n'}} - \varphi(\bm{r}') \frac{\partial{G(\bm{r}',\bm{r})}}{\partial{n'}}] dS'
  $$

  由此可得

  $$
  \varphi(\bm{r}) = \iiint_V G(\bm{r}',\bm{r}) \rho_0(\bm{r}') dV' + \varepsilon \oiint_{\partial V} [G(\bm{r}',\bm{r}) \frac{\partial{\varphi(\bm{r}')}}{\partial{n'}} - \varphi(\bm{r}') \frac{\partial{G(\bm{r}',\bm{r})}}{\partial{n'}}] dS'
  $$

  上式为电势的形式解，为得到实际的电势解，需要将格林函数的边值条件带入其中。对于第一类边值条件，有

  $$
  \varphi(\bm{r}) = \iiint_V G(\bm{r}',\bm{r}) \rho_0(\bm{r}') dV' - \varepsilon \oiint_{\partial V} \varphi(\bm{r}') \frac{\partial{G(\bm{r}',\bm{r})}}{\partial{n'}} dS'
  $$

  对于第二类边值条件，有

  $$
  \varphi(\bm{r}) = \iiint_V G(\bm{r}',\bm{r}) \rho_0(\bm{r}') dV' + \varepsilon \oiint_{\partial V} G(\bm{r}',\bm{r}) \frac{\partial{\varphi(\bm{r}')}}{\partial{n'}} dS'
  $$

  为了使上式的物理意义更加明确，利用格林函数的对称性，将两类边值条件下的电势解分别改写为

  $$
  \varphi(\bm{r}) = \iiint_V G(\bm{r},\bm{r}') \rho_0(\bm{r}') dV' - \varepsilon \oiint_{\partial V} \varphi(\bm{r}') \frac{\partial{G(\bm{r},\bm{r}')}}{\partial{n'}} dS'
  $$

  $$
  \varphi(\bm{r}) = \iiint_V G(\bm{r},\bm{r}') \rho_0(\bm{r}') dV' + \varepsilon \oiint_{\partial V} G(\bm{r},\bm{r}') \frac{\partial{\varphi(\bm{r}')}}{\partial{n'}} dS'
  $$

  将$\bm{r}$视为待求解处的坐标，$\bm{r}'$视为电荷元和边界上的坐标。上式的物理意义为：电势$\varphi(\bm{r})$等于解域内所有自由电荷在$\bm{r}'$处产生的电势或边界上电势或面电荷密度对$\bm{r}$处产生的电势之和。

## 2.4 多极子电场

### 2.4.1 小带电体静电场的多极展开

+ 在自由空间中，给定电荷密度分布在真空中产生的电势为

  $$
  \varphi(\bm{r}) = \frac{1}{4 \pi \varepsilon_0} \iiint \frac{\rho(\bm{r}')}{R} dV'
  $$

  其中$R = |\bm{r} - \bm{r}'|$。由$R$关于位置矢量$\bm{r}$和$\bm{r}'$的对称性可得

  $$
  \nabla f(R) = - \nabla' f(R)
  $$

  设带电体的空间范围为$V'$，其尺寸远小于观察点$\bm{r}$到带电体的距离$R$，即$r \gg r'$，则可将$1/R$展开到二阶：

  $$
  \begin{align*}
  \frac{1}{R} &\approx \frac{1}{r} + \sum_i x'_i\left(\frac{\partial}{\partial x_i} \frac{1}{R}\right)_{\bm{r}'=0} + \frac{1}{2} \sum_{i,j} x'_i x'_j\left(\frac{\partial^2}{\partial x_i \partial x_j} \frac{1}{R}\right)_{\bm{r}'=0} \\ &= \frac{1}{r} + \bm{r}' \cdot \left(\nabla' \frac{1}{R}\right)_{\bm{r}'=0} + \frac{1}{2} \bm{r}' \bm{r}' : \left(\nabla' \nabla' \frac{1}{R}\right)_{\bm{r}'=0} \\ &= \frac{1}{r} - \bm{r}' \cdot \left(\nabla \frac{1}{r}\right) + \frac{1}{2} \bm{r}' \bm{r}' : \left(\nabla \nabla \frac{1}{r}\right) \\ &= \frac{1}{r} + \frac{\bm{r} \cdot \bm{r}'}{r^3} + \frac{3(\bm{r} \cdot \bm{r}')^2 - r^2 r'^2}{2 r^5}
  \end{align*}
  $$

  将上式代入电势表达式中，可得

  $$
  \varphi(\bm{r}) \approx \frac{1}{4 \pi \varepsilon_0} \left[\frac{Q}{r} - \bm{p} \cdot \nabla \frac{1}{r} + \frac{1}{2} \bm{D'} : \nabla \nabla \frac{1}{r} \right] = \frac{1}{4 \pi \varepsilon_0} \left[\frac{Q}{r} + \frac{\bm{p} \cdot \bm{r}}{r^3} + \frac{1}{2} \frac{\bm{D} : \bm{r} \bm{r}}{r^5} \right]
  $$

  其中

  $$
  Q = \iiint \rho(\bm{r}') dV'
  $$

  $$
  \bm{p} = \iiint \rho(\bm{r}') \bm{r}' dV'
  $$

  $$
  \bm{D'} = \iiint \rho(\bm{r}') \bm{r}' \bm{r}' dV'
  $$

  $$
  \bm{D} = \iiint \rho(\bm{r}') (3 \bm{r}' \bm{r}' - r'^2 \bm{I}) dV'
  $$

  分别称为总电荷(零阶矩)、电偶极矩(一阶矩)、二阶矩和电四极矩。对电势求梯度可得各自产生的电场。

### 2.4.2 电多极子在外电场中所受的力和力矩

+ 带电体在外电场中所受的力的表达式如下

  $$
  \bm{F} = \iiint \rho(\bm{r}') \bm{E}_e dV'
  $$

  将外电场在带电体$\bm{r}_0$附近展开到二阶再代入得

  $$
  \bm{F} \approx Q \bm{E}_e(\bm{r}_0) + \bm{p} \cdot \nabla \bm{E}_e + \frac{1}{2} \bm{D'} : \nabla \nabla \bm{E}_e
  $$

  对于力矩，可以表示为

  $$
  \bm{M} = \iiint \rho(\bm{r}') \bm{r}' \times \bm{E}_e dV'
  $$

  将外电场在带电体$\bm{r}_0$附近展开到一阶再代入得

  $$
  \bm{M} = \bm{p} \times \bm{E}_e + (\bm{D'} \cdot \nabla) \times \bm{E}_e
  $$

## 2.5 静电能

### 2.5.1 静电能基本公式

+ 由1.3.3节中的结论，静电场的能量密度为

  $$
  \mathcal{w} = \frac{1}{2} \bm{E} \cdot \bm{D}
  $$

  又由$D$的定义可得

  $$
  \mathcal{w} = \frac{1}{2} \bm{E} \cdot (\varepsilon_0 \bm{E} + \bm{P}) = \frac{1}{2} \varepsilon_0 E^2 + \frac{1}{2} \bm{E} \cdot \bm{P}
  $$

  第一项为静电能密度，第二项为介质的极化能密度。全空间静电能可表示为

  $$
  \begin{align*}
  W &= \frac{1}{2} \iiint \bm{E} \cdot \bm{D} dV \\ &= - \frac{1}{2} \iiint \nabla \varphi \cdot \bm{D} \\ &= - \frac{1}{2} \iiint \nabla \cdot (\varphi \bm{D}) dV + \frac{1}{2} \iiint \varphi \nabla \cdot \bm{D} dV \\ &= \frac{1}{2} \iiint \rho_0 \varphi dV - \frac{1}{2} \oiint \varphi \bm{D} \cdot d\bm{S}
  \end{align*}
  $$

  由于积分区域为全空间，上式第二项为0，故得

  $$
  W = \frac{1}{2} \iiint \bm{E} \cdot \bm{D} dV = \frac{1}{2} \iiint \rho_0 \varphi dV
  $$

  需注意，$\varphi$为所有电荷产生的总电势，$\rho_0$为自由电荷密度。

### 2.5.2 小带电体在外场中的静电能

+ 设小带电体的空间范围为$V'$，其尺寸远小于外电场变化的空间尺度，在外电场中，其静电能为

  $$
  W_{e} = \iiint \rho_0(\bm{r'}) \varphi_{e} dV'
  $$

  其中$\varphi_{e}$为外电场产生的电势。与2.4.1节中的多极展开类似的，对$\varphi_{e}$展开到二阶可得

  $$
  W_{e} \approx Q \varphi_{e}(\bm{r}_0) + \bm{p} \cdot \nabla \varphi_{e}(\bm{r}_0) + \frac{1}{6} \bm{D} : \nabla \nabla \varphi_{e}(\bm{r}_0) 
  $$

  上式中，第一项为单极矩与外电势的相互作用能，第二项为偶极矩与外电场的相互作用能，第三项为四极矩与外电场梯度的相互作用能。

&nbsp;

&nbsp;

&nbsp;

# 第3章 静磁场

## 3.1 静磁场的基本方程

### 3.1.1 基本方程

+ 静磁场的基本方程为

  $$
  \nabla \times \bm{H} = \bm{j}_0
  $$

  $$
  \nabla \cdot \bm{B} = 0
  $$

  $$
  \bm{B} = \mu \bm{H}
  $$

  其中$\bm{H}$为磁场强度，$\bm{B}$为磁感应强度，$\mu$为磁导率，$\bm{j}_0$为传导电流密度，满足$\nabla \cdot \bm{j}_0 = 0$。各区域的磁导率均匀，但不同区域的磁导率可取不同数值。

### 3.1.2 磁矢势及其微分方程

+ 由于静磁场$\bm{B}$散度为0，可将其表示为某个矢量场$\bm{A}$的旋度，即

  $$
  \bm{B} = \nabla \times \bm{A}
  $$

  其中$\bm{A}$为磁矢势。与电势相比，磁矢势具有更高的自由度，上式仅对其旋度做出要求，未对其散度做出规范，可以有多个不同的磁矢势用于描述同一磁场，它们之间可能存在不同的数学形式。一般为使表达式更加简洁，可以人为引入规范条件，使其数学形式唯一，如

  $$
  \nabla \cdot \bm{A} = 0
  $$

  该规范条件可以极大地简化后续的一些讨论。将以上两式代入基本方程可得

  $$
  \nabla^2 \bm{A} = -\mu \bm{j}_0
  $$

  上式为矢量泊松方程，实际是由三个泊松方程组成的方程组。

+ 磁矢势满足的矢量泊松方程的形式与电势满足的泊松方程形式相似，可以通过类比得到在无限均匀线性各向同性磁介质中的磁矢势解

  $$
  \bm{A} = \frac{\mu}{4 \pi} \iiint \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|}
  $$

  可以验证，该解满足规范条件

  $$
  \begin{align*}
  \nabla \cdot \bm{A} &= \frac{\mu}{4 \pi} \iiint \nabla \cdot \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|} \\ &= \frac{\mu}{4 \pi} \iiint \bm{j}_0(\bm{r}') \cdot \nabla \frac{1}{|\bm{r} - \bm{r}'|} dV' \\ &= - \frac{\mu}{4 \pi} \iiint \bm{j}_0(\bm{r}') \cdot \nabla' \frac{1}{|\bm{r} - \bm{r}'|} dV' \\ &= - \frac{\mu}{4 \pi} \iiint \nabla' \cdot \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|} ~~~~~~~~~~~ \{\nabla' \cdot \bm{j}_0(\bm{r}') = 0\} \\ &= - \frac{\mu}{4 \pi} \oiint \frac{\bm{j}_0(\bm{r}') \cdot d\bm{S'}}{|\bm{r} - \bm{r}'|} = 0
  \end{align*}
  $$

  同时也可以得到毕奥-萨伐尔定理

  $$
  \begin{align*}
  \bm{B} = \nabla \times \bm{A} &= \frac{\mu}{4 \pi} \iiint \nabla \times \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|} \\ &= \frac{\mu}{4 \pi} \iiint \nabla \frac{1}{|\bm{r} - \bm{r}'|} \times \bm{j}_0(\bm{r}') dV' \\ &=  \frac{\mu}{4 \pi} \iiint \frac{\bm{j}_0(\bm{r}') \times (\bm{r} - \bm{r}')}{|\bm{r} - \bm{r}'|^3} dV'
  \end{align*}
  $$

### 3.1.3 边值关系

+ 将1.2节中的边值关系以及规范条件等价地转化为磁矢势$\bm{A}$的边值条件
  
  $$
  \bm{A_1} = \bm{A_2}
  $$

  $$
  \bm{n} \times (\frac{1}{\mu_2} \nabla \times \bm{A_2} -\frac{1}{\mu_1} \nabla \times \bm{A_1}) = \bm{i}_0
  $$

  对于第一式，边值关系规定切向连续，在此条件下，规范条件规定法向连续。

## 3.2 磁标势法

+ 当空间无传导电流和自由电荷分布时，将静电场与静磁场相比可见

  |          | 静电场                                                                                  | 静磁场                                                                                  |
  | :------- | :-------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------- |
  | 旋度方程 | $\nabla \times \bm{E} = 0$                                                              | $\nabla \times \bm{H} = 0$                                                              |
  | 散度方程 | $\nabla \cdot \bm{E} = - \nabla \cdot \bm{P}$                                           | $\nabla \cdot \bm{H} = - \mu_0 \nabla \cdot \bm{M}$                                     |
  | 性能方程 | $\bm{D} = \varepsilon \bm{E}$                                                           | $\bm{B} = \mu \bm{H}$                                                                   |
  | 极化强度 | $\bm{P} = \bm{D} - \varepsilon_0 \bm{E}$                                                | $\bm{M} = \frac{1}{\mu_0} \bm{B} - \bm{H}$                                              |
  | 边值条件 | $\bm{n} \times (\bm{E}_2 - \bm{E}_1) = 0$ <br> $\bm{n} \cdot (\bm{D}_2 - \bm{D_1}) = 0$ | $\bm{n} \times (\bm{H}_2 - \bm{H_1}) = 0$ <br> $\bm{n} \cdot (\bm{B}_2 - \bm{B_1}) = 0$ |

  二者的数学形式本质是相同的，故类比电势的引入与求解，可引入磁标势$\varphi_m$，将其表示为

  $$
  \bm{H} = - \nabla \varphi_m
  $$

  其满足与电势相似的边值条件

  $$
  \varphi_{m2} = \varphi_{m1}
  $$

  $$
  \mu_1 \frac{\partial{\varphi_{m1}}}{\partial{n}} = \mu_2 \frac{\partial{\varphi_{m2}}}{\partial{n}}
  $$

  通过与求解电势时类似的定解条件与方法(分离变量法与格林函数法)可以求出磁标势，从而的出静磁场的分布。

## 3.3 磁偶极子

### 3.3.1 小载流体静磁场的多极展开

+ 与求解电多极子类似地，将$1/|\bm{r} - \bm{r}'|$展开到一阶

  $$
  \frac{1}{|\bm{r} - \bm{r}'|} \approx \frac{1}{r} + \frac{\bm{r}' \cdot \bm{r}}{r^3}
  $$

  代入无限均匀线性各向同性磁介质中的磁矢势解得

  $$
  \bm{A} = \frac{\mu}{4 \pi r} \iiint \bm{j}_0(\bm{r}') dV' + \frac{\mu}{4 \pi r^3} \bm{r} \cdot \iiint \bm{r}' \bm{j}_0(\bm{r}') dV'
  $$

  对第一项，由

  $$
  \bm{j}_0(\bm{r}') = \nabla' \cdot [\bm{j}_0(\bm{r}') \bm{r}'] - \nabla' \cdot \bm{j}_0(\bm{r}') \bm{r}' = \nabla' \cdot [\bm{j}_0(\bm{r}') \bm{r}']
  $$

  可将体积分转化为面积分，由在边界处法向电流为0可得积分为0。对于第二项，有

  $$
  \bm{r}' \bm{j}_0(\bm{r}') = \nabla' \cdot [\bm{j}_0(\bm{r}') \bm{r}' \bm{r}'] - \nabla' \cdot \bm{j}_0(\bm{r}') \bm{r}' \bm{r}' - \bm{j}_0(\bm{r}') \bm{r}' = \nabla' \cdot [\bm{j}_0(\bm{r}') \bm{r}' \bm{r}'] - \bm{j}_0(\bm{r}') \bm{r}'
  $$

  而上式第一项可将体积分转化为面积分，由在边界处法向电流为0可得积分为0。上式可由以下方式导出

  $$
  \begin{align*}
  \nabla \cdot (\bm{a} \bm{r} \bm{r}) = \frac{\partial}{\partial x_i} (a_i x_j x_k) \bm{e_j} \bm{e_k} &= \frac{\partial a_i}{\partial x_i} x_j x_k \bm{e_j} \bm{e_k} + a_i \frac{\partial x_j}{\partial x_i} x_k \bm{e_j} \bm{e_k} + a_i x_j \frac{\partial x_k}{\partial x_i} \bm{e_j} \bm{e_k} \\ &= \frac{\partial a_i}{\partial x_i} x_j x_k \bm{e_j} \bm{e_k} + a_i \delta_{ij} x_k \bm{e_j} \bm{e_k} + a_i x_j \delta_{ik} \bm{e_j} \bm{e_k} \\ &= \frac{\partial a_i}{\partial x_i} x_j x_k \bm{e_j} \bm{e_k} + a_j x_k \bm{e_j} \bm{e_k} + x_j a_k \bm{e_j} \bm{e_k} \\ &= \nabla \cdot \bm{a} \bm{r} \bm{r} + \bm{a} \bm{r} + \bm{r} \bm{a}
  \end{align*} 
  $$

  故有

  $$
  \iiint \bm{r}' \bm{j}_0(\bm{r}') dV' = - \iiint \bm{j}_0(\bm{r}') \bm{r}' dV'
  $$

  代入可得

  $$
  \bm{A} = \frac{\mu}{4 \pi r^3} \bm{r} \cdot \iiint \frac{1}{2} [\bm{r}' \bm{j}_0(\bm{r}') - \bm{j}_0(\bm{r}') \bm{r}'] dV' = \frac{\mu}{4 \pi r^3} \frac{1}{2} \iiint [\bm{r}' \times \bm{j}_0(\bm{r}')] \times \bm{r} dV' = \frac{\mu \bm{m} \times \bm{r}}{4 \pi r^3}
  $$

  其中

  $$
  \bm{m} = \frac{1}{2} \iiint \bm{r}' \times \bm{j}_0(\bm{r}')
  $$

  为载流导体的磁矩。

### 3.3.2 小载流体在外场中所受的力与力矩

+ 下面将计算小载流体在磁场中受到的力与力矩，小载流体所受力为

  $$
  \bm{F} = \iiint \bm{j}_0(\bm{r}') \times \bm{B} dV'
  $$

  将磁场在载流体处$\bm{r}_0$展开到一阶，有

  $$
  \bm{B} \approx \bm{B}(\bm{r}_0) + \bm{r}' \cdot \nabla \bm{B} |_{\bm{r} = \bm{r}_0}
  $$

  代入可得

  $$
  \bm{F} = \iiint \bm{j}_0(\bm{r}') \times \bm{B}(\bm{r}_0) + \bm{j}_0 \times \bm{r}' \cdot \nabla \bm{B} dV'
  $$

  与之前类似的，由$\bm{j}_0(\bm{r}') = \nabla' \cdot [\bm{j}_0(\bm{r}') \bm{r}']$,转化为面积分后，可以验证第一项积分为0。故有
  
  $$
  \begin{align*}
  \bm{F} &= \iiint \bm{j}_0(\bm{r}') \times \bm{r}' \cdot \nabla \bm{B} dV' \\ &= \left[\iiint \bm{j}_0(\bm{r}') \bm{r}' dV' \right] \cdot \nabla \times \bm{B} \\ &= \iiint \frac{1}{2} [\bm{j}_0(\bm{r}') \bm{r}' - \bm{r}' \bm{j}_0(\bm{r}')] dV' \cdot \nabla \times \bm{B} \\ &= \frac{1}{2} \iiint \{[\bm{r}' \times \bm{j}_0(\bm{r}')] dV' \times \nabla\} \times \bm{B} \\ &= (\bm{m} \times \nabla) \times \bm{B} \\ &= (\nabla \bm{B}) \cdot \bm{m} - \bm{m} (\nabla \cdot \bm{B}) \\ &= (\nabla \bm{B}) \cdot \bm{m}
  \end{align*}
  $$

  小载流体所受力矩为

  $$
  \bm{M} = \iiint \bm{r}' \times [\bm{j}_0(\bm{r}') \times \bm{B}] dV' \approx \iiint [\bm{j}_0(\bm{r}') \bm{r}' \cdot \bm{B}(\bm{r}_0) - \bm{j}_0(\bm{r}') \cdot \bm{r}' \bm{B}(\bm{r}_0)] dV'
  $$

  对于第二项，由

  $$
  \bm{j}_0(\bm{r}') \cdot \bm{r}' = \bm{j}_0(\bm{r}') \cdot \nabla' \bm{r}' \cdot \bm{r}' = \frac{1}{2} \bm{j}_0(\bm{r}') \cdot \nabla' r'^2 = \frac{1}{2} \nabla \cdot [\bm{j}_0(\bm{r}') r'^2] - \frac{1}{2} \nabla \cdot \bm{j}_0(\bm{r}') r'^2 = \frac{1}{2} \nabla \cdot [\bm{j}_0(\bm{r}') r'^2]
  $$

  将体积分转化为面积分，利用边界处电流法向为0可知积分为0。故力矩为

  $$
  \begin{align*}
  \bm{M} &= \frac{1}{2} \iiint [\bm{j}_0(\bm{r}') \bm{r}' - \bm{r}' \bm{j}_0(\bm{r}')] \cdot \bm{B}(\bm{r}_0) dV' \\ &= \frac{1}{2} \iiint [\bm{j}_0(\bm{r}') \bm{r}' - \bm{r}' \bm{j}_0(\bm{r}')] \cdot \bm{B}(\bm{r}_0) dV' \\ &= \frac{1}{2} \iiint [\bm{r}' \times \bm{j}_0(\bm{r}')] \times \bm{B}(\bm{r}_0) dV' \\ &= \bm{m} \times \bm{B}(\bm{r}_0) 
  \end{align*}
  $$

## 3.4 磁能

### 3.4.1 磁能基本公式


+ 由1.3.3节中的结论，静磁场的能量密度为

  $$
  \mathcal{w} = \frac{1}{2} \bm{B} \cdot \bm{H}
  $$

  又由$H$的定义可得

  $$
  \mathcal{w} = \frac{1}{2} \bm{B} \cdot (\frac{1}{\mu_0} \bm{B} - \bm{M}) = \frac{1}{2} \frac{1}{\mu_0} B^2 + \frac{1}{2} \bm{B} \cdot \bm{M}
  $$

  第一项为磁能密度，第二项为介质的磁化能密度。全空间磁能可表示为

  $$
  \begin{align*}
  W &= \frac{1}{2} \iiint \bm{B} \cdot \bm{H} dV \\ &= \frac{1}{2} \iiint (\nabla \times \bm{A}) \cdot \bm{H} dV \\ &= \frac{1}{2} \iiint [\nabla \cdot (\bm{A} \times \bm{H}) + \bm{A} \cdot (\nabla \times \bm{H})] dV \\ &= \frac{1}{2} \iiint [\nabla \cdot (\bm{A} \times \bm{H}) + \bm{j}_0 \cdot \bm{A}] dV
  \end{align*}
  $$

  第一项可转化为面积分，利用无限远处的正则条件可得积分结果为0，故得

  $$
  W = \frac{1}{2} \iiint \bm{j}_0 \cdot \bm{A} dV
  $$

### 3.4.2 安培力做功

+ 考察将场源从无穷远处放置到外场中需要做的功。选取随场源一并移动的$O'$作为场源位置的参考点，用$\bm{r}_0$表示空间中固定的参考点$O$到$O'$的位矢，$\bm{r}'$表示$O'$到某个电流的位矢，参考点$O$到电流元的位矢为$\bm{r} = \bm{r}' + \bm{r}_0$。安培力做功可表示为

  $$
  A = \int_{\infty}^0 d\bm{r}_0 \cdot \iiint \bm{j}_0(\bm{r}') \times \bm{B}_e(\bm{r}_0 + \bm{r}') dV'
  $$

  对于被积项，有

  $$
  \bm{j}_0 \times \bm{B}_e = \bm{j}_0 \times (\nabla \times \bm{A}_e) = (\nabla \bm{A}_e) \cdot \bm{j}_0 - \bm{j}_0 \cdot \nabla \bm{A}_e = (\nabla_0 \bm{A}_e) \cdot \bm{j}_0 - \bm{j}_0 \cdot \nabla' \bm{A}_e = (\nabla_0 \bm{A}_e) \cdot \bm{j}_0 - \nabla' \cdot (\bm{j}_0 \bm{A}_e)
  $$

  其中，$\nabla$、$\nabla_0$和$\nabla'$分别表示仅作用在$\bm{r}$、$\bm{r}_0$和$\bm{r}'$上的矢量微分算符。推导过程中用到了$\nabla' \cdot \bm{j}_0 = 0$。上式右边第二项在积分时可转化为面积分，利用无穷远处的正则条件可得积分值为0。代回有

  $$
  \begin{align*}
  A &= \int_{\infty}^0 d\bm{r}_0 \cdot \iiint [\nabla_0 \bm{A}_e(\bm{r}_0 + \bm{r}')] \cdot \bm{j}_0(\bm{r}') dV' \\ &= \iiint dV' \int_{\infty}^0 d\bm{r}_0 \cdot [\nabla_0 \bm{A}_e(\bm{r}_0 + \bm{r}')] \cdot \bm{j}_0(\bm{r}') \\ &= \iiint \bm{j}_0(\bm{r}') \cdot \bm{A}_e(\bm{r}') dV'
  \end{align*}
  $$

  结果恰为上一小节中磁能的两倍。可将其与静电场情形类比，在外场中放入电荷所需做功也是如此，这是因为在求全空间的能量时虽然系数为1/2，但求和时算了两次，做功时系数为1，但只计入了将场源放入的情况，只算了一次。两者是对能量的不同描述，其结果是等价的。

### 3.5.3 小载流体在外磁场中的能量

+ 设小载流体的空间范围为$V'$，其尺寸远小于外磁场变化的空间尺度，在外磁场中，其磁能为

  $$
  W = \iiint \bm{j}_0(\bm{r}') \cdot \bm{A}_e dV
  $$

  与前面类似地，将A在场源位置$\bm{r}_0$附近作泰勒展开，代入上式得

  $$
  W \approx \bm{A}_e(\bm{r}_0) \cdot \iiint \bm{j}_0(\bm{r}') dV' + \iiint \bm{j}_0(\bm{r}') \bm{r}' : \nabla_0 \bm{A}_e
  $$

  后续化简过程与3.3.1节类似，不再重复，最终可得

  $$
  W = \bm{m} \cdot \bm{B}_e
  $$