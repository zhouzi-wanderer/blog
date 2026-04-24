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
> 
> 该笔记未讲解该书第七章，将缺少电磁波的散射、色散和吸收以及电磁质量与辐射阻尼部分。

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
  \bm{D} = \varepsilon \bm{E}, ~~~ \bm{H} = \frac{1}{\mu} \bm{B}
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
  \rho_0(\bm{r},t) = \rho_0(\bm{r}) e^{-t / \tau}, ~~~ \tau = \varepsilon_0 / \sigma
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
  p = \bm{f} \cdot \bm{v} = \bm{j} \cdot \bm{E} ~~~ \bm{v}与\bm{j}同向
  $$ 

  可见仅有电场对运动的电荷做功，且不区分场源是“自由”还是“束缚”。

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
  \bm{S} = \frac{1}{\mu_0} \bm{E} \times \bm{B}, ~~~ \mathcal{w} = \frac{\varepsilon_0 E^2}{2} + \frac{B^2}{2 \mu_0}
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
  \nabla \cdot \bm{A} &= \frac{\mu}{4 \pi} \iiint \nabla \cdot \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|} \\ &= \frac{\mu}{4 \pi} \iiint \bm{j}_0(\bm{r}') \cdot \nabla \frac{1}{|\bm{r} - \bm{r}'|} dV' \\ &= - \frac{\mu}{4 \pi} \iiint \bm{j}_0(\bm{r}') \cdot \nabla' \frac{1}{|\bm{r} - \bm{r}'|} dV' \\ &= - \frac{\mu}{4 \pi} \iiint \nabla' \cdot \frac{\bm{j}_0(\bm{r}') dV'}{|\bm{r} - \bm{r}'|} ~~~~~~~~~~ \{\nabla' \cdot \bm{j}_0(\bm{r}') = 0\} \\ &= - \frac{\mu}{4 \pi} \oiint \frac{\bm{j}_0(\bm{r}') \cdot d\bm{S'}}{|\bm{r} - \bm{r}'|} = 0
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
  \bm{B} \approx \bm{B}(\bm{r}_0) + \bm{r}' \cdot \nabla \bm{B}|_{\bm{r} = \bm{r}_0}
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

  全空间磁能增量为

  $$
  W = \iiint \bm{j}_0(\bm{r}') \cdot \bm{A}_e(\bm{r}') dV'
  $$

  为什么$W = A$而不是$W = -A$呢？因为在此处少考虑了为了维持原来的电流源不变外接的电源也需要做功，电源做功$A_e$恰好为外磁场做功的两倍，故由能量守恒$W = A_e - A = A$。

### 3.5.3 小载流体在外磁场中的能量

+ 设小载流体的空间范围为$V'$，其尺寸远小于外磁场变化的空间尺度，将其移至$\bm{r}_0$处磁场力做功为

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

  其所拥有的势能为

  $$
  U = - \bm{m} \cdot \bm{B}_e
  $$

&nbsp;

&nbsp;

&nbsp;

# 第4章 电磁波的传播

+ 本章讨论随时间变化的电磁场在无源区域（绝缘介质或导体）中的传播规律。我们将看到，麦克斯韦方程组预言了电磁波的存在。

## 4.1 平面电磁波

### 4.1.1 波动方程

+ 我们首先从麦克斯韦方程出发，揭示电磁场的波动特征。为简单起见，以下限于分区均匀线性各向同性介质。重抄微分形式的麦克斯韦方程如下：

  $$
  \nabla \times \bm{E} = - \frac{\partial \bm{B}}{\partial t}
  $$

  $$
  \nabla \times \bm{H} = \bm{j}_0 + \frac{\partial \bm{D}}{\partial t}
  $$

  $$
  \nabla \cdot \bm{D} = \rho_0
  $$

  $$
  \nabla \cdot \bm{B} = 0
  $$

+ 在无源区域（$\rho_0=0, \bm{j}_0=0$）的绝缘介质中，或者在导电介质中（$\bm{j}_0 = \sigma \bm{E}$），我们可以推导出电场满足的方程。对旋度方程取旋度，利用矢量恒等式 $\nabla \times (\nabla \times \bm{E}) = \nabla(\nabla \cdot \bm{E}) - \nabla^2 \bm{E}$，并代入性能方程 $\bm{D}=\varepsilon \bm{E}, \bm{B}=\mu \bm{H}$，可得阻尼波动方程：

  $$
  \nabla^2 \bm{E} - \mu \sigma \frac{\partial \bm{E}}{\partial t} - \mu \varepsilon \frac{\partial^2 \bm{E}}{\partial t^2} = 0
  $$

  同理，磁场 $\bm{B}$ 也满足形式相同的方程。

  1. 若介质为绝缘体（$\sigma=0$），方程简化为标准的波动方程，波速 $v = 1/\sqrt{\mu\varepsilon}$。

  2. 若介质为导体（$\sigma \neq 0$），一次对时间的偏导项体现了欧姆耗散对电磁波的阻尼效应，称为阻尼波动方程。

### 4.1.2 时谐电磁场与亥姆霍兹方程

+ 在空间任一点以稳恒振幅随时间做简谐周期变化的电磁场，称为时谐电磁场。随时间任意变化的场，总可以通过傅里叶变换分解为时谐场的叠加。
  采用复数表述：

  $$
  \bm{E}(\bm{r},t) = \bm{E}(\bm{r}) e^{-i\omega t}, ~~~ \bm{B}(\bm{r},t) = \bm{B}(\bm{r}) e^{-i\omega t}
  $$

  其中 $\omega$ 为角频率。实际物理量为复数场的实部。在复数表述下，时间偏导算符替换为 $-i\omega$。

+ 将时谐场形式代入波动方程，可消去时间因子，得到仅关于空间坐标的方程：

  $$
  \nabla^2 \bm{E} + k^2 \bm{E} = 0
  $$

  上式称为亥姆霍兹方程，其中 $k$ 为波数（复数）：

  $$
  k^2 = \omega^2 \mu \varepsilon + i \omega \mu \sigma
  $$

  对于绝缘介质（$\sigma=0$），$k = \omega\sqrt{\mu\varepsilon} = \omega/v$ 为实数。

+ 在时谐场中，利用法拉第电磁感应定律 $\nabla \times \bm{E} = -\frac{\partial \bm{B}}{\partial t} = i\omega \bm{B}$，我们可以由已知的电场直接推导出磁场：

  $$
  \bm{B} = \frac{1}{i\omega} \nabla \times \bm{E} = -\frac{i}{\omega} \nabla \times \bm{E}
  $$

  反之，利用安培环路定理 $\nabla \times \bm{H} = \bm{j}_0 - i\omega \bm{D} = (\sigma - i\omega\varepsilon) \bm{E}$，可由磁场推导电场（在无源区 $\bm{j}_0=0$ 且 $\sigma=0$ 时）：

  $$
  \bm{E} = \frac{i}{\omega\mu\varepsilon} \nabla \times \bm{B} = \frac{i v^2}{\omega} \nabla \times \bm{B}
  $$

+ 对于两个同频率的时谐物理量 $A(t) = \text{Re}(A_0 e^{-i\omega t})$ 和 $B(t) = \text{Re}(B_0 e^{-i\omega t})$，它们的乘积 $A(t)B(t)$ 的时间平均值（在一个周期内）可以通过复振幅计算：

  $$
  \overline{A(t)B(t)} = \frac{1}{2} \text{Re}(A_0 B_0^*)
  $$

  以坡印廷矢量（能流密度）为例，其实际瞬时值为 $\bm{S} = \bm{E}_{\text{real}} \times \bm{H}_{\text{real}}$。其时间平均值为：

  $$
  \overline{\bm{S}} = \frac{1}{2} \text{Re}(\bm{E} \times \bm{H}^*)
  $$

  其中 $\bm{E}$ 和 $\bm{H}$ 为场的复振幅矢量。这种计算方法避免了直接对三角函数进行繁琐的积分运算。

### 4.1.3 无限均匀、线性各向同性绝缘介质中的平面电磁波

+ 在无限大绝缘介质中，亥姆霍兹方程存在平面波解：

  $$
  \bm{E}(\bm{r},t) = \bm{E}_0 e^{i(\bm{k}\cdot\bm{r} - \omega t)}
  $$

  $$
  \bm{B}(\bm{r},t) = \bm{B}_0 e^{i(\bm{k}\cdot\bm{r} - \omega t)}
  $$

  其中 $\bm{k}$ 为波矢，大小 $k = \omega\sqrt{\mu\varepsilon}$，方向为波的传播方向。

  将解代入麦克斯韦方程组，利用 $\nabla \to i\bm{k}$ 和 $\partial/\partial t \to -i\omega$，得到：

  横波性：$\bm{k} \cdot \bm{E} = 0$，$\bm{k} \cdot \bm{B} = 0$。电场和磁场都垂直于传播方向。

  正交性：$\bm{B} = \frac{1}{\omega} \bm{k} \times \bm{E} = \frac{1}{v} \hat{\bm{k}} \times \bm{E}$。$\bm{E}, \bm{B}, \bm{k}$ 构成右手正交系。

  同相性与振幅关系：电场与磁场同相位，且振幅满足：

  $$
  |\bm{E}| = v |\bm{B}| = \frac{1}{\sqrt{\mu\varepsilon}} |\bm{B}|
  $$

  或者引入本征阻抗 $Z = \sqrt{\mu/\varepsilon}$，有 $|\bm{E}| = Z |\bm{H}|$。

+ 总能量密度： 
  
  $$
  w = \frac{1}{2}\varepsilon E^2 + \frac{1}{2\mu} B^2 = \varepsilon E^2
  $$

  能流密度（坡印廷矢量）：

  $$
  \bm{S} = \bm{E} \times \bm{H} = \frac{1}{Z} |\bm{E}|^2 \hat{\bm{k}} = w v \hat{\bm{k}}
  $$

  能量以速度 $v$ 沿波矢方向传播。

  动量密度：
  
  $$
  \bm{g} = \mu \varepsilon \bm{S} = \frac{1}{v^2} \bm{S}
  $$

### 4.1.4 电磁波的偏振

+ 偏振是指电场矢量 $\bm{E}$ 在垂直于传播方向（设为 $z$ 轴）平面内的取向随时间的变化规律。设 $\bm{E} = (E_x \hat{\bm{x}} + E_y \hat{\bm{y}}) e^{i(kz - \omega t)}$，其中 $E_x, E_y$ 为复振幅。

  1. 线偏振 (Linear Polarization)：

    若 $E_x$ 和 $E_y$ 的相位相同或相差 $\pi$，则合成电场矢量始终沿一条直线振动。

  2. 圆偏振 (Circular Polarization)：

    若 $|E_x| = |E_y|$ 且相位差为 $\pm \pi/2$。

    相位差 $+\pi/2$：电场矢量沿逆时针旋转（迎着波传播方向看），称为左旋圆偏振。

    相位差 $-\pi/2$：电场矢量沿顺时针旋转，称为右旋圆偏振。

  3. 椭圆偏振 (Elliptical Polarization)：

  一般情况，电场矢量的端点轨迹是一个椭圆。任何椭圆偏振都可以分解为两个正交的线偏振，或者分解为两个旋转方向相反的圆偏振。

## 4.2 电磁波在绝缘介质界面上的反射和折射

### 4.2.1 定解问题的提法

+ 考虑两个半无限大、线性均匀各向同性的绝缘介质，分界面为无限大平面（设为 $z=0$）。

  介质1 ($z<0$)：介电常数 $\varepsilon_1$，磁导率 $\mu_1$。

  介质2 ($z>0$)：介电常数 $\varepsilon_2$，磁导率 $\mu_2$。

  一列平面电磁波从介质1入射到界面上，将产生反射波（回介质1）和折射波（入介质2）。

  场可表示为：

  入射波 (Incident)：$\bm{E} = \bm{E}_0 e^{i(\bm{k}\cdot\bm{r} - \omega t)}$

  反射波 (Reflected)：$\bm{E}' = \bm{E}'_0 e^{i(\bm{k}'\cdot\bm{r} - \omega' t)}$

  折射波 (Refracted)：$\bm{E}'' = \bm{E}''_0 e^{i(\bm{k}''\cdot\bm{r} - \omega'' t)}$

  磁场 $\bm{B}$ 通过 $\bm{B} = \frac{1}{\omega} \bm{k} \times \bm{E}$ 与电场相关联。

### 4.2.2 反射定律与折射定律

+ 根据边值关系，界面上 ($z=0$) 电磁场的切向分量必须连续。这意味着三个波的场矢量在界面上的时空变化步调必须一致，即相位因子在 $z=0$ 平面上必须相等：

  $$
  (\bm{k}\cdot\bm{r} - \omega t)|_{z=0} = (\bm{k}'\cdot\bm{r} - \omega' t)|_{z=0} = (\bm{k}''\cdot\bm{r} - \omega'' t)|_{z=0}
  $$

  由此导出相位匹配条件：

  频率不变：$\omega = \omega' = \omega''$。反射和折射不改变波的频率。

  共面性：$\bm{k}, \bm{k}', \bm{k}''$ 的切向分量相等。若选取入射面为 $xz$ 平面（即 $k_y=0$），则 $k'_y=0, k''_y=0$。入射波矢、反射波矢、折射波矢与界面法线共面。

  由于在介质1中 $k=k'=\omega\sqrt{\mu_1\varepsilon_1}$，且切向分量 $k_x = k'_x$，则有：

  $$
  k \sin\theta = k' \sin\theta' \implies \theta = \theta'
  $$

  此即反射定律：反射角等于入射角。

  由 $k_x = k''_x$，得 $k \sin\theta = k'' \sin\theta''$。代入波数公式 $k = \omega\sqrt{\mu\varepsilon}$，得：

  $$
  \sqrt{\mu_1\varepsilon_1} \sin\theta = \sqrt{\mu_2\varepsilon_2} \sin\theta''
  $$

  引入折射率 $n = \sqrt{\frac{\mu\varepsilon}{\mu_0\varepsilon_0}} = \frac{c}{v}$，则有折射定律 (斯涅尔定律)：

  $$
  n_1 \sin\theta = n_2 \sin\theta''
  $$

### 4.2.3 菲涅尔公式 (Fresnel Equations)

+ 利用电磁场切向分量连续的边值关系，可以确定反射波和折射波的振幅。将任意偏振的入射波分解为两个独立的分量分别处理：

  1. E 垂直于入射面 (s 偏振 / TE 波)

    电场 $\bm{E}$ 沿 $y$ 轴（垂直纸面），只有切向分量。

    磁场 $\bm{H}$ 在 $xz$ 平面内，其切向分量（$x$ 分量）为 $-H\cos\theta$。

    边界条件：

    $$
    E + E' = E''
    $$

    $$
    -H\cos\theta + H'\cos\theta' = -H''\cos\theta''
    $$

    利用 $H = E/Z$ ($Z=\sqrt{\mu/\varepsilon}$) 和 $\theta=\theta'$，解得反射系数 $r_s$ 和透射系数 $t_s$：

    $$
    r_s = \frac{E'_0}{E_0} = \frac{Z_2 \cos\theta - Z_1 \cos\theta''}{Z_2 \cos\theta + Z_1 \cos\theta''}
    $$

    $$
    t_s = \frac{E''_0}{E_0} = \frac{2 Z_2 \cos\theta}{Z_2 \cos\theta + Z_1 \cos\theta''}
    $$

  2. E 平行于入射面 (p 偏振 / TM 波)

    磁场 $\bm{H}$ 沿 $y$ 轴（垂直纸面），只有切向分量。

    电场 $\bm{E}$ 在 $xz$ 平面内，其切向分量（$x$ 分量）为 $E\cos\theta$。

    边界条件：

    $$
    H + H' = H''
    $$

    $$
    E\cos\theta - E'\cos\theta' = E''\cos\theta''
    $$

    (注：此处规定反射波 $\bm{E}'$ 的正方向与波矢 $\bm{k}'$ 构成右手系，导致切向分量相减)

    解得：

    $$
    r_p = \frac{H'_0}{H_0} = \frac{Z_1 \cos\theta - Z_2 \cos\theta''}{Z_1 \cos\theta + Z_2 \cos\theta''} \quad (\text{磁场反射系数})
    $$

    通常我们关注电场，利用 $E=ZH$，可得电场反射系数（注意与磁场系数可能差一个符号，取决于正方向定义，这里给出常用形式）：

    $$
    r_p = \frac{E'_0}{E_0} = \frac{Z_2 \cos\theta'' - Z_1 \cos\theta}{Z_2 \cos\theta'' + Z_1 \cos\theta}
    $$

    $$
    t_p = \frac{E''_0}{E_0} = \frac{2 Z_2 \cos\theta}{Z_2 \cos\theta'' + Z_1 \cos\theta}
    $$

    若采用非磁性介质近似 ($\mu_1 = \mu_2 = \mu_0$)，此时 $Z \propto 1/n$。菲涅尔公式可化简为仅含 $\theta$ 和 $\theta''$ 的形式（利用斯涅尔定律）：

    $$
    r_s = - \frac{\sin(\theta - \theta'')}{\sin(\theta + \theta'')}
    $$

    $$
    r_p = \frac{\tan(\theta - \theta'')}{\tan(\theta + \theta'')}
    $$

### 4.2.4 物理分析

+ 布儒斯特角 (Brewster Angle)

  对于 p 偏振，当 $\theta + \theta'' = \pi/2$ 时，$\tan(\theta+\theta'') \to \infty$，导致 $r_p = 0$。此时只有 s 偏振光被反射，反射光变为完全线偏振光。对应的入射角称为布儒斯特角 $\theta_B$：

  $$
  \tan\theta_B = \frac{n_2}{n_1}
  $$

+ 半波损失

  ($n_1 < n_2$) 时，对于正入射 ($\theta \approx 0$)，由菲涅尔公式可知 $r_s < 0, r_p < 0$ (取决于定义)。这意味着反射波电场相对于入射波产生 $\pi$ 的相位突变，称为半波损失。

+ 全反射 (Total Internal Reflection)

  发生条件：光从光密介质射向光疏介质 ($n_1 > n_2$)，且入射角大于临界角 $\theta_c = \arcsin(n_2/n_1)$。此时 $\sin\theta'' > 1$，$\cos\theta'' = \sqrt{1-\sin^2\theta''}$ 变为纯虚数。此时：

  1. 反射系数模为 1 ($|r_s|=|r_p|=1$)，能量全部反射。

  2. 折射波变成倏逝波 (Evanescent Wave)：沿界面方向 ($x$) 传播，但在垂直界面方向 ($z$) 指数衰减。倏逝波不向介质 2 深处传输平均能流，但在界面附近存在能量吞吐（古斯-汉兴位移）。

### 4.2.5 能量守恒和动量守恒关系

+ 能量守恒关系

  反射率 $R$ 和透射率 $T$ 定义为界面上垂直于界面的平均能流密度（即功率流）之比。由于入射波和反射波在同一介质中（阻抗相同），且角度相同（截面变化相同），故反射率直接等于振幅反射系数的模平方：

  $$
  R = \frac{|\langle S'_{z} \rangle|}{|\langle S_{z} \rangle|} = \frac{|E'_0|^2 / (2Z_1)}{|E_0|^2 / (2Z_1)} = |r|^2
  $$

  对于透射波，介质阻抗变更 ($Z_1 \to Z_2$) 且波束截面因折射而改变 ($\cos\theta \to \cos\theta''$)。因此，透射率不等于透射系数的模平方，必须包含介质阻抗比和几何因子：

  $$
  T = \frac{|\langle S''_{z} \rangle|}{|\langle S_{z} \rangle|} = \frac{\frac{1}{2Z_2}|E''_0|^2 \cos\theta''}{\frac{1}{2Z_1}|E_0|^2 \cos\theta} = \underbrace{\frac{Z_1}{Z_2}}_{\text{阻抗修正}} \underbrace{\frac{\cos\theta''}{\cos\theta}}_{\text{几何修正}} |t|^2
  $$

  对于非磁性介质 ($\mu_1=\mu_2=\mu_0$)，利用 $n \propto 1/Z$，系数可写为：

  $$
  T = \frac{n_2 \cos\theta''}{n_1 \cos\theta} |t|^2
  $$

  对于无损耗介质，总能量守恒要求：

  $$
  R + T = 1
  $$

  将菲涅尔公式代入计算，可验证此守恒关系恒成立。

+ 动量守恒关系

  电磁波不仅携带能量，还携带动量。当电磁波在界面上发生反射和折射时，电磁动量的流动方向和大小发生改变，根据动量守恒定律，界面（或介质）必将受到力的作用，这种力即为光压。设单位时间内投射到界面单位面积上的平均电磁动量流密度张量为 $\overline{\mathbf{T}}$，则界面受到的平均压力 $\bm{f}$ 为入射、反射和折射波的法向动量流密度之差：

  $$
  \bm{f} = \bm{n} \cdot (\overline{\mathbf{T}}_1 - \overline{\mathbf{T}}_2) = \bm{n} \cdot (\overline{\mathbf{T}}_{\text{inc}} + \overline{\mathbf{T}}_{\text{refl}} - \overline{\mathbf{T}}_{\text{trans}})
  $$

  对于平面波，动量流密度张量的平均值为 $\overline{\mathbf{T}} = \overline{w} \hat{\bm{k}}\hat{\bm{k}}$（其中 $\overline{w}$ 为平均能量密度）。界面受到的法向压力 $p$ (压强) 为：

  $$
  p = (\overline{w} \cos^2\theta + \overline{w}' \cos^2\theta) - \overline{w}'' \cos^2\theta''
  $$

  利用能量密度与能流密度的关系 $\overline{S} = \overline{w} v$，以及能量守恒关系 $R+T=1$，可以推导出：

  1. 全吸收界面 ($R=0, T=0$，能量被界面吸收)：
    光压为 $p = \overline{w} \cos^2\theta$。对于正入射 ($\theta=0$)，光压等于入射波能量密度。

  2. 全反射界面 ($R=1, T=0$，如理想导体)：
    
    光压为 $p = 2\overline{w} \cos^2\theta$。对于正入射，光压等于入射波能量密度的两倍（因为动量反向，变化量加倍）。

  3. 普通透明介质界面：
  
    由于 $\overline{w}''$ 与 $\overline{w}$ 的关系较为复杂（涉及折射率），界面受力可能表现为压力或拉力，具体取决于介质参数。通常情况下，光从光疏介质射向光密介质时，界面受到指向光疏介质的压力。

## 4.3 导体中的电磁波

### 4.3.1 导体中的非均匀平面波

+ 在导电介质中，为简化计算，通常引入复数，复介电常数定义为 $\varepsilon' = \varepsilon + i \frac{\sigma}{\omega}$。亥姆霍兹方程 $\nabla^2 \bm{E} + k^2 \bm{E} = 0$ 中的波数 $k$ 变为复数：

  $$
  k^2 = \omega^2 \mu \varepsilon' = \omega^2 \mu \varepsilon + i \omega \mu \sigma
  $$

  此时，平面波解的形式为 $\bm{E} = \bm{E}_0 e^{i(\bm{k}\cdot\bm{r} - \omega t)}$，其中波矢 $\bm{k}$ 也是复矢量。将其分解为实部和虚部：

  $$
  \bm{k} = \bm{\beta} + i\bm{\alpha}
  $$

  其中：$\bm{\beta}$ 为 相位矢量 (Phase Vector)，垂直于等相位面，决定波的传播方向和相速度。$\bm{\alpha}$ 为 衰减矢量 (Attenuation Vector)，垂直于等振幅面，决定波幅衰减的方向。将 $\bm{k}$ 代入平面波表达式：

  $$
  \bm{E} = \bm{E}_0 e^{-\bm{\alpha}\cdot\bm{r}} e^{i(\bm{\beta}\cdot\bm{r} - \omega t)}
  $$

  将 $\bm{k} = \bm{\beta} + i\bm{\alpha}$ 代入色散关系 $\bm{k} \cdot \bm{k} = k^2$，并分离实部和虚部：

  $$
  (\bm{\beta} + i\bm{\alpha}) \cdot (\bm{\beta} + i\bm{\alpha}) = \beta^2 - \alpha^2 + 2i \bm{\alpha} \cdot \bm{\beta} = \omega^2 \mu \varepsilon + i \omega \mu \sigma
  $$

  由此得到两个约束方程：

  $$
  \beta^2 - \alpha^2 = \omega^2 \mu \varepsilon
  $$

  $$
  \bm{\alpha} \cdot \bm{\beta} = \frac{1}{2} \omega \mu \sigma
  $$

  第二个方程表明，只要介质导电 ($\sigma \neq 0$)，$\bm{\alpha} \cdot \bm{\beta} \neq 0$，即 $\bm{\alpha}$ 与 $\bm{\beta}$ 之间的夹角不能是 $\pi/2$。但它们不一定平行。

+ 考虑电磁波从绝缘介质斜入射到导体表面（设界面为 $z=0$ 平面）。根据边界条件，波矢的切向分量必须连续。由于入射波矢 $\bm{k}_i$ 是实矢量，折射波矢 $\bm{k}_t$ 的切向分量 $\bm{k}_{t\parallel}$ 也必须是实数。

  $$
  \bm{k}_{t\parallel} = \bm{k}_{i\parallel} = \text{实数}
  $$

  这意味着 $\bm{k}_t$ 的虚部 $\bm{\alpha}$ 没有切向分量，即：

  $$
  \bm{\alpha} \perp \text{界面} \quad (\bm{\alpha} \parallel \hat{\bm{z}})
  $$

  而折射波的实部 $\bm{\beta}$ 遵循折射定律，通常与界面法线成一定角度（除非正入射）。因此，在斜入射情况下，$\bm{\alpha}$ 与 $\bm{\beta}$ 不平行。这种等相位面与等振幅面不重合的波称为非均匀平面波 (Inhomogeneous Plane Wave)。波沿折射角方向传播，但振幅总是沿着垂直于界面的方向衰减最快。

### 4.3.2 导体中的均匀平面波

+ 为简化讨论，以下限于讨论垂直入射情况。当电磁波垂直入射到导体表面，或者波源就在无限大导体内部时，根据对称性，相位传播方向与衰减方向一致。此时：

  $$
  \bm{\alpha} \parallel \bm{\beta}
  $$

  这种等相位面与等振幅面重合的波称为均匀平面波 (Homogeneous Plane Wave)。由于方向平行，$\bm{\alpha} \cdot \bm{\beta} = \alpha \beta$。方程组简化为：

  $$
  \beta^2 - \alpha^2 = \omega^2 \mu \varepsilon
  $$

  $$
  2 \alpha \beta = \omega \mu \sigma
  $$

  联立求解可得 $\alpha$ 和 $\beta$ 的显式解：

  $$
  \beta = \omega \sqrt{\frac{\mu\varepsilon}{2} \left[ \sqrt{1 + (\frac{\sigma}{\omega\varepsilon})^2} + 1 \right]} \quad (\text{相位常数})
  $$

  $$
  \alpha = \omega \sqrt{\frac{\mu\varepsilon}{2} \left[ \sqrt{1 + (\frac{\sigma}{\omega\varepsilon})^2} - 1 \right]} \quad (\text{衰减常数})
  $$

+ 对于良导体 ($\sigma \gg \omega\varepsilon$)，上述公式可取近似：

  $$
  \alpha \approx \beta \approx \sqrt{\frac{\omega\mu\sigma}{2}} = \frac{1}{\delta}
  $$

  其中 $\delta$ 定义为趋肤深度：

  $$
  \delta = \sqrt{\frac{2}{\omega\mu\sigma}}
  $$

  这表明在良导体中，均匀平面波的波长 $\lambda = 2\pi/\beta = 2\pi\delta$，且波幅在穿过 $\delta$ 的距离后衰减为原来的 $1/e$。电磁波被限制在导体表面极薄的一层内。

  良导体中相速 $v_p = \omega/\beta \approx \sqrt{2\omega/(\mu\sigma)}$，群速 $v_g = d\omega/d\beta = 2v_p$。这是一种强色散介质。

  由 $\nabla \times \bm{E} = i\omega \mu \bm{H}$，对于平面波 $\bm{H} = \frac{k}{\omega\mu} \hat{\bm{k}} \times \bm{E}$。由于 $k = \beta + i\alpha$，且良导体中 $\alpha \approx \beta$，故

  $$
  k \approx \beta(1+i) = \sqrt{2}\beta e^{i\pi/4}
  $$

  因此，磁场 $\bm{H}$ 在相位上滞后于电场 $\bm{E}$ 约 $45^\circ$ ($\pi/4$)。

### 4.3.3 导体中的功率损耗与平均能流密度

+ 导体中存在欧姆损耗，电磁能转化为热能。平均焦耳热功率密度为：

  $$
  \bar{p} = \frac{1}{2} \text{Re}(\bm{j} \cdot \bm{E}^*) = \frac{1}{2} \sigma |\bm{E}|^2 = \frac{1}{2} \sigma |\bm{E}_0|^2 e^{-2\alpha z}
  $$

  功率密度随深度以 $e^{-2\alpha z} = e^{-2z/\delta}$ 的速率衰减。对于在导体中沿 $z$ 方向传播的均匀平面波，平均坡印廷矢量为：

  $$
  \bar{\bm{S}} = \frac{1}{2} \text{Re}(\bm{E} \times \bm{H}^*)
  $$

  利用 $\bm{H} = \frac{k}{\omega\mu} \hat{\bm{z}} \times \bm{E}$，得：

  $$
  \bar{\bm{S}} = \frac{1}{2} |\bm{E}|^2 \text{Re}\left(\frac{k^*}{\omega\mu}\right) \hat{\bm{z}} = \frac{1}{2} |\bm{E}|^2 \frac{\beta}{\omega\mu} \hat{\bm{z}}
  $$

  代入 $|\bm{E}|^2 = |\bm{E}_0|^2 e^{-2\alpha z}$，得：

  $$
  \bar{S}_z(z) = \frac{\beta}{2\omega\mu} |\bm{E}_0|^2 e^{-2\alpha z}
  $$

  这表明平均能流密度同样随深度指数衰减。在良导体近似下 ($\alpha \approx \beta \approx 1/\delta$)，单位面积导体表面的平均功耗 $\bar{P}_s$ 可以通过对 $\bar{p}$ 积分得到：

  $$
  \bar{P}_s = \int_0^\infty \bar{p} \, dz = \int_0^\infty \frac{1}{2} \sigma |\bm{E}_0|^2 e^{-2z/\delta} \, dz = \frac{\sigma \delta}{4} |\bm{E}_0|^2
  $$

  通常用表面切向磁场 $H_{0t}$ 来表示更方便（因为在边界上 $H_t$ 近似等于外加磁场，而 $E_t$ 很小）。利用 $|\bm{E}_0| \approx \sqrt{\frac{\omega\mu}{\sigma}} |\bm{H}_{0t}|$ 和 $\delta \approx \sqrt{\frac{2}{\omega\mu\sigma}}$，可推得：

  $$
  \bar{P}_s = \frac{1}{2} R_s |\bm{H}_{0t}|^2
  $$

  其中 $R_s$ 定义为表面电阻：

  $$
  R_s = \frac{1}{\sigma \delta} = \sqrt{\frac{\omega\mu}{2\sigma}}
  $$

  这说明导体表面的功率损耗等效于一个阻值为 $R_s$ 的电阻上流过大小为 $|\bm{H}_{0t}|$ 的表面电流所产生的损耗。

### 4.3.4 导体表面的反射与折射

+ 处理导体表面的反射与折射时，只需将绝缘介质公式中的折射率 $n_2$ 或阻抗 $Z_2$ 替换为复数。导体的复波阻抗为：

  $$
  Z_c = \sqrt{\frac{\mu}{\varepsilon'}} \approx \sqrt{\frac{\mu \omega}{\sigma}} e^{-i\pi/4} \quad (\text{良导体})
  $$

  当电磁波从真空 (阻抗 $Z_0$) 垂直入射到良导体 (阻抗 $Z_c$)时：

  $$
  r = \frac{Z_c - Z_0}{Z_c + Z_0}
  $$

  由于对于良导体（如铜、银），$|Z_c| \ll Z_0$，故：

  $$
  r \approx \frac{-Z_0}{Z_0} = -1
  $$

  这意味着良导体表面发生全反射，且有 $\pi$ 的相位突变（半波损失）。反射率 $R = |r|^2$ 的更精确近似为：

  $$
  R \approx 1 - 2\sqrt{\frac{2\omega\varepsilon_0}{\sigma}}
  $$

  该公式表明，频率越低或电导率越高，反射率越接近 1。这解释了金属在低频和光频（可见光范围对许多金属仍满足良导体条件）具有良好反射性的原因。

## 4.4 谐振腔和波导管

+ 要有效激发和输送高频电磁波（微波），必须将电磁场局限在有限空间内，金属导体正好可用来实现这一目标。本节讨论由理想导体壁围成的空腔（谐振腔）和管（波导管）中的电磁场解。

### 4.4.1 基本方程和边界条件

+ 假设谐振腔或波导管内部为真空（或线性均匀各向同性介质 $\varepsilon, \mu$），无场源 ($\rho=0, \bm{j}=0$)。电磁场满足定态波动方程（亥姆霍兹方程）：

  $$
  \nabla^2 \bm{E} + k^2 \bm{E} = 0
  $$

  $$
  \nabla^2 \bm{H} + k^2 \bm{H} = 0
  $$

  其中 $k^2 = \omega^2 \mu \varepsilon$。此外，电场还必须满足无散条件 $\nabla \cdot \bm{E} = 0$。

+ 在理想导体壁面 $S$ 上，电场切向分量为零，磁场法向分量为零：

  $$
  \bm{n} \times \bm{E} |_S = 0 \quad \text{或} \quad E_\tau |_S = 0
  $$

  $$
  \bm{n} \times \bm{H} |_S = 0 \quad \text{或} \quad H_\tau |_S = 0
  $$

  其中 $\bm{n}$ 为边界内法向。

  说明：采用上述模型的原因在于，实际波导通常由良导体制成，在微波频段其趋肤深度极小，可视作理想导体，内部场为零，从而导出表面切向电场和法向磁场为零的边界条件。同时，由于波动方程是二阶方程，其解空间比一阶麦克斯韦方程组更广（包含非物理的纵波解），因此必须显式引入无散条件 $\nabla \cdot \bm{E} = 0$ 来剔除伪解，确保结果的物理正确性。

+ 对于波导管（沿 $z$ 轴延伸），通常将场分解为纵向分量 ($E_z, H_z$) 和横向分量 ($\bm{E}_t, \bm{H}_t$)。利用麦克斯韦方程，可以将横向分量用纵向分量表示出来。因此，求解过程归结为先求解 $E_z$ 和 $H_z$ 满足的二维标量亥姆霍兹方程，再推导其他分量。根据 $E_z$ 和 $H_z$ 的存在情况，电磁波分为三类：

  TEM 波 ($E_z=0, H_z=0$)：在单连通的空心金属波导中不存在。

  TE 波 ($E_z=0, H_z \neq 0$)：电场由磁场感应产生，只有横向电场。

  TM 波 ($E_z \neq 0, H_z=0$)：磁场由电场位移电流产生，只有横向磁场。

### 4.4.2 谐振腔

+ 谐振腔是封闭的金属空腔，电磁波在其中形成三维驻波。

  考虑边长分别为 $L_1, L_2, L_3$ 的长方体谐振腔（$0 \le x \le L_1, 0 \le y \le L_2, 0 \le z \le L_3$）。采用分离变量法求解 $E_z$（针对 TM 模）或 $H_z$（针对 TE 模）。以 $E_z$ 为例，满足 $\nabla^2 E_z + k^2 E_z = 0$。解的形式为驻波：

  $$
  E_z(x,y,z) = E_0 \sin(k_x x) \sin(k_y y) \cos(k_z z)
  $$

  根据边界条件（$x=0,L_1$ 和 $y=0,L_2$ 处 $E_z=0$；$z=0,L_3$ 处 $E_x, E_y$ 为零导致 $E_z$ 的 $z$ 向导数为零），波数分量必须满足：

  $$
  k_x = \frac{m\pi}{L_1}, \quad k_y = \frac{n\pi}{L_2}, \quad k_z = \frac{l\pi}{L_3} \quad (m, n, l \text{ 为整数})
  $$

+ 总波数 $k^2 = k_x^2 + k_y^2 + k_z^2$，对应的谐振角频率为：

  $$
  \omega_{mnl} = v k = \frac{1}{\sqrt{\mu\varepsilon}} \sqrt{\left(\frac{m\pi}{L_1}\right)^2 + \left(\frac{n\pi}{L_2}\right)^2 + \left(\frac{l\pi}{L_3}\right)^2}
  $$

  这表明谐振腔只能以特定的一系列离散频率（本征频率）进行振荡。

### 4.4.3 波导管

+ 波导管是无限长的金属管，电磁波沿轴向（$z$ 轴）传播。对于行波解，场沿 $z$ 向的变化为 $e^{i k_z z}$（$k_z$ 为传播常数，常记为 $\beta$）。场量写为：

  $$
  \bm{E}(x,y,z) = \bm{E}(x,y) e^{i k_z z}
  $$

  代入波动方程，得到横向截面上的二维方程：

  $$
  \nabla_t^2 \psi + (k^2 - k_z^2) \psi = 0
  $$

  其中 $\psi$ 代表 $E_z$ 或 $H_z$。令截止波数 $k_c^2 = k^2 - k_z^2 = \mu\varepsilon\omega^2 - k_z^2$。

+ 对于截面为 $a \times b$ 的矩形波导。

  1. TM 模 ($H_z=0$)：

    边界条件要求 $E_z$ 在管壁上为零。

    $$
    E_z = E_0 \sin(\frac{m\pi x}{a}) \sin(\frac{n\pi y}{b}) \quad (m, n = 1, 2, \dots)
    $$

    截止波数：$k_c^2 = (\frac{m\pi}{a})^2 + (\frac{n\pi}{b})^2$。

  2. TE 模 ($E_z=0$)：

    边界条件要求与对 $E_z$ 要求相同。

    $$
    H_z = H_0 \sin(\frac{m\pi x}{a}) \sin(\frac{n\pi y}{b}) \quad (m, n = 1, 2, \dots)
    $$

    截止波数与 TM 模形式相同。

+ 波导中的波传播常数 $k_z$ 为：

  $$
  k_z = \sqrt{\mu\varepsilon\omega^2 - k_c^2} = \sqrt{\mu\varepsilon(\omega^2 - \omega_c^2)}
  $$

  其中 $\omega_c = v k_c$ 为截止频率。

  当 $\omega > \omega_c$ 时，$k_z$ 为实数，波可以无衰减地传播。

  当 $\omega < \omega_c$ 时，$k_z$ 为纯虚数，波幅指数衰减，形成倏逝波，波导截止。

  主模：对于 $a > b$ 的矩形波导，截止频率最低的模式是 $TE_{10}$ 模 ($m=1, n=0$)，其截止波长为 $\lambda_c = 2a$。

+ 在波导中传播时（$\omega > \omega_c$）：

  相速：$v_p = \frac{\omega}{k_z} = \frac{v}{\sqrt{1 - (\omega_c/\omega)^2}} > v$。

  群速：$v_g = \frac{d\omega}{d k_z} = v \sqrt{1 - (\omega_c/\omega)^2} < v$。
  
  满足 $v_p v_g = v^2$。波导具有显著的色散特性。

&nbsp;

&nbsp;

&nbsp;

# 第5章 电磁波的辐射

## 5.1 电磁势及其方程

### 5.1.1 电磁势的引入

+ 在一般时变电磁场中，磁场 $\bm{B}$ 依然是无散场，但电场 $\bm{E}$ 不再是无旋场（由于变化的磁场产生感应电场）。回顾麦克斯韦方程组：

  $$
  \nabla \cdot \bm{B} = 0
  $$

  $$
  \nabla \times \bm{E} = - \frac{\partial \bm{B}}{\partial t}
  $$

  矢势 $\bm{A}$ 的引入：由 $\nabla \cdot \bm{B} = 0$，根据矢量恒等式 $\nabla \cdot (\nabla \times \bm{A}) \equiv 0$，可引入矢量场 $\bm{A}$ 使其旋度等于磁场：

  $$
  \bm{B} = \nabla \times \bm{A}
  $$

  标势 $\varphi$ 的引入：将上式代入法拉第电磁感应定律：

  $$
  \nabla \times \bm{E} = - \frac{\partial}{\partial t} (\nabla \times \bm{A}) = - \nabla \times \frac{\partial \bm{A}}{\partial t}
  $$

  移项得：

  $$
  \nabla \times (\bm{E} + \frac{\partial \bm{A}}{\partial t}) = 0
  $$

  由于无旋场可以表示为标量场的梯度，故可引入标量场 $\varphi$（注意符号）：

  $$
  \bm{E} + \frac{\partial \bm{A}}{\partial t} = - \nabla \varphi
  $$

### 5.1.2 规范变换与规范不变性

+ 电磁势的不唯一性：对于给定的电磁场 $(\bm{E}, \bm{B})$，电磁势 $(\varphi, \bm{A})$ 并不是唯一的。
  设有一组电磁势 $(\varphi, \bm{A})$，引入任意标量函数 $\psi(\bm{r}, t)$，作如下变换：

  $$
  \bm{A}' = \bm{A} + \nabla \psi
  $$

  $$
  \varphi' = \varphi - \frac{\partial \psi}{\partial t}
  $$

  可以验证，变换后的势 $(\varphi', \bm{A}')$ 描述的电磁场 $(\bm{E}', \bm{B}')$ 与原场完全相同：

  $$
  \bm{B}' = \nabla \times (\bm{A} + \nabla \psi) = \nabla \times \bm{A} + \nabla \times \nabla \psi = \bm{B}
  $$

  $$
  \bm{E}' = - \nabla (\varphi - \frac{\partial \psi}{\partial t}) - \frac{\partial}{\partial t} (\bm{A} + \nabla \psi) = - \nabla \varphi + \nabla \frac{\partial \psi}{\partial t} - \frac{\partial \bm{A}}{\partial t} - \frac{\partial \nabla \psi}{\partial t} = \bm{E}
  $$

+ 规范变换与规范不变性：上述变换称为规范变换。物理规律（如麦克斯韦方程组、洛伦兹力公式）只涉及 $\bm{E}$ 和 $\bm{B}$，因此在规范变换下保持形式不变，这一性质称为规范不变性。

### 5.1.3 电磁势满足的微分方程

+ 将电磁势的表达式代入含源的麦克斯韦方程组：

  $$
  \nabla \cdot \bm{E} = \frac{\rho}{\varepsilon} \implies \nabla \cdot (- \nabla \varphi - \frac{\partial \bm{A}}{\partial t}) = \frac{\rho}{\varepsilon} \implies \nabla^2 \varphi + \frac{\partial}{\partial t} (\nabla \cdot \bm{A}) = - \frac{\rho}{\varepsilon}
  $$

  $$
  \nabla \times \bm{B} = \mu \bm{j} + \mu \varepsilon \frac{\partial \bm{E}}{\partial t} \implies \nabla \times (\nabla \times \bm{A}) = \mu \bm{j} + \mu \varepsilon \frac{\partial}{\partial t} (- \nabla \varphi - \frac{\partial \bm{A}}{\partial t})
  $$

  利用 $\nabla \times (\nabla \times \bm{A}) = \nabla (\nabla \cdot \bm{A}) - \nabla^2 \bm{A}$，整理得：

  $$
  \nabla^2 \bm{A} - \mu \varepsilon \frac{\partial^2 \bm{A}}{\partial t^2} - \nabla (\nabla \cdot \bm{A} + \mu \varepsilon \frac{\partial \varphi}{\partial t}) = - \mu \bm{j}
  $$

  此时方程中 $\varphi$ 和 $\bm{A}$ 还是耦合在一起的，难以求解。

+ 洛伦茨规范 (Lorenz Gauge)

  为了使方程解耦并具有对称性，采用洛伦茨规范条件：

  $$
  \nabla \cdot \bm{A} + \mu \varepsilon \frac{\partial \varphi}{\partial t} = 0
  $$

  达朗贝尔方程 (d'Alembert Equations)：在洛伦茨规范下，电磁势满足一组非齐次波动方程：

  $$
  \nabla^2 \bm{A} - \mu \varepsilon \frac{\partial^2 \bm{A}}{\partial t^2} = - \mu \bm{j}, ~~~ \nabla^2 \varphi - \mu \varepsilon \frac{\partial^2 \varphi}{\partial t^2} = - \frac{\rho}{\varepsilon}
  $$

  或者引入达朗贝尔算符 $\Box^2 = \nabla^2 - \mu \varepsilon \frac{\partial^2}{\partial t^2}$，简写为：

  $$
  \Box^2 \bm{A} = - \mu \bm{j}, ~~~ \Box^2 \varphi = - \frac{\rho}{\varepsilon}
  $$

  其中波速 $v = 1/\sqrt{\mu \varepsilon}$。在真空中，$v=c$。这组方程表明，变化的电荷和电流是产生电磁波的源，电磁势以波动形式传播。洛伦茨规范在处理辐射问题时特别方便。

+ 库仑规范 (Coulomb Gauge)

  规定矢势的散度为零：

  $$
  \nabla \cdot \bm{A} = 0
  $$

  这与静磁场中的规范条件一致。

  势方程：
  代入 $\nabla^2 \varphi + \frac{\partial}{\partial t} (\nabla \cdot \bm{A}) = - \frac{\rho}{\varepsilon}$，得到标势方程：

  $$
  \nabla^2 \varphi = - \frac{\rho}{\varepsilon}
  $$

  这是熟悉的泊松方程。其解为瞬时库仑势：

  $$
  \varphi(\bm{r}, t) = \frac{1}{4\pi\varepsilon} \int \frac{\rho(\bm{r}', t)}{|\bm{r} - \bm{r}'|} dV'
  $$

  这意味着 $\varphi$ 随 $\rho$ 瞬间变化，没有推迟效应。但这并不意味着物理信号超光速传播，因为 $\bm{E}$ 还包含 $-\partial \bm{A}/\partial t$，这一项会抵消 $\varphi$ 中的瞬时效应。矢势方程变为：

  $$
  \nabla^2 \bm{A} - \mu \varepsilon \frac{\partial^2 \bm{A}}{\partial t^2} = - \mu \bm{j} + \mu \varepsilon \nabla \frac{\partial \varphi}{\partial t} = - \mu (\bm{j} - \varepsilon \nabla \frac{\partial \varphi}{\partial t})
  $$

## 5.2 推迟势

### 5.2.1 推迟势解

+ 重抄标势 $\varphi$ 满足的达朗贝尔方程如下：

  $$
  \nabla^2 \varphi - \frac{1}{c^2} \frac{\partial^2 \varphi}{\partial t^2} = - \frac{\rho}{\varepsilon_0}
  $$

  其中，电荷密度 $\rho(\bm{r},t)$ 给定。由方程的线性性质，我们可以使用叠加原理，即将带电体划分为许多电荷元，分别求出各个电荷元的贡献之后叠加，最终求得解。为此，考察位于 $\bm{r}'$ 的电荷元，体积为 $dV'$，电量为

  $$
  Q(t) = \rho(\bm{r}', t) dV'
  $$

  该电荷元可视作“点电荷”，对应的电荷密度分布可用 $\delta$ 函数表述：

  $$
  \rho'(\bm{r}, t) = Q(t)\delta(\bm{r} - \bm{r}')
  $$

  将 $\rho'$ 代入达朗贝尔方程，我们求解该点电荷产生的微元势 $\varphi'$。为了便于求解，将坐标原点移至电荷元所在位置 $\bm{r}'$，相对场点 $\bm{r}$ 的距离为 $R = |\bm{r} - \bm{r}'|$。此时方程变为（除了在原点 $R=0$ 处）：

  $$
  \frac{1}{R^2} \frac{\partial}{\partial R} (R^2 \frac{\partial \varphi'}{\partial R}) - \frac{1}{c^2} \frac{\partial^2 \varphi'}{\partial t^2} = 0 \quad (R \neq 0)
  $$

  引入代换 $\varphi' = \frac{u(R, t)}{R}$，方程简化为一维波动方程：

  $$
  \frac{\partial^2 u}{\partial R^2} - \frac{1}{c^2} \frac{\partial^2 u}{\partial t^2} = 0
  $$

  其通解为向外传播的波 $f(t - R/c)$ 和向内传播的波 $g(t + R/c)$ 的叠加。对于点源辐射问题，根据因果律，我们只取向外传播的发散波，即：

  $$
  \varphi'(R, t) = \frac{f(t - R/c)}{R}
  $$

  为了确定函数 $f$，我们需要利用原点附近的性质。在 $R \to 0$ 的极小区域内，推迟时间 $t - R/c \approx t$，推迟效应可以忽略，方程应退化为静电场的泊松方程。对以源点为球心、半径为 $\xi$ 的小球体积分达朗贝尔方程：

  $$
  \iiint_{R \le \xi} \nabla^2 \varphi' dV - \frac{1}{c^2} \iiint_{R \le \xi} \frac{\partial^2 \varphi'}{\partial t^2} dV = - \frac{Q(t)}{\varepsilon_0}
  $$

  当 $\xi \to 0$ 时，左边第二项体积分趋于零（因被积函数有限），第一项利用高斯公式转化为面积分：

  $$
  \iiint \nabla^2 \varphi' dV = \oint \nabla \varphi' \cdot d\bm{\sigma} = \oint \frac{\partial}{\partial R} \left( \frac{f(t)}{R} \right) R^2 d\Omega = \oint \left( -\frac{f(t)}{R^2} \right) R^2 d\Omega = -4\pi f(t)
  $$

  于是有：

  $$
  -4\pi f(t) = - \frac{Q(t)}{\varepsilon_0} \quad \implies \quad f(t) = \frac{Q(t)}{4\pi \varepsilon_0}
  $$

  将 $f(t)$ 代回，得到点电荷的推迟标势：

  $$
  \varphi'(\bm{r}, t) = \frac{Q(t - R/c)}{4\pi\varepsilon_0 R}
  $$

  推迟势的积分表达式：
  对所有电荷元积分，得到总的标势：

  $$
  \varphi(\bm{r}, t) = \frac{1}{4\pi\varepsilon_0} \iiint \frac{\rho(\bm{r}', t - R/c)}{R} dV'
  $$

  同理，由矢势满足的达朗贝尔方程 $\Box^2 \bm{A} = -\mu_0 \bm{j}$，可直接写出矢势的解：

  $$
  \bm{A}(\bm{r}, t) = \frac{\mu_0}{4\pi} \iiint \frac{\bm{j}(\bm{r}', t - R/c)}{R} dV'
  $$

  可以验证这样的解同时满足洛伦茨条件。

## 5.3 谐振荡电流的电磁场

+ 本节利用推迟势公式，由给定的电荷和电流密度分布计算电磁势和电磁场。

### 5.3.1 电荷和电流密度的傅里叶积分表示

+ 随时间任意变化的场源，可通过傅里叶变换，分解为不同频率、随时间作简谐变化的场源分量。傅里叶变换公式如下：

  $$
  \rho(\bm{r}, t) = \int_{-\infty}^{\infty} \rho_\omega(\bm{r}) e^{-i\omega t} d\omega, ~~~ \bm{j}(\bm{r}, t) = \int_{-\infty}^{\infty} \bm{j}_\omega(\bm{r}) e^{-i\omega t} d\omega
  $$

  其中，$\rho_\omega$ 和 $\bm{j}_\omega$ 分别为单位频率间隔的谐振荡电荷和电流密度的振幅。基于电磁势方程的线性性质，可分别求出各谐振荡场源分量的电磁势，然后叠加起来，得到随时间任意变化的场源的电磁势。因此，下面的分析限于谐振荡场源的情况。

### 5.3.2 谐振荡场源的电磁场

+ 将谐振荡电荷和电流密度表示为

  $$
  \rho(\bm{r}, t) = \rho_\omega(\bm{r}) e^{-i\omega t}, ~~~ \bm{j}(\bm{r}, t) = \bm{j}_\omega(\bm{r}) e^{-i\omega t}
  $$

  其中，振幅 $\rho_\omega(\bm{r})$，$\bm{j}_\omega(\bm{r})$ 可以为复数矢量。

+ 推迟势的时谐形式：
 
  将上述场源代入推迟势公式，注意到推迟时间 $t' = t - R/c$，有 $e^{-i\omega t'} = e^{-i\omega(t - R/c)} = e^{ikR} e^{-i\omega t}$，其中 $k = \omega/c$ 为波数。
  于是，电磁势的时谐振幅 $\varphi_\omega$ 和 $\bm{A}_\omega$ 满足：

  $$
  \varphi(\bm{r}, t) = \varphi_\omega(\bm{r}) e^{-i\omega t}, ~~~ \bm{A}(\bm{r}, t) = \bm{A}_\omega(\bm{r}) e^{-i\omega t}
  $$

  $$
  \varphi_\omega(\bm{r}) = \frac{1}{4\pi\varepsilon_0} \int_V \frac{\rho_\omega(\bm{r}') e^{ikR}}{R} dV'
  $$

  $$
  \bm{A}_\omega(\bm{r}) = \frac{\mu_0}{4\pi} \int_V \frac{\bm{j}_\omega(\bm{r}') e^{ikR}}{R} dV'
  $$

  这里 $R = |\bm{r} - \bm{r}'|$。因子 $e^{ikR}$ 体现了推迟效应。

+ 电磁场的计算：

  得到 $\bm{A}_\omega$ 后，可计算磁场：

  $$
  \bm{B}_\omega = \nabla \times \bm{A}_\omega
  $$

  在洛伦茨规范下，电场可由安培定律的推广形式 $\nabla \times \bm{H} = \bm{j} - i\omega \varepsilon_0 \bm{E}$ 或直接由 $\bm{E} = i\frac{c}{k} \nabla \times \bm{B}$（源外区域）求得。更通用的公式是：

  $$
  \bm{E}_\omega = i\frac{c}{k} \nabla \times \bm{B}_\omega = \frac{i c}{\omega} \nabla \times (\nabla \times \bm{A}_\omega) \quad (\text{源外，}\bm{j}=0)
  $$

### 5.3.3 近区、远区和小场源近似

+ 对于受限在有限区域 $V'$ 内的场源（尺度为 $l$），我们要计算距离源中心 $r$ 处的场。涉及三个长度参数：

  1. 场源尺度 $l$。

  2. 波长 $\lambda = 2\pi/k$。

  3. 考察点距离 $r$。

  通常假设 $r \gg l$（场点在源外）。

  1. 近区 (Near Zone)： $r \ll \lambda$ (即 $kr \ll 1$)。

  此时 $e^{ikR} \approx 1$。推迟势退化为瞬时势（静电势和静磁矢势形式）：

  $$
  \varphi_\omega \approx \frac{1}{4\pi\varepsilon_0} \int \frac{\rho_\omega}{R} dV', ~~~ \bm{A}_\omega \approx \frac{\mu_0}{4\pi} \int \frac{\bm{j}_\omega}{R} dV'
  $$

  在近区，电磁场主要表现为准静态场，随时间变化，但推迟效应不明显。

  2. 远区 (Far Zone / Radiation Zone)： $r \gg \lambda$ (即 $kr \gg 1$) 且 $r \gg l$。

  此时必须考虑相位因子 $e^{ikR}$。对 $R$ 进行近似：

  $$
  R = |\bm{r} - \bm{r}'| \approx r - \hat{\bm{k}} \cdot \bm{r}'
  $$

  其中 $\hat{\bm{k}} = \bm{r}/r$ 是径向单位矢量。

  在分母中，取 $R \approx r$（振幅近似）。

  在指数中，取 $kR \approx kr - k \hat{\bm{k}} \cdot \bm{r}' = kr - \bm{k} \cdot \bm{r}'$（相位近似，不能略去第二项，因为它可能引起明显的相位差）。

  于是矢势在远区的表达式为：

  $$
  \bm{A}_\omega(\bm{r}) \approx \frac{\mu_0 e^{ikr}}{4\pi r} \int \bm{j}_\omega(\bm{r}') e^{-i \bm{k} \cdot \bm{r}'} dV'
  $$

  3. 小场源近似： $l \ll \lambda$ (即 $kl \ll 1$)。

  这对应于电多极展开。因为 $\bm{k} \cdot \bm{r}' \le kl \ll 1$，可以对指数项展开：

  $$
  e^{-i \bm{k} \cdot \bm{r}'} \approx 1 - i \bm{k} \cdot \bm{r}' + \frac{1}{2} (-i \bm{k} \cdot \bm{r}')^2 + \dots
  $$

  这将导出电偶极辐射（第一项）、磁偶极和电四极辐射（第二项）等。

### 5.3.4 辐射电磁场及其特性

+ 在远区，电磁势表现为向外传播的球面波：$\bm{A}_\omega \sim \frac{e^{ikr}}{r} \bm{f}(\theta, \phi)$。利用 $\nabla \approx i \bm{k}$（只对 $e^{ikr}$ 作用，忽略 $1/r$ 的高阶导数），可得：

  $$
  \bm{B}_\omega = \nabla \times \bm{A}_\omega \approx i \bm{k} \times \bm{A}_\omega
  $$

  $$
  \bm{E}_\omega = \frac{i c}{k} \nabla \times \bm{B}_\omega \approx - \frac{c}{k} \bm{k} \times (\bm{k} \times \bm{A}_\omega) = c (\bm{B}_\omega \times \hat{\bm{k}})
  $$

  可以看出辐射电磁场有以下特性：

  1. 在该近似下 $\bm{E}, \bm{B}, \hat{\bm{k}}$ 构成右手正交系，且都与传播方向 $\hat{\bm{k}}$ 垂直（横波）。

  2. $|\bm{E}| = c |\bm{B}|$。

  3.振幅随距离按 $1/r$ 衰减（这是辐射场的特征，保证积分能量有限）。

### 5.3.5 辐射功率及辐射功率角分布

+ 对于时谐场，时间平均的能流密度为：

  $$
  \overline{\bm{S}} = \frac{1}{2} \text{Re}(\bm{E}_\omega \times \bm{H}_\omega^*) = \frac{1}{2\mu_0} \text{Re}(\bm{E}_\omega \times \bm{B}_\omega^*)
  $$

  代入辐射场公式，得：

  $$
  \overline{\bm{S}} = \frac{c}{2\mu_0} |\bm{B}_\omega|^2 \hat{\bm{k}} = \frac{1}{2 c \mu_0} |\bm{E}_\omega|^2 \hat{\bm{k}}
  $$

  能流沿径向向外。

  单位立体角内的辐射功率（辐射强度）：

  $$
  \frac{dP}{d\Omega} = r^2 \overline{S} = \frac{c r^2}{2\mu_0} |\bm{B}_\omega|^2
  $$

  总辐射功率：

  $$
  P = \oint \frac{dP}{d\Omega} d\Omega
  $$

  对于非辐射场（如库仑场 $\sim 1/r^2$），$S \sim 1/r^4$，积分功率 $P \to 0$（当 $r \to \infty$）。只有 $1/r$ 的辐射场才能将能量带到无穷远处。

## 5.4 电偶极、磁偶极和电四极辐射

+ 在 **小场源近似** ($l \ll \lambda$, 即 $kl \ll 1$) 下，我们可以对推迟势公式中的相位因子 $e^{-i\bm{k}\cdot\bm{r}'}$ 进行泰勒展开：

  $$
  e^{-i\bm{k}\cdot\bm{r}'} = 1 - i\bm{k}\cdot\bm{r}' + \frac{1}{2}(-i\bm{k}\cdot\bm{r}')^2 + \cdots
  $$

  将此展开式代入远区矢势公式 $\bm{A}(\bm{r}) = \frac{\mu_0 e^{ikr}}{4\pi r} \int \bm{j}(\bm{r}') e^{-i\bm{k}\cdot\bm{r}'} dV'$，可得到不同阶数的辐射项。

### 5.4.1 电偶极辐射

+ 取展开式的第一项（$1$），对应零阶近似：

  $$
  \bm{A}(\bm{r}) = \frac{\mu_0 e^{ikr}}{4\pi r} \int \bm{j}(\bm{r}') dV'
  $$

  利用恒等式 $\int \bm{j} dV = \frac{d\bm{p}}{dt} = -i\omega \bm{p}$（其中 $\bm{p} = \int \rho \bm{r}' dV'$ 为电偶极矩），得：

  $$
  \bm{A}(\bm{r}) = -\frac{i\omega\mu_0}{4\pi r} e^{ikr} \bm{p}
  $$

  如果我们在时域中表示（即不限于时谐场），注意到 $-i\omega \bm{p} \to \dot{\bm{p}}(t-r/c)$，则矢势为：

  $$
  \bm{A}(\bm{r}, t) = \frac{\mu_0}{4\pi r} \dot{\bm{p}}(t-r/c)
  $$

+ 利用 $\bm{B} = i\bm{k} \times \bm{A}$ 和 $\bm{E} = c \bm{B} \times \hat{\bm{k}}$（这里 $\hat{\bm{k}}=\bm{n}=\bm{r}/r$），并注意到 $k=\omega/c$，求得时谐场的辐射场：

  $$
  \bm{B} = \frac{\mu_0 \omega^2}{4\pi c} \frac{e^{ikr}}{r} (\hat{\bm{k}} \times \bm{p})
  $$

  $$
  \bm{E} = \frac{\mu_0 \omega^2}{4\pi} \frac{e^{ikr}}{r} (\hat{\bm{k}} \times \bm{p}) \times \hat{\bm{k}}
  $$

  若使用时域表示，注意到 $\omega^2 \bm{p} \leftrightarrow -\ddot{\bm{p}}$，我们得到含 $\ddot{\bm{p}}$ 的表达式（即赫兹公式）：

  $$
  \bm{B}(\bm{r}, t) = \frac{\mu_0}{4\pi c r} \ddot{\bm{p}} \times \hat{\bm{k}}
  $$

  $$
  \bm{E}(\bm{r}, t) = \frac{\mu_0}{4\pi r} [\ddot{\bm{p}}(t') \times \hat{\bm{k}}] \times \hat{\bm{k}}
  $$

  其中 $t' = t - r/c$。这表明辐射场正比于电偶极矩的二阶导数（加速度）。

+ 平均能流密度（坡印廷矢量）：

  $$
  \overline{\bm{S}} = \frac{c}{2\mu_0} |\bm{B}|^2 \hat{\bm{k}} = \frac{\mu_0 |\ddot{\bm{p}}(t')|^2}{32 \pi^2 c} \frac{\sin^2\theta}{r^2} \hat{\bm{k}}
  $$

  辐射功率角分布：

  $$
  \frac{dP}{d\Omega} = r^2 \overline{S} = \frac{\mu_0 |\ddot{\bm{p}}(t')|^2}{32 \pi^2 c} \sin^2\theta
  $$

  总辐射功率：

  $$
  P = \oint \frac{dP}{d\Omega} d\Omega = \frac{\mu_0 \omega^4 p^2}{12 \pi c}
  $$

### 5.4.2 磁偶极辐射

+ 考虑展开式的第二项 $-i\bm{k}\cdot\bm{r}'$，矢势积分项为：

  $$
  \bm{A}^{(1)}(\bm{r}) = -\frac{i\mu_0 k}{4\pi r} e^{ikr} \int (\hat{\bm{k}}\cdot\bm{r}') \bm{j}(\bm{r}') dV'
  $$

  利用矢量恒等式，我们将被积函数中的矢量 $\bm{J}_{\bm{k}} = (\hat{\bm{k}}\cdot\bm{r}') \bm{j}$ 分解为反对称部分和对称部分：

  $$
  (\hat{\bm{k}}\cdot\bm{r}') \bm{j} = \frac{1}{2} [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} - (\hat{\bm{k}}\cdot\bm{j})\bm{r}'] + \frac{1}{2} [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} + (\hat{\bm{k}}\cdot\bm{j})\bm{r}']
  $$

  其中第一项是反对称部分（对应磁偶极子）：

  $$
  \frac{1}{2} [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} - (\hat{\bm{k}}\cdot\bm{j})\bm{r}'] = \frac{1}{2} (\bm{r}' \times \bm{j}) \times \hat{\bm{k}} = - \frac{1}{2} \hat{\bm{k}} \times (\bm{r}' \times \bm{j})
  $$

  第二项是对称部分（对应电四极子）：

  $$
  \frac{1}{2} [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} + (\hat{\bm{k}}\cdot\bm{j})\bm{r}']
  $$

+ 先讨论磁偶极项，将反对称部分代入积分，并定义磁偶极矩 $\bm{m} = \frac{1}{2} \int (\bm{r}' \times \bm{j}) dV'$，得到磁偶极辐射的矢势：

  $$
  \bm{A}_{mag}(\bm{r}) = \frac{ik\mu_0}{4\pi r} e^{ikr} (\hat{\bm{k}} \times \bm{m}) = \frac{\mu_0}{4\pi c r} e^{ikr} (\dot{\bm{m}} \times \hat{\bm{k}})
  $$

  辐射场：

  $$
  \bm{B} = i\bm{k} \times \bm{A} = \frac{\mu_0}{4\pi c^2} \frac{e^{ikr}}{r} (\ddot{\bm{m}} \times \hat{\bm{k}}) \times \hat{\bm{k}}
  $$

  $$
  \bm{E} = c \bm{B} \times \hat{\bm{k}} = -\frac{\mu_0}{4\pi c} \frac{e^{ikr}}{r} (\ddot{\bm{m}} \times \hat{\bm{k}})
  $$

+ 能流密度与辐射功率，平均能流密度（坡印廷矢量）$\overline{\bm{S}} = \frac{1}{2\mu_0} \text{Re}(\bm{E} \times \bm{B}^*)$：

  $$
  \overline{\bm{S}} = \frac{\mu_0 \omega^4}{32 \pi^2 c^3 r^2} |\bm{m} \times \hat{\bm{k}}|^2 \hat{\bm{k}} = \frac{\mu_0 \omega^4 m^2}{32 \pi^2 c^3 r^2} \sin^2\theta \, \hat{\bm{k}}
  $$

  其中 $\theta$ 为 $\hat{\bm{k}}$ 与 $\bm{m}$ 的夹角。总辐射功率：

  $$
  P = \oint \overline{S} r^2 d\Omega = \frac{\mu_0 \omega^4 m^2}{12 \pi c^3}
  $$

### 5.4.3 电四极辐射

+ 考虑被积函数中的对称部分：

  $$
  \bm{A}_{elec}^{(1)}(\bm{r}) = -\frac{i\mu_0 k}{8\pi r} e^{ikr} \int [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} + (\hat{\bm{k}}\cdot\bm{j})\bm{r}'] dV'
  $$

  利用恒等式 $\nabla' \cdot (x'_i x'_j \bm{j}) = x'_i x'_j (i\omega \rho) + x'_i j_j + x'_j j_i$ 对全空间积分为0（第三章中有证），故有：

  $$
  \int (x'_i j_j + x'_j j_i) dV' = -i\omega \int x'_i x'_j \rho dV'
  $$

  将被积矢量的分量形式写出：

  $$
  [(\hat{\bm{k}}\cdot\bm{r}')\bm{j} + (\hat{\bm{k}}\cdot\bm{j})\bm{r}']_\alpha = k_\beta r'_\beta j_\alpha + k_\beta j_\beta r'_\alpha = k_\beta (r'_\beta j_\alpha + j_\beta r'_\alpha)
  $$

  代入积分并利用上述关系：

  $$
  \int (r'_\beta j_\alpha + j_\beta r'_\alpha) dV' = -i\omega \int r'_\beta r'_\alpha \rho dV'
  $$

  于是矢势变为：

  $$
  \bm{A}_{elec}^{(1)}(\bm{r}) = -\frac{\mu_0 \omega k}{8\pi r} e^{ikr} \hat{\bm{k}} \cdot \left( \int \rho \bm{r}' \bm{r}' dV' \right)
  $$

  引入无迹的电四极矩张量 $\bm{D} = \int \rho (3\bm{r}'\bm{r}' - r'^2 \bm{I}) dV'$。由于 $\hat{\bm{k}} \cdot (r'^2 \bm{I}) = r'^2 \hat{\bm{k}}$ 是纵向分量，在计算 $\bm{B} = i\bm{k} \times \bm{A}$ 时会被叉乘消去（或对辐射场无贡献），因此可以用 $\bm{D}/3$ 替换积分项 $\int \rho \bm{r}' \bm{r}' dV'$。最终得到电四极辐射的矢势：

  $$
  \bm{A}(\bm{r}) = -\frac{\mu_0 \omega k}{24\pi r} e^{ikr} \hat{\bm{k}} \cdot \bm{D} = \frac{\mu_0}{24\pi c r} e^{ikr} \hat{\bm{k}} \cdot \ddot{\bm{D}}
  $$

  (注：这里系数可能因 $\bm{D}$ 定义不同而有倍数差异，此处按 $\bm{D}_{ij} = \int \rho (3x'_i x'_j - r'^2 \delta_{ij}) dV'$ 的常见定义，通常系数为 $1/24$ 或类似)

+ 利用 $\nabla \approx i\bm{k}$ 计算场：

  $$
  \bm{B} = i \bm{k} \times \bm{A} = \frac{\mu_0 k^2}{24 \pi r} e^{ikr} (\hat{\bm{k}} \cdot \bm{D}) \times \hat{\bm{k}} 
  $$

  $$
  \bm{E} = c \bm{B} \times \hat{\bm{k}} = \frac{c \mu_0 k^2}{24 \pi r} e^{ikr} [(\hat{\bm{k}} \cdot \bm{D}) \times \hat{\bm{k}}] \times \hat{\bm{k}}
  $$

  平均能流密度（坡印廷矢量）：

  $$
  \overline{\bm{S}} = \frac{c}{2\mu_0} |\bm{B}|^2 \hat{\bm{k}} = \frac{\mu_0 \omega^6}{1152 \pi^2 c^5 r^2} |(\hat{\bm{k}} \cdot \bm{D}) \times \hat{\bm{k}}|^2 \hat{\bm{k}}
  $$

  总辐射功率（对立体角积分）：

  $$
  P = \frac{\mu_0 \omega^6}{1440 \pi c^5} \sum_{i,j} |D_{ij}|^2
  $$

  这里的 $\sum |D_{ij}|^2$ 是张量 $\bm{D}$ 的模的平方（双点积 $\bm{D}:\bm{D}^*$）。电四极辐射功率与频率的六次方 $\omega^6$ 成正比。

&nbsp;

&nbsp;

&nbsp;

# 第6章 运动电荷的辐射

## 6.1 李纳-维谢尔势 (Liénard-Wiechert Potentials)

### 6.1.1 数学准备

+ 设有一个电量为 $q$ 的点电荷，其运动轨迹由位置矢量 $\bm{r}_0(t)$ 描述，速度为 $\bm{v}(t) = \dot{\bm{r}}_0(t)$。我们要计算该运动电荷在场点 $\bm{r}$、时刻 $t$ 产生的电磁势 $\varphi(\bm{r}, t)$ 和 $\bm{A}(\bm{r}, t)$。利用 $\delta$ 函数，运动点电荷的源密度可表示为：

  $$
  \rho(\bm{r}', t') = q \delta(\bm{r}' - \bm{r}_0(t'))
  $$

  $$
  \bm{j}(\bm{r}', t') = q \bm{v}(t') \delta(\bm{r}' - \bm{r}_0(t'))
  $$

  代入第5章推导的推迟势公式：

  $$
  \varphi(\bm{r}, t) = \frac{1}{4\pi\varepsilon_0} \int \frac{\rho(\bm{r}', t - R/c)}{R} dV'
  $$

  其中 $R = |\bm{r} - \bm{r}'|$。由于被积函数中的 $\rho$ 包含推迟时间 $t' = t - R/c$，这使得对 $\bm{r}'$ 的空间积分变得复杂（因为 $\delta$ 函数中的 $\bm{r}_0$ 也是 $\bm{r}'$ 的函数）。为了简化积分，我们引入关于时间的积分，利用 $\delta$ 函数的性质：

  $$
  \varphi(\bm{r}, t) = \frac{1}{4\pi\varepsilon_0} \iint \frac{\rho(\bm{r}', t')}{R} \delta(t' - t + R/c) dV' dt'
  $$

### 6.1.2 李纳-维谢尔势

+ 将 $\rho(\bm{r}', t') = q \delta(\bm{r}' - \bm{r}_0(t'))$ 代入双重积分公式：

  $$
  \varphi(\bm{r}, t) = \frac{q}{4\pi\varepsilon_0} \int dt' \int dV' \frac{\delta(\bm{r}' - \bm{r}_0(t'))}{R} \delta(t' - t + R/c)
  $$

  先完成对 $dV'$ 的空间积分。由于 $\delta(\bm{r}' - \bm{r}_0(t'))$ 的存在，只需将 $\bm{r}'$ 替换为 $\bm{r}_0(t')$，此时 $R$ 变为 $R(t') = |\bm{r} - \bm{r}_0(t')|$。得到：

  $$
  \varphi(\bm{r}, t) = \frac{q}{4\pi\varepsilon_0} \int_{-\infty}^{\infty} \frac{\delta(t' - t + R(t')/c)}{R(t')} dt'
  $$

  利用 $\delta$ 函数的性质 $\int g(x) \delta(f(x)) dx = \sum_i \frac{g(x_i)}{|f'(x_i)|}$，其中 $x_i$ 是 $f(x)=0$ 的根。令 $f(t') = t' - t + R(t')/c$。方程 $f(t')=0$ 即 $t' = t - R(t')/c$，这意味着 $t'$ 正是推迟时刻。由于电荷运动速度 $v < c$，该方程只有唯一解。 计算导数（将$t$视为常数）：

  $$
  \frac{df}{dt'} = 1 + \frac{1}{c} \frac{dR(t')}{dt'}
  $$

  其中 $R(t') = \sqrt{(\bm{r} - \bm{r}_0(t'))^2}$，对其求导得：

  $$
  \frac{dR(t')}{dt'} = \frac{1}{2R} 2(\bm{r} - \bm{r}_0) \cdot (-\bm{v}) = - \frac{\bm{R} \cdot \bm{v}}{R} = - \bm{n} \cdot \bm{v}
  $$

  这里 $\bm{R} = \bm{r} - \bm{r}_0(t')$，$\bm{n} = \bm{R}/R$ 是从源点指向场点的单位矢量。于是导数为：

  $$
  \frac{df}{dt'} = 1 - \frac{\bm{n} \cdot \bm{v}}{c} = 1 - \bm{n} \cdot \bm{\beta}
  $$

  其中 $\bm{\beta} = \bm{v}/c$。将上述结果代入积分，得到标势 $\varphi$。同理可得矢势 $\bm{A}$。这组势称为李纳-维谢尔势 (Liénard-Wiechert Potentials)：

  $$
  \varphi(\bm{r}, t) = \frac{q}{4\pi\varepsilon_0} \frac{1}{R(1 - \bm{n} \cdot \bm{\beta})} \bigg|_{t'}
  $$

  $$
  \bm{A}(\bm{r}, t) = \frac{\mu_0 q}{4\pi} \frac{\bm{v}}{R(1 - \bm{n} \cdot \bm{\beta})} \bigg|_{t'} = \frac{\bm{v}(t')}{c^2} \varphi(\bm{r}, t)
  $$

  注意：公式右端的所有物理量（$R, \bm{n}, \bm{v}, \bm{\beta}$）都必须在推迟时刻 $t'$ 取值，其中 $t'$ 由隐函数方程 $t' = t - R(t')/c$ 确定。

### 6.1.3 物理分析

+ 分母中的因子 $K = 1 - \bm{n} \cdot \bm{\beta}$ 称为多普勒因子。它反映了源的运动对势场的影响。

  >当电荷向着观察者运动时 ($\bm{n} \cdot \bm{v} > 0$)，$K < 1$，势场增强。
  >
  >当电荷背离观察者运动时 ($\bm{n} \cdot \bm{v} < 0$)，$K > 1$，势场减弱。
  >
  >当 $v \to c$ 且电荷正对观察者运动时，势场趋于无穷大（激波效应）。

  与静止点电荷的势 ($\varphi \sim 1/R$) 相比，运动电荷的势不仅取决于距离 $R$，还取决于速度 $\bm{v}$ 以及速度与观察方向的夹角。这体现了相对论效应在电动力学中的自然涌现。

## 6.2 运动电荷的电磁场

+ 已知运动电荷的势（李纳-维谢尔势），电磁场由下式给出：

  $$
  \bm{E} = -\nabla \varphi - \frac{\partial \bm{A}}{\partial t}
  $$

  $$
  \bm{B} = \nabla \times \bm{A}
  $$

### 6.2.1 数学准备：关于推迟时刻的导数

+ 势的表达式是推迟时刻 $t'$ 的函数，而 $t'$ 又是 $(\bm{r}, t)$ 的隐函数。因此，计算 $\nabla$ 和 $\partial/\partial t$ 时需要利用链式法则。

  1. 对时间的偏导数 $\partial t'/\partial t$：
    
    对 $t' = t - R(t')/c$ 两边求 $\partial/\partial t$：

    $$
    \frac{\partial t'}{\partial t} = 1 - \frac{1}{c} \frac{\partial R}{\partial t'} \frac{\partial t'}{\partial t}
    $$

    利用 $\frac{\partial R}{\partial t'} = -\bm{n} \cdot \bm{v}$（见 6.1.2 节），得：

    $$
    \frac{\partial t'}{\partial t} = 1 + \bm{n} \cdot \bm{\beta} \frac{\partial t'}{\partial t} \implies \frac{\partial t'}{\partial t} = \frac{1}{1 - \bm{n} \cdot \bm{\beta}} = \frac{1}{K}
    $$

    其中 $K = 1 - \bm{n} \cdot \bm{\beta} = 1 - \frac{\bm{n} \cdot \bm{v}}{c}$。

  2. 对空间的梯度 $\nabla t'$：

    对 $t' = t - R(t')/c$ 两边求 $\nabla$：

    $$
    \nabla t' = - \frac{1}{c} (\nabla R)_{t'} - \frac{1}{c} \frac{\partial R}{\partial t'} \nabla t'
    $$

    利用 $(\nabla R)_{t'} = \nabla |\bm{r} - \bm{r}_0(t')| = \bm{n}$，得：

    $$
    \nabla t' = - \frac{\bm{n}}{c} + (\bm{n} \cdot \bm{\beta}) \nabla t' \implies \nabla t' = - \frac{\bm{n}}{c(1 - \bm{n} \cdot \bm{\beta})} = - \frac{\bm{n}}{cK}
    $$

  3. 其他辅助公式：

    $$
    \nabla R = \bm{n} + \frac{\partial R}{\partial t'} \nabla t' = \bm{n} - (\bm{n} \cdot \bm{v}) \frac{\bm{n}}{cK} = \bm{n} (1 - \frac{\bm{n} \cdot \bm{\beta}}{K}) = \frac{\bm{n}}{K}
    $$

    $$
    \frac{\partial R}{\partial t} = \frac{\partial R}{\partial t'} \frac{\partial t'}{\partial t} = - \frac{\bm{n} \cdot \bm{v}}{K}
    $$

    $$
    \nabla (\bm{n} \cdot \bm{\beta}) = \frac{\bm{\beta}}{R} - \frac{\bm{n}}{K} \left[\frac{\bm{n}\cdot\dot{\bm{\beta}}}{c} + \frac{\bm{n}\cdot\bm{\beta}}{R} - \frac{\beta^2}{R} \right]
    $$

### 6.2.2 李纳-维谢尔场公式

+ 利用上述导数公式，对势求导，经过繁琐但直接的代数运算，可得到运动电荷产生的电磁场公式。

  电场 $\bm{E}(\bm{r}, t)$：

  $$
  \bm{E}(\bm{r}, t) = \frac{q}{4\pi\varepsilon_0} \left[ \frac{\bm{n} - \bm{\beta}}{\gamma^2 K^3 R^2} \right]_{t'} + \frac{q}{4\pi\varepsilon_0 c} \left[ \frac{\bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}]}{K^3 R} \right]_{t'}
  $$

  其中 $\gamma = 1/\sqrt{1 - \beta^2}$ 为相对论因子，$\dot{\bm{\beta}} = \dot{\bm{v}}/c$ 是加速度项。

  磁场 $\bm{B}(\bm{r}, t)$：

  $$
  \bm{B}(\bm{r}, t) = \frac{1}{c} \bm{n}(t') \times \bm{E}(\bm{r}, t)
  $$

  磁场始终垂直于电场和推迟时刻的径向矢量 $\bm{n}$。

### 6.2.3 场的物理分析

+ 电场公式包含两部分，具有截然不同的物理性质：

  1. 速度场 (Velocity Field)：

    公式中的第一项：

    $$
    \bm{E}_{vel} = \frac{q}{4\pi\varepsilon_0} \frac{\bm{n} - \bm{\beta}}{\gamma^2 K^3 R^2}
    $$

    特点：

    >与加速度无关，只与速度 $\bm{\beta}$ 有关。
    >
    >随距离按 $1/R^2$ 衰减。
    >
    >它是依附于电荷并随电荷一起运动的场（“束缚场”）。对于匀速运动电荷，这就是其全部场。
    >
    >在低速极限 ($\beta \ll 1$) 下退化为库仑场。

  2. 加速度场 (Acceleration Field) / 辐射场 (Radiation Field)：

    公式中的第二项：

    $$
    \bm{E}_{rad} = \frac{q}{4\pi\varepsilon_0 c} \frac{\bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}]}{K^3 R}
    $$

    特点：

    >正比于加速度 $\dot{\bm{\beta}}$。只有加速运动的电荷才产生此项。
    >
    >随距离按 $1/R$ 衰减。
    >
    >由于衰减慢，它在远处占主导地位，并将能量带向无穷远，因此称为辐射场。
    >
    >它是横场：$\bm{E}_{rad}$ 垂直于 $\bm{n}$（由叉乘结构 $\bm{n} \times (\cdots)$ 可见）。

## 6.3 运动电荷的辐射功率与特性

+ 本节讨论运动电荷辐射能量的规律。我们仅关注辐射场 $\bm{E}_{rad}$（与 $1/R$ 成正比的项），因为只有它对流向无穷远处的净能量有贡献。

### 6.3.1 辐射总功率

+ 在远区，辐射场 $\bm{E}_{rad}$ 和 $\bm{B}_{rad}$ 相互垂直且垂直于径向 $\bm{n}$，且 $|\bm{E}_{rad}| = c |\bm{B}_{rad}|$。坡印廷矢量为：

  $$
  \bm{S}_{rad} = \frac{1}{\mu_0} \bm{E}_{rad} \times \bm{B}_{rad} = \frac{1}{\mu_0 c} |\bm{E}_{rad}|^2 \bm{n}
  $$

  代入 6.2 节得到的辐射场公式 $\bm{E}_{rad} = \frac{q}{4\pi\varepsilon_0 c} \frac{\bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}]}{K^3 R}$，得：

  $$
  \bm{S}_{rad}(\bm{r}, t) = \frac{\mu_0 q^2}{16\pi^2 c} \frac{1}{R^2} \frac{|\bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}]|^2}{(1 - \bm{n} \cdot \bm{\beta})^6} \bm{n}
  $$

  注意这里 $\bm{S}_{rad}$ 是场点时刻 $t$ 的能流密度矢量，方向沿径向 $\bm{n}$ 向外。

+ 计算辐射功率时，必须区分发射能量的时间间隔 $dt'$ 和接收能量的时间间隔 $dt$。考虑电荷在 $t'$ 时刻发出一个信号，在 $t' + dt'$ 时刻发出另一个信号。
  
  第一个信号到达观察点 $\bm{r}$ 的时刻是 $t = t' + \frac{R(t')}{c}$。

  第二个信号到达观察点的时刻是 $t + dt = (t' + dt') + \frac{R(t' + dt')}{c}$。

  因此，接收到的时间间隔 $dt$ 为：

  $$
  dt = dt' + \frac{1}{c} [R(t' + dt') - R(t')] \approx dt' + \frac{1}{c} \frac{dR}{dt'} dt'
  $$

  利用 $dR/dt' = - \bm{n} \cdot \bm{v}$（见 6.1.2 推导），可得：

  $$
  dt = dt' - \frac{\bm{n} \cdot \bm{v}}{c} dt' = (1 - \bm{n} \cdot \bm{\beta}) dt' = K dt'
  $$

  这表明：当电荷朝向观察者运动时 ($K < 1$)，接收到的辐射脉冲在时间上被压缩（功率变大）；反之则被拉伸。

+ 设电荷在 $dt'$ 时间内向立体角 $d\Omega$ 辐射出的能量为 $dW'$。这部分能量在观察者处的 $dt$ 时间内通过相应的面积 $dA = R^2 d\Omega$。根据能量守恒：$dW' = (\bm{S}_{rad} \cdot \bm{n} dA) dt$。我们关心的辐射功率 $P(t')$ 定义为电荷单位发射时间辐射出的能量：

  $$
  \frac{dP(t')}{d\Omega} = \frac{dW'}{dt' d\Omega} = \frac{(\bm{S}_{rad} \cdot \bm{n} R^2 d\Omega) dt}{dt' d\Omega} = (\bm{S}_{rad} \cdot \bm{n} R^2) \frac{dt}{dt'}
  $$

  将 $\frac{dt}{dt'} = K$ 代入，得：

  $$
  \frac{dP(t')}{d\Omega} = K R^2 (\bm{S}_{rad} \cdot \bm{n})
  $$

  这就是为什么在计算电荷自身的辐射功率时，需要乘以一个额外的因子 $K$。这个因子在物理上补偿了多普勒效应对能流密度的“稀释”或“浓缩”作用。

+ 总辐射功率：

  $$
  P(t') = \oint \frac{dP(t')}{d\Omega} d\Omega = \oint \bm{S}_{rad} \cdot \bm{n} \, K R^2 d\Omega
  $$

  1. 低速极限：拉莫尔公式 (Larmor Formula)

    当 $v \ll c$ ($\beta \to 0, K \to 1$) 时，辐射角分布较为简单。

    $$
    \bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}] \approx \bm{n} \times (\bm{n} \times \dot{\bm{\beta}}) = (\bm{n} \cdot \dot{\bm{\beta}}) \bm{n} - \dot{\bm{\beta}}
    $$

    其模平方为 $\dot{v}^2 - (\bm{n} \cdot \dot{\bm{v}})^2 = \dot{v}^2 \sin^2\theta$，其中 $\theta$ 是加速度 $\dot{\bm{v}}$ 与观察方向 $\bm{n}$ 的夹角。
    对立体角积分 $\int \sin^2\theta d\Omega = 8\pi/3$，得到经典的拉莫尔公式：

    $$
    P = \frac{\mu_0 q^2}{6\pi c} \dot{v}^2
    $$

    这表明低速运动电荷的辐射功率正比于加速度的平方。

  2. 任意速度：李纳推广公式 (Liénard's Generalization)

    对于高速运动，需对完整公式进行积分。利用相对论变换或直接积分可得：

    $$
    P = \frac{\mu_0 q^2 \gamma^6}{6\pi c} \left[ \dot{v}^2 - (\bm{\beta} \times \dot{\bm{v}})^2 \right]
    $$

    这就是相对论性的辐射功率公式。它表明辐射功率极其强烈地依赖于能量（通过 $\gamma^6$ 因子）。

### 6.3.2 辐射角分布与集束效应

+ 辐射场的角分布（即能量在不同方向上的集中程度）由能流密度公式中的角度相关项决定。单位立体角内的辐射功率（针对推迟时间 $t'$）：

  $$
  \frac{dP(t')}{d\Omega} = R^2 (\bm{S}_{rad} \cdot \bm{n}) K = \frac{\mu_0 q^2}{16\pi^2 c} \frac{|\bm{n} \times [(\bm{n} - \bm{\beta}) \times \dot{\bm{\beta}}]|^2}{(1 - \bm{n} \cdot \bm{\beta})^5}
  $$

  注意分母为 $K^5$（因为 $S_{rad}$ 含 $K^{-6}$，而时间变换乘了 $K$）。

  1. 对于低速情况 ($\beta \ll 1$)：

    分母 $K \approx 1$。辐射图样呈现为关于加速度轴对称的“面包圈”形状（$\sin^2\theta$ 分布），在垂直于加速度的方向辐射最强，沿加速度方向辐射为零。

  2. 高速情况 ($\beta \approx 1$) —— 辐射集束效应 (Beaming Effect)：
   
    当 $v \to c$ 时，分母 $(1 - \beta \cos\theta)^5$ 起主导作用。

    在 $\theta = 0$（正前方）附近，分母极小，辐射强度极大。

    辐射能量高度集中在速度 $\bm{v}$ 前方的一个极小的圆锥角内，半张角约为：

    $$
    \Delta \theta \sim \frac{1}{\gamma} = \sqrt{1 - \beta^2}
    $$

    这就像探照灯一样，随着粒子速度增加，辐射光锥变得越来越窄，能量密度极高。

### 6.3.3 两种典型的高速辐射

+ 根据加速度 $\dot{\bm{v}}$ 与速度 $\bm{v}$ 的方向关系，可以分为两种典型情况：

  1. 轫致辐射 (Bremsstrahlung)：$\dot{\bm{v}} \parallel \bm{v}$

    发生在带电粒子在直线运动中加速或减速（如电子撞击靶材）时。

    功率：代入李纳公式（$\bm{\beta} \times \dot{\bm{v}} = 0$）：

    $$
    P_\parallel = \frac{\mu_0 q^2 \gamma^6}{6\pi c} \dot{v}^2
    $$

    角分布：由于集束效应，辐射集中在运动方向的前方圆锥内。但在正前方 $\theta=0$ 处，由于 $\bm{n} \times (\bm{n} \times \dot{\bm{\beta}}) = 0$，辐射强度反而为零。因此辐射图样是一个空心的圆锥。

  2. 同步辐射 (Synchrotron Radiation)：$\dot{\bm{v}} \perp \bm{v}$

    发生在带电粒子做圆周运动（如在回旋加速器或磁场中）时。

    功率：代入李纳公式（$|\bm{\beta} \times \dot{\bm{v}}| = \beta \dot{v}$）：

    $$
    P_\perp = \frac{\mu_0 q^2 \gamma^4}{6\pi c} \dot{v}^2
    $$

  (注：此处形式化简利用了 $1-\beta^2 = 1/\gamma^2$。若比较相同外力下的辐射，由于 $\dot{v}_\perp \propto 1/\gamma$ 而 $\dot{v}_\parallel \propto 1/\gamma^3$，同步辐射功率远大于轫致辐射功率)。

  特性：

  >强方向性：极度集中在轨道切线方向。观察者只能在粒子扫过切点时看到短暂的强光脉冲。
  >
  >宽频谱：由于脉冲极短，频域上包含极宽的频谱（从射频到X射线）。
  >
  >高偏振：具有很强的线偏振特性。
  
  同步辐射既是高能粒子加速器的能量损耗机制（需克服的困难），也是一种极为优良的强光源（同步辐射光源）。

&nbsp;

&nbsp;

&nbsp;

# 第7章 狭义相对论

## 7.1 狭义相对论的时空观

### 7.1.1 相对论的基本假设

+ 爱因斯坦狭义相对论建立在两个基本公设之上：

  1. 相对性原理：物理定律在所有惯性参考系中都具有相同的形式。这意味着不存在“绝对静止”的参考系，任何力学或电磁学实验都无法区分一个惯性系是静止还是做匀速直线运动。

  2. 光速不变原理：在所有惯性系中，真空中的光速 $c$ 恒为常数（$c \approx 3 \times 10^8$ m/s），与光源或观察者的运动状态无关。

### 7.1.2 洛伦兹变换 (Lorentz Transformation)

+ 设有两个惯性系 $\Sigma$ 和 $\Sigma'$。$\Sigma'$ 系相对于 $\Sigma$ 系沿 $x$ 轴正方向以速度 $v$ 匀速运动。当 $t=t'=0$ 时，两坐标系原点重合。连接两时空坐标 $(x, y, z, t)$ 和 $(x', y', z', t')$ 的变换关系为洛伦兹变换：

  $$
  \begin{cases}
  x' = \gamma (x - vt) \\
  y' = y \\
  z' = z \\
  t' = \gamma (t - \frac{v}{c^2} x)
  \end{cases}
  $$

  其中引入两个无量纲参数：归一化速度：$\beta = \frac{v}{c}$，洛伦兹因子：$\gamma = \frac{1}{\sqrt{1 - \beta^2}}$ （当 $v < c$ 时，$\gamma \ge 1$）。其逆变换只需将 $v$ 换为 $-v$（即把带撇和不带撇的量互换）：

  $$
  \begin{cases}
  x = \gamma (x' + vt') \\
  y = y' \\
  z = z' \\
  t = \gamma (t' + \frac{v}{c^2} x')
  \end{cases}
  $$

  当 $v \ll c$ ($\beta \to 0, \gamma \to 1$) 时，洛伦兹变换退化为经典的伽利略变换。

### 7.1.3 相对论的时空效应

+ 由洛伦兹变换直接导出两个著名的运动学效应：

  1. 钟慢效应 (Time Dilation)：

    设在 $\Sigma'$ 系中同一地点 ($dx'=0$) 发生两个事件，时间间隔为固有时间 $d\tau = dt'$。在 $\Sigma$ 系中观测，这两个事件的时间间隔 $dt$ 为：

    $$
    dt = \gamma d\tau = \frac{d\tau}{\sqrt{1 - \beta^2}} \ge d\tau
    $$

    运动的时钟变慢。

  2. 尺缩效应 (Length Contraction)：

    设在 $\Sigma'$ 系中有一根静止的尺子，沿 $x'$ 轴放置，其固有长度为 $l_0 = dx'$。在 $\Sigma$ 系中观测（要求同时测量尺子两端，即 $dt=0$），其长度 $l = dx$ 满足：

    $$
    l = \frac{l_0}{\gamma} = l_0 \sqrt{1 - \beta^2} \le l_0
    $$

    运动的物体在运动方向上长度收缩。

  3. 同时的相对性：

    在 $\Sigma$ 系中不同地点同时发生的两个事件 ($dt=0, dx \neq 0$)，在 $\Sigma'$ 系中观测并不亦步亦趋：

    $$
    t'_2 - t'_1 = -\gamma \frac{v}{c^2} (x_2 - x_1) \neq 0
    $$

    这意味着“同时”不是绝对的，而是依赖于参考系的。

## 7.2 闵可夫斯基空间与四维矢量

+ 狭义相对论将空间和时间统一为一个四维连续区，称为闵可夫斯基空间 (Minkowski Space)。在此空间中，我们采用 $x_4 = ict$ 的虚时间形式，使得四维时空具有欧几里得度规。物理定律表现为四维张量方程，从而在形式上显式地展现出洛伦兹协变性。

### 7.2.1 四维坐标与间隔

+ 引入虚时间坐标 $x_4 = ict$，将事件的时空坐标定义为四维位置矢量 $x_\mu$ ($\mu = 1, 2, 3, 4$)：

  $$
  x_\mu = (x_1, x_2, x_3, x_4) = (\bm{x}, ict)
  $$

  其中 $\bm{x} = (x, y, z)$ 为三维空间坐标。

+ 两个事件点 $x_\mu$ 和 $x_\mu + dx_\mu$ 之间的时空间隔平方定义为：

  $$
  ds^2 = dx_\mu dx_\mu = dx_1^2 + dx_2^2 + dx_3^2 + dx_4^2 = |d\bm{x}|^2 - c^2 dt^2
  $$

  (注：此处采用爱因斯坦求和约定，对重复指标 $\mu$ 从 1 到 4 求和)。根据光速不变原理，$ds^2$ 是一个洛伦兹不变量 (Lorentz Scalar)，即在所有惯性系中其值相等。

### 7.2.2 洛伦兹变换的几何意义

+ 由于 $dx_\mu dx_\mu$ 不变，洛伦兹变换在数学上等价于四维欧几里得空间中的正交线性变换（类似于三维空间中的转动）。变换关系写作：

  $$
  x'_\mu = a_{\mu\nu} x_\nu
  $$

  其中 $a_{\mu\nu}$ 为变换矩阵的元素。

+ 对于 $\Sigma'$ 系相对 $\Sigma$ 系沿 $x_1$ ($x$) 轴以速度 $v$ 运动的情况，变换矩阵为：

  $$
  (a_{\mu\nu}) = \begin{pmatrix}
  \gamma & 0 & 0 & i\beta\gamma \\
  0 & 1 & 0 & 0 \\
  0 & 0 & 1 & 0 \\
  -i\beta\gamma & 0 & 0 & \gamma
  \end{pmatrix}
  $$

  利用三角函数关系 $\gamma = \cos(i\alpha)$ 等，这可以看作是 $x_1 - x_4$ 平面内的转动。

+ 为保证 $x'_\mu x'_\mu = x_\mu x_\mu$，变换系数必须满足正交性条件：

  $$
  a_{\mu\lambda} a_{\nu\lambda} = \delta_{\mu\nu} \quad (\text{或 } a_{\lambda\mu} a_{\lambda\nu} = \delta_{\mu\nu})
  $$

### 7.2.3 四维矢量与张量

+ 四维矢量：一组由 4 个分量组成的量 $A_\mu = (A_1, A_2, A_3, A_4)$，如果在坐标变换下，其分量像坐标 $x_\mu$ 一样变换，则称为四维矢量：

  $$
  A'_\mu = a_{\mu\nu} A_\nu
  $$

  三维对应关系：通常 $A_\mu$ 由一个三维矢量 $\bm{A}$ 和一个标量 $\phi$ 构成，形式为 $A_\mu = (\bm{A}, i\phi)$。注意第四分量通常包含虚数单位 $i$，以保证模长平方的物理意义。

+ 标量积 (Scalar Product)：两个四维矢量 $A_\mu$ 和 $B_\mu$ 的标量积定义为 $A_\mu B_\mu$。它是一个不变量（标量）：

  $$
  A_\mu B_\mu = \bm{A} \cdot \bm{B} + A_4 B_4 = \text{Invariant}
  $$

+ 四维张量 (Four-Tensor)：依此类推，二阶张量 $T_{\mu\nu}$ 的变换规则为：

  $$
  T'_{\mu\nu} = a_{\mu\alpha} a_{\nu\beta} T_{\alpha\beta}
  $$

### 7.2.4 四维微分算符

+ 四维梯度：对坐标的偏导数算符 $\partial_\mu \equiv \frac{\partial}{\partial x_\mu}$ 也是一个四维矢量。其分量为：

  $$
  \frac{\partial}{\partial x_\mu} = \left( \nabla, \frac{1}{ic} \frac{\partial}{\partial t} \right)
  $$

  三维对应：空间部分为梯度算符 $\nabla$，时间部分与 $\partial/\partial t$ 有关。

+ 四维散度：四维矢量 $A_\mu$ 的散度是一个标量（不变量）：

  $$
  \frac{\partial A_\mu}{\partial x_\mu} = \nabla \cdot \bm{A} + \frac{1}{ic} \frac{\partial A_4}{\partial t}
  $$

+ 达朗贝尔算符 (d'Alembertian)：四维梯度的自身标量积构成了达朗贝尔算符，它是一个标量算符：

  $$
  \square^2 \equiv \frac{\partial}{\partial x_\mu} \frac{\partial}{\partial x_\mu} = \nabla^2 - \frac{1}{c^2} \frac{\partial^2}{\partial t^2}
  $$

  这意味着波动方程 $\square^2 \psi = 0$ 在洛伦兹变换下保持形式不变。

## 7.3 相对论力学中的四维矢量与不变量

+ 本节利用四维矢量语言重构相对论力学。构建四维物理量的基本原则是：为了保证物理定律的协变性，物理方程两边的量必须具有相同的变换性质（如同为四维矢量或同为四维张量）。

### 7.3.1 固有时间与四维速度

+ 固有时间 (Proper Time)：间隔 $ds^2$ 是不变量，对于做类时运动（$v<c$）的粒子，我们可以定义一个与参考系无关的时间参数——固有时间 $\tau$。它是随粒子一起运动的时钟所记录的时间。

  $$
  d\tau = \frac{ds}{ic} = dt \sqrt{1 - \beta^2} = \frac{dt}{\gamma}
  $$

  $d\tau$ 是洛伦兹标量。

+ 四维速度 (Four-Velocity)：为了定义相对论速度，我们需要用位置矢量 $x_\mu$ 对一个标量（固有时间 $\tau$）求导，而不是对坐标时间 $t$ 求导（因为 $t$ 在变换下会改变）。定义四维速度 $U_\mu$ 为：

  $$
  U_\mu = \frac{dx_\mu}{d\tau}
  $$

+ 四维与三维的关系：利用 $d\tau = dt/\gamma$ 和 $x_\mu = (\bm{x}, ict)$，可得：

  $$
  U_\mu = \frac{dt}{d\tau} \frac{dx_\mu}{dt} = \gamma (\bm{v}, ic)
  $$

  即：

  $$
  U_\mu = (\gamma \bm{v}, i\gamma c)
  $$

  其中前三个分量是相对论性空间速度，第四分量与 $c$ 有关。

+ 不变量恒等式：四维速度的模平方是一个常数：

  $$
  U_\mu U_\mu = \gamma^2 v^2 - \gamma^2 c^2 = \gamma^2 (v^2 - c^2) = -c^2
  $$

  即 $U_\mu U_\mu = -c^2$。这意味着在四维速度空间中，粒子始终位于半径为 $ic$ 的球面上。

### 7.3.2 四维动量与质能关系

+ 四维动量 (Four-Momentum)：定义粒子的四维动量 $P_\mu$ 为静止质量 $m_0$ 与四维速度的乘积：

  $$
  P_\mu = m_0 U_\mu
  $$

  四维与三维的关系：将 $U_\mu$ 代入，得：

  $$
  P_\mu = (m_0 \gamma \bm{v}, i m_0 \gamma c)
  $$

  我们识别出前三个分量为相对论动量 $\bm{p} = m \bm{v} = \gamma m_0 \bm{v}$（其中 $m=\gamma m_0$ 为运动质量）。第四个分量除以 $i/c$ 后具有能量的量纲，即 $P_4 = iE/c$，其中 $E = m c^2 = \gamma m_0 c^2$ 为粒子的总能量。总结关系如下：

  $$
  P_\mu = (\bm{p}, i\frac{E}{c})
  $$

+ 不变量恒等式 (质能关系)：利用 $U_\mu U_\mu = -c^2$，我们有：

  $$
  P_\mu P_\mu = m_0^2 U_\mu U_\mu = -m_0^2 c^2
  $$

  另一方面，利用分量形式展开 $P_\mu P_\mu = \bm{p}^2 + (iE/c)^2 = p^2 - E^2/c^2$。联立两式，得到著名的能量-动量关系：

  $$
  p^2 - \frac{E^2}{c^2} = -m_0^2 c^2 \quad \implies \quad E^2 - p^2 c^2 = m_0^2 c^4
  $$

### 7.3.3 四维力与闵可夫斯基方程

+ 四维力 (Four-Force)：为了建立相对论动力学方程（牛顿第二定律的推广），我们将四维动量对固有时间求导，定义闵可夫斯基力 $K_\mu$：

  $$
  K_\mu = \frac{d P_\mu}{d\tau}
  $$

  于是相对论动力学方程为 $K_\mu = m_0 \frac{d^2 x_\mu}{d\tau^2}$。

  四维与三维的关系：利用 $d\tau = dt/\gamma$，我们将其与三维力 $\bm{f} = \frac{d\bm{p}}{dt}$ 联系起来：

  $$
  K_\mu = \gamma \frac{d P_\mu}{dt} = \gamma \frac{d}{dt} (\bm{p}, i\frac{E}{c}) = \left( \gamma \frac{d\bm{p}}{dt}, i\frac{\gamma}{c} \frac{dE}{dt} \right)
  $$

  利用功能关系 $\frac{dE}{dt} = \bm{f} \cdot \bm{v}$（力做功的功率），代入得：

  $$
  K_\mu = \left( \gamma \bm{f}, i\gamma \frac{\bm{f} \cdot \bm{v}}{c} \right)
  $$

  这表明四维力的空间分量并不是普通的三维力 $\bm{f}$，而是修正后的 $\gamma \bm{f}$。

+ 正交性不变量：考察四维力与四维速度的标量积：

  $$
  K_\mu U_\mu = \gamma \bm{f} \cdot \gamma \bm{v} + \left( i\gamma \frac{\bm{f} \cdot \bm{v}}{c} \right) (i\gamma c) = \gamma^2 (\bm{f} \cdot \bm{v}) - \gamma^2 (\bm{f} \cdot \bm{v}) = 0
  $$

  即 $K_\mu U_\mu = 0$。这个恒等式反映了静止质量 $m_0$ 是常数这一事实（$P_\mu P_\mu = \text{const}$ 隐含了 $P_\mu \frac{dP_\mu}{d\tau} = 0$）。至于四维力的模平方 $K_\mu^2$，它不像 $U_\mu^2$ 或 $P_\mu^2$ 那样是一个普适常数，而是取决于粒子的运动状态。在粒子的瞬时静止系中，$K_\mu = (\bm{f}_0, 0)$，故：

  $$
  K_\mu^2 = K_\mu K_\mu = \bm{f}_0^2 = m_0^2 \bm{a}_0^2
  $$

  即四维力的模长等于粒子固有加速度（静止系加速度）产生的惯性力 $m_0 a_0$。

## 7.4 相对论电动力学中的四维矢量与不变量

+ 电动力学本身就是符合相对论的（符合光速不变原理及相对性原理），因此将其改写为四维形式不需要修改物理内容，只需寻找合适的四维矢量定义。

### 7.4.1 四维电流密度与四维势

+ 四维电流密度 (Four-Current Density)：电荷量 $dQ$ 是一个洛伦兹标量（电荷不变性）。但电荷密度 $\rho = dQ/dV$ 不是标量，因为体积元受尺缩效应影响 $dV = dV_0 \sqrt{1-\beta^2}$。因此 $\rho = \rho_0 / \sqrt{1-\beta^2} = \gamma \rho_0$。利用 $\bm{j} = \rho \bm{v}$，我们构造四维电流密度 $J_\mu$：

  $$
  J_\mu = \rho_0 U_\mu = \rho_0 (\gamma \bm{v}, i\gamma c) = (\rho \bm{v}, i\rho c)
  $$

  即：

  $$
  J_\mu = (\bm{j}, ic\rho)
  $$

  电荷守恒定律的四维形式为四维散度为零：

  $$
  \frac{\partial J_\mu}{\partial x_\mu} = \nabla \cdot \bm{j} + \frac{\partial (ic\rho)}{\partial (ict)} = \nabla \cdot \bm{j} + \frac{\partial \rho}{\partial t} = 0
  $$

+ 四维电磁势 (Four-Potential)：为了使电磁势满足协变性，标势 $\varphi$ 和矢势 $\bm{A}$ 构成一个四维矢量 $A_\mu$：

  $$
  A_\mu = (\bm{A}, i\frac{\varphi}{c})
  $$

  洛伦兹规范条件的四维形式：

  $$
  \frac{\partial A_\mu}{\partial x_\mu} = \nabla \cdot \bm{A} + \frac{1}{ic} \frac{\partial (i\varphi/c)}{\partial t} = \nabla \cdot \bm{A} + \mu_0 \varepsilon_0 \frac{\partial \varphi}{\partial t} = 0
  $$

  达朗贝尔方程（非齐次波动方程）的四维形式：

  $$
  \square^2 A_\mu = -\mu_0 J_\mu
  $$

  这是显然协变的，因为 $\square^2$ 是标量算符，$A_\mu$ 和 $J_\mu$ 都是四维矢量。

+ 四维波矢 (Four-Wave Vector)：对于平面单色波，相位因子 $\Phi = \bm{k}\cdot\bm{r} - \omega t$ 是一个洛伦兹标量（相位是计数的周期数，不随参考系改变）。将其重写为四维标量积形式：

  $$
  \bm{k}\cdot\bm{r} - \omega t = \bm{k}\cdot\bm{r} + (i\frac{\omega}{c})(ict) = k_\mu x_\mu
  $$

  由此定义四维波矢 $k_\mu$：

  $$
  k_\mu = (\bm{k}, i\frac{\omega}{c})
  $$

  对于真空中的光波，$k = \omega/c$，故：

  $$
  k_\mu k_\mu = k^2 - \frac{\omega^2}{c^2} = 0
  $$

  这对应于光子是零质量粒子（四维动量 $P_\mu = \hbar k_\mu$，故 $P_\mu^2 = 0$）。

### 7.4.2 电磁场张量

+ 电场 $\bm{E}$ 和磁场 $\bm{B}$ 既不是标量也不是四维矢量，它们是四维势 $A_\mu$ 的导数。定义二阶反对称张量——电磁场张量 $F_{\mu\nu}$：

  $$
  F_{\mu\nu} = \frac{\partial A_\nu}{\partial x_\mu} - \frac{\partial A_\mu}{\partial x_\nu}
  $$

  显然 $F_{\mu\nu} = -F_{\nu\mu}$，对角元为零。利用 $\bm{E} = -\nabla \varphi - \frac{\partial \bm{A}}{\partial t}$ 和 $\bm{B} = \nabla \times \bm{A}$，具体计算各分量：

  $F_{12} = \frac{\partial A_y}{\partial x} - \frac{\partial A_x}{\partial y} = B_z$

  $F_{14} = \frac{\partial (i\varphi/c)}{\partial x} - \frac{\partial A_x}{\partial (ict)} = \frac{i}{c} (-\frac{\partial \varphi}{\partial x} - \frac{\partial A_x}{\partial t}) = -\frac{i}{c} E_x$

  写成矩阵形式：

  $$
  (F_{\mu\nu}) = \begin{pmatrix}
  0 & B_z & -B_y & -iE_x/c \\
  -B_z & 0 & B_x & -iE_y/c \\
  B_y & -B_x & 0 & -iE_z/c \\
  iE_x/c & iE_y/c & iE_z/c & 0
  \end{pmatrix}
  $$

  这表明 $\bm{E}$ 和 $\bm{B}$ 统一为一个几何客体 $F_{\mu\nu}$。

### 7.4.3 麦克斯韦方程组的协变形式

+ 麦克斯韦方程组可以写成两组极其简洁的张量方程：

  1. 非齐次方程组 (含源)：
   
    对应 $\nabla \times \bm{B} - \frac{1}{c^2}\frac{\partial \bm{E}}{\partial t} = \mu_0 \bm{j}$ 和 $\nabla \cdot \bm{E} = \rho/\varepsilon_0$。

    $$
    \frac{\partial F_{\mu\nu}}{\partial x_\nu} = \mu_0 J_\mu
    $$

  2. 齐次方程组 (无源恒等式)：

    对应 $\nabla \times \bm{E} + \frac{\partial \bm{B}}{\partial t} = 0$ 和 $\nabla \cdot \bm{B} = 0$。

    $$
    \frac{\partial F_{\mu\nu}}{\partial x_\lambda} + \frac{\partial F_{\nu\lambda}}{\partial x_\mu} + \frac{\partial F_{\lambda\mu}}{\partial x_\nu} = 0
    $$

    或者利用完全反对称张量 $\epsilon_{\mu\nu\lambda\sigma}$ 定义对偶张量 $\tilde{F}_{\mu\nu}$，方程可简写为 $\frac{\partial \tilde{F}_{\mu\nu}}{\partial x_\nu} = 0$。

### 7.4.4 电磁场的不变量

+ 由张量 $F_{\mu\nu}$ 可以构造出洛伦兹标量（不变量），这些量在任何惯性系中数值相等。

  1. 标量不变量 (由 $F_{\mu\nu} F_{\mu\nu}$ 构造)：

    $$
    F_{\mu\nu} F_{\mu\nu} = 2(B^2 - \frac{E^2}{c^2}) = \text{invariant}
    $$

    物理意义：$c^2 B^2 - E^2$ 的值与参考系无关。

  2. 伪标量不变量 (由 $\det(F_{\mu\nu})$ 或 $F_{\mu\nu} \tilde{F}_{\mu\nu}$ 构造)：

    $$
    \frac{1}{4} \epsilon_{\mu\nu\lambda\sigma} F_{\mu\nu} F_{\lambda\sigma} = \frac{i}{c} \bm{E} \cdot \bm{B} = \text{invariant}
    $$

    物理意义：$\bm{E} \cdot \bm{B}$ 的值与参考系无关。

+ 物理推论：

  1. 如果在一个参考系中 $\bm{E} \perp \bm{B}$（即 $\bm{E} \cdot \bm{B} = 0$），那么在任何参考系中它们都垂直。

  2. 如果在一个参考系中 $|\bm{E}| < c|\bm{B}|$，则总能找到一个参考系使得 $\bm{E}'=0$（纯磁场）。

  3. 如果在一个参考系中 $|\bm{E}| > c|\bm{B}|$，则总能找到一个参考系使得 $\bm{B}'=0$（纯电场）。

  4. 平面电磁波满足 $E = cB$ 且 $\bm{E} \perp \bm{B}$，这两个不变量均为零。这意味着光波的性质在所有惯性系中保持不变。

## 7.5 总结：相对论物理量的四维对应关系

+ 将物理定律写成四维形式，不仅展示了物理规律的简洁美，更重要的是显式地体现了其洛伦兹协变性。只要方程两边具有相同的张量性质，该方程在所有惯性系中就具有相同的形式。为了便于查阅和记忆，本节总结了相对论力学和电动力学中常见的物理量及其四维对应形式，并列出了相关的不变量。

### 7.5.1 四维与三维物理量的对应表

  下表中，四维矢量定义为 $A_\mu = (\bm{A}, i A_0)$，其中前三量为空间分量，第四量为时间分量（虚数）。

  |   物理概念   | 四维表示 $A_\mu$ |               三维对应 $(\bm{A}, iA_0)$               |     模平方不变量 $A_\mu^2$      |
  | :----------: | :--------------: | :---------------------------------------------------: | :-----------------------------: |
  |   事件坐标   |     $x_\mu$      |                    $(\bm{x}, ict)$                    | $s^2 = r^2 - c^2t^2$ (时空间隔) |
  |   梯度算符   |  $\partial_\mu$  |  $(\nabla, \frac{1}{ic}\frac{\partial}{\partial t})$  |   $\square^2$ (达朗贝尔算符)    |
  |     速度     |     $U_\mu$      |              $(\gamma\bm{v}, i\gamma c)$              |             $-c^2$              |
  |     动量     |     $P_\mu$      |                   $(\bm{p}, iE/c)$                    |     $-m_0^2 c^2$ (质能关系)     |
  |      力      |     $K_\mu$      | $(\gamma\bm{f}, i\gamma \frac{\bm{f}\cdot\bm{v}}{c})$ | $m_0^2 a_0^2$ (固有加速度平方)  |
  |   电流密度   |     $J_\mu$      |                  $(\bm{j}, ic\rho)$                   |        $j^2 - c^2\rho^2$        |
  |    电磁势    |     $A_\mu$      |                $(\bm{A}, i\varphi/c)$                 |      $A^2 - \varphi^2/c^2$      |
  |     波矢     |     $k_\mu$      |                 $(\bm{k}, i\omega/c)$                 |  $k^2 - \omega^2/c^2 = 0$ (光)  |
  | 洛伦兹力密度 |     $f_\mu$      |    $(\bm{f}_{den}, \frac{i}{c}\bm{j}\cdot\bm{E})$     |     $f_\mu^2$ (无特定常数)      |
  |    场张量    |   $F_{\mu\nu}$   |                $(\bm{E}, \bm{B})$ 组合                |       $2(B^2 - E^2/c^2)$        |

### 7.5.2 重要的协变方程

+ 这些方程在洛伦兹变换下保持形式不变。

  电荷守恒：

  $$
  \frac{\partial J_\mu}{\partial x_\mu} = 0
  $$

  洛伦兹规范：

  $$
  \frac{\partial A_\mu}{\partial x_\mu} = 0
  $$

  波动方程 (达朗贝尔方程)：

  $$
  \square^2 A_\mu = -\mu_0 J_\mu
  $$

  麦克斯韦方程组：

  $$
  \frac{\partial F_{\mu\nu}}{\partial x_\nu} = \mu_0 J_\mu
  $$

  $$
  \frac{\partial F_{\mu\nu}}{\partial x_\lambda} + \frac{\partial F_{\nu\lambda}}{\partial x_\mu} + \frac{\partial F_{\lambda\mu}}{\partial x_\nu} = 0
  $$

  相对论动力学方程：

  $$
  K_\mu = \frac{d P_\mu}{d\tau}
  $$

### 7.5.3 电磁场不变量

+ 电场 $\bm{E}$ 和磁场 $\bm{B}$ 虽然在变换下会相互转化，但某些组合量是洛伦兹标量，其数值与参考系无关：

  标量不变量：

  $$
  F_{\mu\nu} F_{\mu\nu} = 2(B^2 - \frac{E^2}{c^2})
  $$

  伪标量不变量：

  $$
  \frac{1}{4} \epsilon_{\mu\nu\lambda\sigma} F_{\mu\nu} F_{\lambda\sigma} = \frac{i}{c} \bm{E} \cdot \bm{B}
  $$

  这些不变量决定了电磁场在时空中的基本拓扑性质（如是否垂直、是否等大等），这些性质是内在的，不随观察者的运动状态改变。