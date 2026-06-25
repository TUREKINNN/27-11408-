---
title: Lecture 60：第二类曲面积分
tags: [考研, 数学一, 高等数学, 数学, 曲面积分, 对坐标的曲面积分, 高斯公式, 第二类曲面积分]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 60：第二类曲面积分

## 一、对坐标的曲面积分（第二类曲面积分）定义

> [!important|purple] 定义：第二类曲面积分
> 设 $\Sigma$ 为有向光滑曲面，$P, Q, R$ 为定义在 $\Sigma$ 上的函数。将 $\Sigma$ 分成 $n$ 小块 $\Delta S_i$，$\Delta S_i$ 在 $xOy$ 面上的投影为 $(\Delta S_i)_{xy}$（可正可负，取决于法向量方向），在每小块上取一点 $(\xi_i, \eta_i, \zeta_i)$，作和
> $$\sum_{i=1}^n R(\xi_i, \eta_i, \zeta_i)(\Delta S_i)_{xy}$$
> 若极限存在，记为 $\displaystyle\iint_\Sigma R(x,y,z)\,dxdy$。
>
> 类似地定义 $\displaystyle\iint_\Sigma P\,dydz$ 和 $\displaystyle\iint_\Sigma Q\,dzdx$。
>
> **一般形式：**
> $$\iint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy$$
>
> **向量形式：** 设 $\boldsymbol{F} = (P, Q, R)$，$d\boldsymbol{S} = (dydz, dzdx, dxdy)$，则
> $$\iint_\Sigma \boldsymbol{F} \cdot d\boldsymbol{S} = \iint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy$$
>
> **物理意义：** 向量场 $\boldsymbol{F}$ 通过有向曲面 $\Sigma$ 的**通量**。

> [!important|blue] 定理：第二类曲面积分的性质
> 1. **与曲面的侧有关**：改变曲面的侧（法向量反向），积分变号。
> 2. **线性性**、**曲面可加性**同第一类。
> 3. $\displaystyle\iint_{-\Sigma} P\,dydz + Q\,dzdx + R\,dxdy = -\iint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy$
>    （$-\Sigma$ 表示与 $\Sigma$ 取相反侧的同一曲面）

---

## 二、两类曲面积分的关系

> [!important|blue] 定理：两类曲面积分的联系
> $$\iint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy = \iint_\Sigma (P\cos\alpha + Q\cos\beta + R\cos\gamma)\,dS$$
> 其中 $(\cos\alpha, \cos\beta, \cos\gamma)$ 为 $\Sigma$ 上点处指定侧的单位法向量。
>
> **等价关系：**
> $$dydz = \cos\alpha\,dS, \quad dzdx = \cos\beta\,dS, \quad dxdy = \cos\gamma\,dS$$

---

## 三、计算方法

### 方法一：投影法（合一投影法）

> [!important|blue] 定理：投影法计算公式
> 以 $\displaystyle\iint_\Sigma R(x,y,z)\,dxdy$ 为例：
>
> 若 $\Sigma: z = z(x,y)$，$(x,y) \in D_{xy}$，取上侧（法向量朝上，$\cos\gamma > 0$），则
> $$\iint_\Sigma R\,dxdy = \iint_{D_{xy}} R(x, y, z(x,y))\,dxdy$$
>
> 若取下侧（$\cos\gamma < 0$），则
> $$\iint_\Sigma R\,dxdy = -\iint_{D_{xy}} R(x, y, z(x,y))\,dxdy$$
>
> **记忆：** 上侧为正，下侧为负。前侧（$x$ 正方向）为正，后侧为负。右侧（$y$ 正方向）为正，左侧为负。
>
> **合一投影法：** 将 $P\,dydz + Q\,dzdx + R\,dxdy$ 统一投影到 $xOy$ 面：
> $$\iint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy = \pm\iint_{D_{xy}} \left[P(-z_x) + Q(-z_y) + R\right] dxdy$$
> 取上侧为 $+$，下侧为 $-$。

#### 例题 1

计算 $\iint_\Sigma z\,dxdy$，其中 $\Sigma$ 是球面 $x^2 + y^2 + z^2 = a^2$ 的外侧。

**解：** 分上下两部分：$\Sigma_1$（上半球面 $z = \sqrt{a^2-x^2-y^2}$，上侧）和 $\Sigma_2$（下半球面 $z = -\sqrt{a^2-x^2-y^2}$，下侧）。

$$\iint_{\Sigma_1} z\,dxdy = \iint_{D_{xy}} \sqrt{a^2-x^2-y^2}\,dxdy$$

$$\iint_{\Sigma_2} z\,dxdy = -\iint_{D_{xy}} (-\sqrt{a^2-x^2-y^2})\,dxdy = \iint_{D_{xy}} \sqrt{a^2-x^2-y^2}\,dxdy$$

两部分相同！总和：

$$\iint_\Sigma z\,dxdy = 2\iint_{D_{xy}} \sqrt{a^2-x^2-y^2}\,dxdy = 2\int_0^{2\pi}\int_0^a \sqrt{a^2-r^2}\,rdrd\theta$$

$$= 2 \cdot 2\pi \cdot \left[-\frac{1}{3}(a^2-r^2)^{3/2}\right]_0^a = 4\pi \cdot \frac{a^3}{3} = \frac{4\pi a^3}{3}$$

---

### 方法二：高斯公式

> [!important|blue] 定理：高斯公式（Gauss Formula / 散度定理）
> 设空间闭区域 $\Omega$ 由分片光滑的闭曲面 $\Sigma$ 围成，$P, Q, R$ 在 $\Omega$ 上有一阶连续偏导数，则
> $$\oiint_\Sigma P\,dydz + Q\,dzdx + R\,dxdy = \iiint_\Omega \left(\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\right) dxdydz$$
>
> 其中 $\Sigma$ 取**外侧**（法向量朝外）。
>
> **向量形式：** 设 $\boldsymbol{F} = (P, Q, R)$，则
> $$\oiint_\Sigma \boldsymbol{F} \cdot d\boldsymbol{S} = \iiint_\Omega \nabla \cdot \boldsymbol{F}\,dV = \iiint_\Omega \text{div}\,\boldsymbol{F}\,dV$$
>
> 其中 $\text{div}\,\boldsymbol{F} = \dfrac{\partial P}{\partial x} + \dfrac{\partial Q}{\partial y} + \dfrac{\partial R}{\partial z}$ 为散度。
>
> **注意：** 高斯公式将闭曲面上的第二类曲面积分转化为三重积分，简化计算。

#### 例题 2

计算 $\oiint_\Sigma x\,dydz + y\,dzdx + z\,dxdy$，其中 $\Sigma$ 为立方体 $0 \le x, y, z \le 1$ 的外侧表面。

**解：** $P = x$，$Q = y$，$R = z$。

$$\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z} = 1 + 1 + 1 = 3$$

由高斯公式：$\oiint_\Sigma = \iiint_\Omega 3\,dV = 3 \times 1 = 3$。

---

#### 例题 3

计算 $\oiint_\Sigma x^3\,dydz + y^3\,dzdx + z^3\,dxdy$，其中 $\Sigma$ 为球面 $x^2+y^2+z^2 = a^2$ 的外侧。

**解：** $P = x^3$，$Q = y^3$，$R = z^3$。

$$\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z} = 3x^2 + 3y^2 + 3z^2 = 3(x^2+y^2+z^2)$$

由高斯公式：

$$\oiint_\Sigma = \iiint_\Omega 3(x^2+y^2+z^2)\,dV = 3\int_0^{2\pi}\int_0^\pi\int_0^a r^2 \cdot r^2\sin\varphi\,drd\varphi d\theta$$

$$= 3 \cdot 2\pi \cdot 2 \cdot \frac{a^5}{5} = \frac{12\pi a^5}{5}$$

---

## 四、高斯公式的应用

### 应用一：求空间区域的体积

取 $P = x$，$Q = 0$，$R = 0$，则

$$\oiint_\Sigma x\,dydz = \iiint_\Omega 1\,dV = V$$

类似地：$V = \dfrac{1}{3}\oiint_\Sigma x\,dydz + y\,dzdx + z\,dxdy$。

### 应用二：补面法

当 $\Sigma$ 不是闭曲面时，补上一个简单的曲面 $\Sigma'$ 使之成为闭曲面，用高斯公式后再减去 $\Sigma'$ 上的积分。

#### 例题 4

计算 $\iint_\Sigma x\,dydz + y\,dzdx + z\,dxdy$，其中 $\Sigma$ 为上半球面 $z = \sqrt{a^2-x^2-y^2}$ 的上侧。

**解：** 补底面 $\Sigma'$：$z = 0$，$x^2+y^2 \le a^2$，取下侧。

$\Sigma + \Sigma'$ 构成闭曲面（取外侧），由高斯公式：

$$\oiint_{\Sigma+\Sigma'} = \iiint_\Omega (1+1+1)\,dV = 3 \cdot \frac{2\pi a^3}{3} = 2\pi a^3$$

在 $\Sigma'$ 上：$z = 0$，$dxdy$ 对应 $z$ 分量，下侧取负：

$$\iint_{\Sigma'} z\,dxdy = -\iint_{D_{xy}} 0\,dxdy = 0$$

（$x\,dydz$ 和 $y\,dzdx$ 在 $z = 0$ 上的投影也都是 0）

$$\iint_\Sigma = 2\pi a^3 - 0 = 2\pi a^3$$

---

## 五、典型例题汇总

#### 例题 5

计算 $\iint_\Sigma (x^2+y^2)\,dxdy$，其中 $\Sigma$ 为锥面 $z = \sqrt{x^2+y^2}$ 被 $z = 1$ 截下部分的下侧。

**解：** 下侧取负号，$D_{xy}$：$x^2+y^2 \le 1$。

$$\iint_\Sigma (x^2+y^2)\,dxdy = -\iint_{D_{xy}} (x^2+y^2)\,dxdy = -\int_0^{2\pi}\int_0^1 r^2 \cdot r\,drd\theta = -2\pi \cdot \frac{1}{4} = -\frac{\pi}{2}$$

#### 例题 6

计算 $\oiint_\Sigma \dfrac{x\,dydz + y\,dzdx + z\,dxdy}{(x^2+y^2+z^2)^{3/2}}$，其中 $\Sigma$ 为任意不包含原点的光滑闭曲面外侧。

**解：** $P = \dfrac{x}{r^3}$，$Q = \dfrac{y}{r^3}$，$R = \dfrac{z}{r^3}$，其中 $r = \sqrt{x^2+y^2+z^2}$。

$$\frac{\partial P}{\partial x} = \frac{r^3 - x \cdot 3r^2 \cdot \frac{x}{r}}{r^6} = \frac{r^2 - 3x^2}{r^5}$$

类似地：$\dfrac{\partial Q}{\partial y} = \dfrac{r^2 - 3y^2}{r^5}$，$\dfrac{\partial R}{\partial z} = \dfrac{r^2 - 3z^2}{r^5}$。

$$\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z} = \frac{3r^2 - 3(x^2+y^2+z^2)}{r^5} = \frac{3r^2 - 3r^2}{r^5} = 0$$

由于 $\Sigma$ 不包含原点，散度在 $\Omega$ 内处处为 0，由高斯公式：

$$\oiint_\Sigma = \iiint_\Omega 0\,dV = 0$$

> **注意：** 若 $\Sigma$ 包含原点，高斯公式不适用（$P, Q, R$ 在原点处不连续），需要用小球面法。此时积分值为 $4\pi$。

---

## 六、高斯公式与格林公式的对比

| | 格林公式 | 高斯公式 |
|:---:|:---:|:---:|
| 维度 | 二维 | 三维 |
| 积分对象 | 平面闭曲线 $L$ | 空间闭曲面 $\Sigma$ |
| 区域 | 平面区域 $D$ | 空间区域 $\Omega$ |
| 转化 | 曲线积分 $\to$ 二重积分 | 曲面积分 $\to$ 三重积分 |
| 核心量 | $\dfrac{\partial Q}{\partial x} - \dfrac{\partial P}{\partial y}$ | $\dfrac{\partial P}{\partial x} + \dfrac{\partial Q}{\partial y} + \dfrac{\partial R}{\partial z}$ |
| 方向 | 逆时针 | 外侧 |

---

## 七、易错点总结

> 1. **第二类曲面积分与曲面的侧有关**：外侧为正向，内侧为负向。上侧对应 $dxdy > 0$，下侧对应 $dxdy < 0$。
> 2. **投影法中正负号的判断**：$\iint_\Sigma R\,dxdy = \pm\iint_{D_{xy}} R\,dxdy$，上侧取正，下侧取负。
> 3. **高斯公式的条件**：$P, Q, R$ 在 $\Omega$ 内有连续偏导数。若有奇点（如 $\frac{1}{r^3}$ 在原点），需挖去奇点后用高斯公式。
> 4. **合一投影法中 $dzdx$ 的正负号**：$dzdx$ 对应法向量的 $y$ 分量符号，右侧为正，左侧为负。注意不是 $\cos\beta$ 的简单替换。
> 5. **补面法**：补的面要取适当的方向，使得 $\Sigma + \Sigma'$ 构成闭曲面的正确侧。$\Sigma'$ 上的积分通常较简单。
> 6. **高斯公式右边的散度是加号**：$\dfrac{\partial P}{\partial x} + \dfrac{\partial Q}{\partial y} + \dfrac{\partial R}{\partial z}$，不要和格林公式中的减号混淆。
> 7. **$dydz, dzdx, dxdy$ 三个投影的对应关系**：$dydz$ 对应法向量的 $x$ 分量，$dzdx$ 对应 $y$ 分量，$dxdy$ 对应 $z$ 分量。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 59：第一类曲面积分]] — 第一类
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 58：第二类曲线积分]] — 曲线积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 61：场论初步]] — 场论
