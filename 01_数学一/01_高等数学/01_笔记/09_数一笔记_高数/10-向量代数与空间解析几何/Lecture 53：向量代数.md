---
title: Lecture 53：向量代数
tags: [考研, 数学一, 高等数学, 数学, 向量代数, 空间解析几何, 点积, 叉积]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 53：向量代数

## 一、向量的基本概念

> [!important|purple] 定义：向量
> 既有大小又有方向的量称为**向量**（矢量），记作 $\vec{a}$ 或 $\boldsymbol{a}$。
>
> **向量的坐标表示：** 若 $\vec{a}$ 在三个坐标轴上的投影分别为 $a_x, a_y, a_z$，则
> $$\vec{a} = a_x\boldsymbol{i} + a_y\boldsymbol{j} + a_z\boldsymbol{k} = (a_x, a_y, a_z)$$
>
> **向量的模（大小）：**
> $$|\vec{a}| = \sqrt{a_x^2 + a_y^2 + a_z^2}$$
>
> **单位向量：** 模为 1 的向量。$\vec{a}$ 方向的单位向量：
> $$\vec{a}^0 = \frac{\vec{a}}{|\vec{a}|} = \left(\frac{a_x}{|\vec{a}|}, \frac{a_y}{|\vec{a}|}, \frac{a_z}{|\vec{a}|}\right)$$
>
> **方向余弦：** 设 $\vec{a}$ 与 $x, y, z$ 轴的夹角分别为 $\alpha, \beta, \gamma$，则
> $$\cos\alpha = \frac{a_x}{|\vec{a}|}, \quad \cos\beta = \frac{a_y}{|\vec{a}|}, \quad \cos\gamma = \frac{a_z}{|\vec{a}|}$$
> 且 $\cos^2\alpha + \cos^2\beta + \cos^2\gamma = 1$。

---

## 二、向量的线性运算

> [!important|blue] 定理：向量的加法与数乘
>
> **加法（平行四边形法则 / 三角形法则）：**
> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$，则
> $$\vec{a} + \vec{b} = (a_x + b_x,\; a_y + b_y,\; a_z + b_z)$$
>
> **减法：**
> $$\vec{a} - \vec{b} = (a_x - b_x,\; a_y - b_y,\; a_z - b_z)$$
>
> **数乘：** 设 $\lambda$ 为实数，
> $$\lambda\vec{a} = (\lambda a_x,\; \lambda a_y,\; \lambda a_z)$$
> - $\lambda > 0$：方向不变，模变为 $|\lambda||\vec{a}|$
> - $\lambda < 0$：方向反向，模变为 $|\lambda||\vec{a}|$
> - $\lambda = 0$：得到零向量 $\vec{0}$
>
> **运算律：**
> - 交换律：$\vec{a} + \vec{b} = \vec{b} + \vec{a}$
> - 结合律：$(\vec{a} + \vec{b}) + \vec{c} = \vec{a} + (\vec{b} + \vec{c})$
> - 分配律：$\lambda(\vec{a} + \vec{b}) = \lambda\vec{a} + \lambda\vec{b}$

**向量共线的条件：** $\vec{a} \parallel \vec{b}$ $\Leftrightarrow$ 存在 $\lambda$ 使得 $\vec{a} = \lambda\vec{b}$ $\Leftrightarrow$ $\dfrac{a_x}{b_x} = \dfrac{a_y}{b_y} = \dfrac{a_z}{b_z}$（对应分量成比例）。

---

## 三、数量积（点积、内积）

> [!important|blue] 定理：数量积的定义与公式
>
> **定义：** $\vec{a} \cdot \vec{b} = |\vec{a}||\vec{b}|\cos\theta$，其中 $\theta$ 是 $\vec{a}$ 与 $\vec{b}$ 的夹角（$0 \le \theta \le \pi$）。
>
> **坐标公式：**
> $$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z$$
>
> **性质：**
> 1. 交换律：$\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$
> 2. 分配律：$\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$
> 3. $\vec{a} \cdot \vec{a} = |\vec{a}|^2$
> 4. $\vec{a} \cdot \vec{b} = 0 \Leftrightarrow \vec{a} \perp \vec{b}$（当 $\vec{a}, \vec{b}$ 为非零向量时）
>
> **几何意义：** $\vec{a} \cdot \vec{b}$ 等于 $\vec{a}$ 的模乘以 $\vec{b}$ 在 $\vec{a}$ 方向上的投影，即
> $$\vec{a} \cdot \vec{b} = |\vec{a}| \cdot \text{Prj}_{\vec{a}}\vec{b}$$

**两向量夹角公式：**
$$\cos\theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}||\vec{b}|} = \frac{a_x b_x + a_y b_y + a_z b_z}{\sqrt{a_x^2+a_y^2+a_z^2}\sqrt{b_x^2+b_y^2+b_z^2}}$$

#### 例题 1

设 $\vec{a} = (1, 2, -1)$，$\vec{b} = (2, -1, 1)$，求 $\vec{a} \cdot \vec{b}$ 和夹角 $\theta$。

**解：**
$$\vec{a} \cdot \vec{b} = 1 \times 2 + 2 \times (-1) + (-1) \times 1 = 2 - 2 - 1 = -1$$

$$|\vec{a}| = \sqrt{1+4+1} = \sqrt{6}, \quad |\vec{b}| = \sqrt{4+1+1} = \sqrt{6}$$

$$\cos\theta = \frac{-1}{\sqrt{6}\cdot\sqrt{6}} = -\frac{1}{6}, \quad \theta = \arccos\left(-\frac{1}{6}\right)$$

---

## 四、向量积（叉积、外积）

> [!important|blue] 定理：向量积的定义与公式
>
> **定义：** $\vec{a} \times \vec{b}$ 是一个向量，满足：
> 1. **方向：** $\vec{a} \times \vec{b}$ 垂直于 $\vec{a}$ 和 $\vec{b}$ 所确定的平面，且 $\vec{a}, \vec{b}, \vec{a} \times \vec{b}$ 构成右手系。
> 2. **大小：** $|\vec{a} \times \vec{b}| = |\vec{a}||\vec{b}|\sin\theta$（$\theta$ 为夹角）。
>
> **坐标公式（行列式形式）：**
> $$\vec{a} \times \vec{b} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ a_x & a_y & a_z \\ b_x & b_y & b_z \end{vmatrix} = (a_y b_z - a_z b_y)\boldsymbol{i} - (a_x b_z - a_z b_x)\boldsymbol{j} + (a_x b_y - a_y b_x)\boldsymbol{k}$$
>
> 简记为：
> $$\vec{a} \times \vec{b} = (a_y b_z - a_z b_y,\; a_z b_x - a_x b_z,\; a_x b_y - a_y b_x)$$
>
> **性质：**
> 1. **反交换律：** $\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$（叉积不满足交换律！）
> 2. 分配律：$\vec{a} \times (\vec{b} + \vec{c}) = \vec{a} \times \vec{b} + \vec{a} \times \vec{c}$
> 3. $\lambda(\vec{a} \times \vec{b}) = (\lambda\vec{a}) \times \vec{b} = \vec{a} \times (\lambda\vec{b})$
> 4. $\vec{a} \times \vec{a} = \vec{0}$
> 5. $\vec{a} \times \vec{b} = \vec{0} \Leftrightarrow \vec{a} \parallel \vec{b}$（当 $\vec{a}, \vec{b}$ 为非零向量时）
>
> **几何意义：** $|\vec{a} \times \vec{b}|$ 等于以 $\vec{a}, \vec{b}$ 为邻边的**平行四边形的面积**。

#### 例题 2

设 $\vec{a} = (1, 0, 1)$，$\vec{b} = (1, 1, 0)$，求 $\vec{a} \times \vec{b}$。

**解：**
$$\vec{a} \times \vec{b} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ 1 & 0 & 1 \\ 1 & 1 & 0 \end{vmatrix} = (0-1)\boldsymbol{i} - (0-1)\boldsymbol{j} + (1-0)\boldsymbol{k} = (-1, 1, 1)$$

---

## 五、混合积（三重积）

> [!important|blue] 定理：混合积的定义与公式
>
> **定义：** 三个向量 $\vec{a}, \vec{b}, \vec{c}$ 的混合积为
> $$[\vec{a}\;\vec{b}\;\vec{c}] = (\vec{a} \times \vec{b}) \cdot \vec{c}$$
>
> **行列式公式：**
> $$(\vec{a} \times \vec{b}) \cdot \vec{c} = \begin{vmatrix} a_x & a_y & a_z \\ b_x & b_y & b_z \\ c_x & c_y & c_z \end{vmatrix}$$
>
> **性质：**
> 1. 轮换不变性：$(\vec{a} \times \vec{b}) \cdot \vec{c} = (\vec{b} \times \vec{c}) \cdot \vec{a} = (\vec{c} \times \vec{a}) \cdot \vec{b}$
> 2. 交换两个相邻向量变号：$(\vec{a} \times \vec{b}) \cdot \vec{c} = -(\vec{b} \times \vec{a}) \cdot \vec{c}$
> 3. 混合积的绝对值等于以 $\vec{a}, \vec{b}, \vec{c}$ 为棱的**平行六面体的体积**：
> $$V = |(\vec{a} \times \vec{b}) \cdot \vec{c}|$$
> 4. 三向量共面 $\Leftrightarrow$ $(\vec{a} \times \vec{b}) \cdot \vec{c} = 0$

#### 例题 3

设 $\vec{a} = (1, 1, 0)$，$\vec{b} = (0, 1, 1)$，$\vec{c} = (1, 0, 1)$，求混合积和以它们为棱的平行六面体体积。

**解：**
$$(\vec{a} \times \vec{b}) \cdot \vec{c} = \begin{vmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{vmatrix} = 1(1-0) - 1(0-1) + 0(0-1) = 1 + 1 + 0 = 2$$

平行六面体体积 $V = |2| = 2$。

---

## 六、向量平行与垂直的判定

> [!important|blue] 定理：平行与垂直的判定方法
>
> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$ 为非零向量。
>
> **垂直 $\Leftrightarrow$ 点积为零：**
> $$\vec{a} \perp \vec{b} \;\Leftrightarrow\; \vec{a} \cdot \vec{b} = 0 \;\Leftrightarrow\; a_x b_x + a_y b_y + a_z b_z = 0$$
>
> **平行 $\Leftrightarrow$ 叉积为零：**
> $$\vec{a} \parallel \vec{b} \;\Leftrightarrow\; \vec{a} \times \vec{b} = \vec{0} \;\Leftrightarrow\; \frac{a_x}{b_x} = \frac{a_y}{b_y} = \frac{a_z}{b_z}$$
>
> **记忆口诀：** 点乘为零判断垂直，叉乘为零判断平行。与二维情形一致。

**向量投影公式：**

$\vec{a}$ 在 $\vec{b}$ 上的投影（标量投影）：
$$\text{Prj}_{\vec{b}}\vec{a} = \frac{\vec{a} \cdot \vec{b}}{|\vec{b}|} = |\vec{a}|\cos\theta$$

$\vec{a}$ 在 $\vec{b}$ 上的投影向量：
$$\text{proj}_{\vec{b}}\vec{a} = \frac{\vec{a} \cdot \vec{b}}{|\vec{b}|^2}\vec{b}$$

#### 例题 4

判断 $\vec{a} = (2, -1, 1)$ 与 $\vec{b} = (1, 2, 0)$ 是否垂直，与 $\vec{c} = (4, -2, 2)$ 是否平行。

**解：**
- $\vec{a} \cdot \vec{b} = 2 \times 1 + (-1) \times 2 + 1 \times 0 = 0$，故 $\vec{a} \perp \vec{b}$。
- $\dfrac{4}{2} = \dfrac{-2}{-1} = \dfrac{2}{1} = 2$，对应分量成比例，故 $\vec{a} \parallel \vec{c}$。

---

## 七、三种乘积的对比总结

| | 数量积（点积） | 向量积（叉积） | 混合积 |
|:---:|:---:|:---:|:---:|
| 记号 | $\vec{a} \cdot \vec{b}$ | $\vec{a} \times \vec{b}$ | $(\vec{a} \times \vec{b}) \cdot \vec{c}$ |
| 结果 | **标量** | **向量** | **标量** |
| 公式 | $a_x b_x + a_y b_y + a_z b_z$ | 行列式展开 | $3\times3$ 行列式 |
| 交换律 | $\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$ ✓ | $\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$ ✗ | 轮换不变 |
| 几何意义 | 投影 | 平行四边形面积 | 平行六面体体积 |
| 判定 | 垂直：$= 0$ | 平行：$= \vec{0}$ | 共面：$= 0$ |

---

## 八、典型例题

#### 例题 5

已知 $|\vec{a}| = 2$，$|\vec{b}| = 3$，$\vec{a}$ 与 $\vec{b}$ 的夹角为 $\dfrac{\pi}{3}$，求 $|2\vec{a} - 3\vec{b}|$。

**解：**
$$|2\vec{a} - 3\vec{b}|^2 = (2\vec{a} - 3\vec{b}) \cdot (2\vec{a} - 3\vec{b}) = 4|\vec{a}|^2 - 12\vec{a}\cdot\vec{b} + 9|\vec{b}|^2$$

$$= 4 \times 4 - 12 \times 2 \times 3 \times \cos\frac{\pi}{3} + 9 \times 9 = 16 - 12 \times 6 \times \frac{1}{2} + 81 = 16 - 36 + 81 = 61$$

$$|2\vec{a} - 3\vec{b}| = \sqrt{61}$$

#### 例题 6

求与 $\vec{a} = (1, -2, 1)$ 和 $\vec{b} = (2, 1, -1)$ 都垂直的单位向量。

**解：** 所求向量与 $\vec{a}$ 和 $\vec{b}$ 都垂直，即平行于 $\vec{a} \times \vec{b}$。

$$\vec{a} \times \vec{b} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ 1 & -2 & 1 \\ 2 & 1 & -1 \end{vmatrix} = (2-1)\boldsymbol{i} - (-1-2)\boldsymbol{j} + (1+4)\boldsymbol{k} = (1, 3, 5)$$

$$|\vec{a} \times \vec{b}| = \sqrt{1+9+25} = \sqrt{35}$$

所求单位向量为 $\pm\dfrac{1}{\sqrt{35}}(1, 3, 5)$。

#### 例题 7

设三点 $A(1, 0, 0)$，$B(0, 1, 0)$，$C(0, 0, 1)$，求三角形 $ABC$ 的面积。

**解：**
$$\vec{AB} = (-1, 1, 0), \quad \vec{AC} = (-1, 0, 1)$$

$$\vec{AB} \times \vec{AC} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ -1 & 1 & 0 \\ -1 & 0 & 1 \end{vmatrix} = (1, 1, 1)$$

$$S = \frac{1}{2}|\vec{AB} \times \vec{AC}| = \frac{1}{2}\sqrt{1+1+1} = \frac{\sqrt{3}}{2}$$

---

## 九、易错点总结

> 1. **点积是标量，叉积是向量**：$\vec{a} \cdot \vec{b}$ 是数，$\vec{a} \times \vec{b}$ 是向量，二者完全不同。
> 2. **叉积不满足交换律**：$\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$，方向相反！
> 3. **叉积行列式的展开**：第二列要加负号，即 $-(a_x b_z - a_z b_x)$，不要漏掉符号。
> 4. **混合积的轮换性质**：只能轮换 $(a,b,c) \to (b,c,a) \to (c,a,b)$，不能任意交换，交换相邻两个要变号。
> 5. **平行判定用叉积，垂直判定用点积**：不要混淆。
> 6. **分量成比例判平行时**：如果某分量为 0，对应分量也必须为 0，不能用 0 做分母。应检查 $a_x b_y - a_y b_x = 0$，$a_y b_z - a_z b_y = 0$，$a_z b_x - a_x b_z = 0$ 三个条件同时成立。
> 7. **求面积用叉积的模的一半**：三角形面积 $S = \frac{1}{2}|\vec{a} \times \vec{b}|$，不要忘记 $\frac{1}{2}$。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/10-向量代数与空间解析几何/Lecture 54：空间平面与直线]] — 平面直线
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 57：第一类曲线积分]] — 曲线积分
