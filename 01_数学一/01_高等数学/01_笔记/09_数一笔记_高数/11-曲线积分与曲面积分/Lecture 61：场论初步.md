---
title: Lecture 61：场论初步
tags: [考研, 数学一, 高等数学, 数学, 场论, 梯度, 散度, 旋度, 斯托克斯公式]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 61：场论初步

## 一、方向导数与梯度

> [!important|purple] 定义：方向导数
> 设函数 $f(x,y,z)$ 在点 $P_0(x_0, y_0, z_0)$ 的某邻域内有定义，$\boldsymbol{l}^0 = (\cos\alpha, \cos\beta, \cos\gamma)$ 为方向 $\boldsymbol{l}$ 的单位向量。若极限
> $$\frac{\partial f}{\partial \boldsymbol{l}}\bigg|_{P_0} = \lim_{t \to 0^+} \frac{f(P_0 + t\boldsymbol{l}^0) - f(P_0)}{t}$$
> 存在，则称其为 $f$ 在 $P_0$ 沿方向 $\boldsymbol{l}$ 的**方向导数**。

> [!important|blue] 定理：方向导数的计算公式
> 若 $f$ 在 $P_0$ 可微，则
> $$\frac{\partial f}{\partial \boldsymbol{l}} = \frac{\partial f}{\partial x}\cos\alpha + \frac{\partial f}{\partial y}\cos\beta + \frac{\partial f}{\partial z}\cos\gamma$$

> [!important|purple] 定义：梯度
> 设 $f(x,y,z)$ 有连续偏导数，$f$ 在点 $P$ 的**梯度**定义为：
> $$\text{grad}\,f = \nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}\right)$$
>
> 其中 $\nabla = \left(\dfrac{\partial}{\partial x}, \dfrac{\partial}{\partial y}, \dfrac{\partial}{\partial z}\right)$ 为**Nabla 算子**（哈密顿算子）。

> [!important|blue] 定理：梯度的重要性质
> 1. **方向导数与梯度的关系：**
> $$\frac{\partial f}{\partial \boldsymbol{l}} = \text{grad}\,f \cdot \boldsymbol{l}^0 = |\text{grad}\,f|\cos\theta$$
> 其中 $\theta$ 为梯度与方向 $\boldsymbol{l}$ 的夹角。
>
> 2. **梯度方向是方向导数最大的方向**：当 $\theta = 0$（即 $\boldsymbol{l}$ 与梯度同向）时，$\dfrac{\partial f}{\partial \boldsymbol{l}}$ 最大，最大值为 $|\text{grad}\,f|$。
>
> 3. **梯度的几何意义**：梯度 $\nabla f$ 垂直于等值面 $f(x,y,z) = C$，指向 $f$ 增大的方向。
>
> 4. **梯度的运算性质：**
> - $\nabla(Cf) = C\nabla f$
> - $\nabla(f + g) = \nabla f + \nabla g$
> - $\nabla(fg) = f\nabla g + g\nabla f$
> - $\nabla\left(\dfrac{f}{g}\right) = \dfrac{g\nabla f - f\nabla g}{g^2}$

#### 例题 1

求 $f(x,y,z) = x^2 + y^2 + z^2$ 在点 $(1, -1, 2)$ 处的梯度和沿方向 $\boldsymbol{l} = (1, 1, 1)$ 的方向导数。

**解：**
$$\nabla f = (2x, 2y, 2z), \quad \nabla f(1,-1,2) = (2, -2, 4)$$

$\boldsymbol{l}$ 的单位向量：$\boldsymbol{l}^0 = \dfrac{1}{\sqrt{3}}(1, 1, 1)$。

$$\frac{\partial f}{\partial \boldsymbol{l}} = (2, -2, 4) \cdot \frac{1}{\sqrt{3}}(1,1,1) = \frac{2-2+4}{\sqrt{3}} = \frac{4}{\sqrt{3}} = \frac{4\sqrt{3}}{3}$$

---

## 二、散度

> [!important|purple] 定义：散度
> 设向量场 $\boldsymbol{F} = (P, Q, R)$，其中 $P, Q, R$ 有连续偏导数，则 $\boldsymbol{F}$ 在点 $(x,y,z)$ 的**散度**定义为：
> $$\text{div}\,\boldsymbol{F} = \nabla \cdot \boldsymbol{F} = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}$$

> [!important|blue] 定理：散度的性质与意义
> 1. **散度是标量**：$\text{div}\,\boldsymbol{F}$ 是一个数（不是向量）。
> 2. **物理意义**：散度表示向量场在该点的"源"或"汇"的强度。$\text{div}\,\boldsymbol{F} > 0$ 表示该点是"源"（流出），$\text{div}\,\boldsymbol{F} < 0$ 表示"汇"（流入），$\text{div}\,\boldsymbol{F} = 0$ 表示无源场。
> 3. **高斯公式的散度形式**：
> $$\oiint_\Sigma \boldsymbol{F} \cdot d\boldsymbol{S} = \iiint_\Omega \text{div}\,\boldsymbol{F}\,dV$$
> 4. **运算性质：**
> - $\nabla \cdot (f\boldsymbol{F}) = f\nabla \cdot \boldsymbol{F} + \nabla f \cdot \boldsymbol{F}$
> - $\nabla \cdot (\boldsymbol{F} + \boldsymbol{G}) = \nabla \cdot \boldsymbol{F} + \nabla \cdot \boldsymbol{G}$

#### 例题 2

求 $\boldsymbol{F} = (x^2 y, y^2 z, z^2 x)$ 的散度。

**解：**
$$\text{div}\,\boldsymbol{F} = \frac{\partial}{\partial x}(x^2 y) + \frac{\partial}{\partial y}(y^2 z) + \frac{\partial}{\partial z}(z^2 x) = 2xy + 2yz + 2zx$$

---

## 三、旋度

> [!important|purple] 定义：旋度
> 设向量场 $\boldsymbol{F} = (P, Q, R)$，则 $\boldsymbol{F}$ 的**旋度**定义为：
> $$\text{rot}\,\boldsymbol{F} = \nabla \times \boldsymbol{F} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ \dfrac{\partial}{\partial x} & \dfrac{\partial}{\partial y} & \dfrac{\partial}{\partial z} \\ P & Q & R \end{vmatrix}$$
>
> $$= \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right)\boldsymbol{i} + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right)\boldsymbol{j} + \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)\boldsymbol{k}$$

> [!important|blue] 定理：旋度的性质
> 1. **旋度是向量**：$\text{rot}\,\boldsymbol{F}$ 是一个向量（不是标量）。
> 2. **物理意义**：旋度描述向量场的旋转程度。$\text{rot}\,\boldsymbol{F} = \boldsymbol{0}$ 时称 $\boldsymbol{F}$ 为**无旋场**（保守场）。
> 3. **运算性质：**
> - $\nabla \times (\nabla f) = \boldsymbol{0}$（梯度场的旋度为零）
> - $\nabla \cdot (\nabla \times \boldsymbol{F}) = 0$（旋度场的散度为零）
> 4. **无旋场等价于保守场**：在单连通区域内，$\text{rot}\,\boldsymbol{F} = \boldsymbol{0}$ $\Leftrightarrow$ $\boldsymbol{F}$ 是某个标量函数的梯度 $\Leftrightarrow$ 曲线积分与路径无关。

#### 例题 3

求 $\boldsymbol{F} = (yz, xz, xy)$ 的旋度。

**解：**
$$\text{rot}\,\boldsymbol{F} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ \dfrac{\partial}{\partial x} & \dfrac{\partial}{\partial y} & \dfrac{\partial}{\partial z} \\ yz & xz & xy \end{vmatrix}$$

$$= (x - x)\boldsymbol{i} + (y - y)\boldsymbol{j} + (z - z)\boldsymbol{k} = \boldsymbol{0}$$

$\boldsymbol{F}$ 是无旋场。实际上 $f = xyz$，$\boldsymbol{F} = \nabla f$。

---

## 四、斯托克斯公式

> [!important|blue] 定理：斯托克斯公式（Stokes' Formula）
> 设 $\Sigma$ 为有向光滑曲面，$\partial\Sigma$ 为其正向边界（与 $\Sigma$ 的侧符合右手法则），$P, Q, R$ 在包含 $\Sigma$ 的区域内有一阶连续偏导数，则
> $$\oint_{\partial\Sigma} P\,dx + Q\,dy + R\,dz = \iint_\Sigma \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right)dydz + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right)dzdx + \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)dxdy$$
>
> **行列式形式（便于记忆）：**
> $$\oint_{\partial\Sigma} P\,dx + Q\,dy + R\,dz = \iint_\Sigma \begin{vmatrix} dydz & dzdx & dxdy \\ \dfrac{\partial}{\partial x} & \dfrac{\partial}{\partial y} & \dfrac{\partial}{\partial z} \\ P & Q & R \end{vmatrix}$$
>
> **向量形式：**
> $$\oint_{\partial\Sigma} \boldsymbol{F} \cdot d\boldsymbol{r} = \iint_\Sigma (\nabla \times \boldsymbol{F}) \cdot d\boldsymbol{S}$$
>
> **物理意义：** 向量场 $\boldsymbol{F}$ 沿闭曲线 $\partial\Sigma$ 的环流量等于旋度通过曲面 $\Sigma$ 的通量。

#### 例题 4

用斯托克斯公式计算 $\oint_L y\,dx + z\,dy + x\,dz$，其中 $L$ 为圆 $\begin{cases} x^2 + y^2 + z^2 = a^2 \\ x + y + z = 0 \end{cases}$，从 $x$ 轴正向看取逆时针方向。

**解：** $P = y$，$Q = z$，$R = x$。

$$\text{rot}\,\boldsymbol{F} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ \dfrac{\partial}{\partial x} & \dfrac{\partial}{\partial y} & \dfrac{\partial}{\partial z} \\ y & z & x \end{vmatrix} = (0-1)\boldsymbol{i} + (0-1)\boldsymbol{j} + (0-1)\boldsymbol{k} = (-1, -1, -1)$$

取 $\Sigma$ 为 $x + y + z = 0$ 上被 $L$ 围成的圆盘，法向量 $\boldsymbol{n} = \dfrac{1}{\sqrt{3}}(1, 1, 1)$（与 $L$ 的方向符合右手法则）。

$$\iint_\Sigma \text{rot}\,\boldsymbol{F} \cdot d\boldsymbol{S} = \iint_\Sigma (-1, -1, -1) \cdot \boldsymbol{n}\,dS = -\frac{3}{\sqrt{3}}\iint_\Sigma dS = -\sqrt{3} \cdot \pi a^2$$

（圆盘面积为 $\pi a^2$，因为大圆在球面上被平面截得的截面半径就是 $a$。）

$$\oint_L y\,dx + z\,dy + x\,dz = -\sqrt{3}\pi a^2$$

---

## 五、场论三大公式的统一

> [!important|blue] 定理：微积分基本定理的推广
>
> | 公式 | 维度 | 形式 | 本质 |
> |:---:|:---:|:---:|:---:|
> | **牛顿-莱布尼茨公式** | 1D | $\displaystyle\int_a^b f'(x)\,dx = f(b) - f(a)$ | 边界值之差 |
> | **格林公式** | 2D | $\displaystyle\oint_{\partial D} \boldsymbol{F} \cdot d\boldsymbol{r} = \iint_D (\nabla \times \boldsymbol{F}) \cdot \boldsymbol{k}\,dA$ | 边界上的积分 = 区域内的旋度 |
> | **高斯公式** | 3D | $\displaystyle\oiint_{\partial\Omega} \boldsymbol{F} \cdot d\boldsymbol{S} = \iiint_\Omega \nabla \cdot \boldsymbol{F}\,dV$ | 边界上的积分 = 区域内的散度 |
> | **斯托克斯公式** | 2D/3D | $\displaystyle\oint_{\partial\Sigma} \boldsymbol{F} \cdot d\boldsymbol{r} = \iint_\Sigma (\nabla \times \boldsymbol{F}) \cdot d\boldsymbol{S}$ | 边界上的积分 = 曲面上的旋度 |
>
> **核心思想：** 区域内部的微分信息（导数、散度、旋度）决定了边界上的积分行为。

---

## 六、易错点总结

> 1. **梯度是向量，散度是标量，旋度是向量**：三者类型不同，不要混淆。
> 2. **方向导数是标量**，不是向量。它是梯度在某方向上的投影。
> 3. **方向导数的计算要求函数可微**：如果不可微，方向导数可能存在但不能用公式 $\nabla f \cdot \boldsymbol{l}^0$ 计算。
> 4. **散度用点乘**（$\nabla \cdot \boldsymbol{F}$），**旋度用叉乘**（$\nabla \times \boldsymbol{F}$）。
> 5. **旋度行列式展开时**：第二列加负号，与叉积行列式一样。
> 6. **斯托克斯公式的边界方向**：$\partial\Sigma$ 的方向与 $\Sigma$ 的侧符合右手法则——右手四指沿边界方向弯曲，拇指指向法向量方向。
> 7. **无旋场 $\Leftrightarrow$ 保守场** 只在单连通区域内成立。非单连通区域内旋度为零不一定保守。
> 8. **梯度最大方向导数**：最大方向导数为 $|\nabla f|$，方向为 $\nabla f$ 方向，不是任意方向。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 58：第二类曲线积分]] — 曲线积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 60：第二类曲面积分]] — 曲面积分
