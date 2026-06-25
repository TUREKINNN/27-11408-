---
title: Lecture 07 - 向量代数与空间解析几何
subject: 高等数学
chapter: 第四章
lecture: 07
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 07: 向量代数与空间解析几何

## 一、空间直角坐标系

### 1.1 空间直角坐标系的建立

<span style="background-color: #ccc1d9">**定义（空间直角坐标系）**</span> 在空间中取一点 $O$，过 $O$ 作三条两两垂直的数轴 $Ox$、$Oy$、$Oz$，统称为坐标轴。它们的正方向符合右手系（右手握住 $z$ 轴，大拇指指向 $z$ 轴正方向，四指指向 $x$ 轴正方向的旋转方向）。

- **坐标原点**：$O$
- **坐标轴**：$x$ 轴（横轴）、$y$ 轴（纵轴）、$z$ 轴（竖轴）
- **坐标平面**：$xOy$ 平面、$yOz$ 平面、$zOx$ 平面

### 1.2 空间中点的坐标

<span style="background-color: #ccc1d9">**定义（空间点的坐标）**</span> 设空间一点 $M$，过 $M$ 作三个平面分别垂直于三条坐标轴，它们与坐标轴的交点分别为 $P$、$Q$、$R$。若这三个点在 $x$、$y$、$z$ 轴上的坐标分别为 $x$、$y$、$z$，则称有序实数 $(x, y, z)$ 为点 $M$ 的坐标，记作 $M(x, y, z)$。

### 1.3 空间两点间的距离

<span style="background-color: #8db3e2">**定理（空间两点距离公式）**</span> 设空间两点 $M_1(x_1, y_1, z_1)$ 和 $M_2(x_2, y_2, z_2)$，则它们之间的距离为：

$$d = |M_1M_2| = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2 + (z_2 - z_1)^2}$$

---

## 二、向量的概念与表示

### 2.1 向量的定义

<span style="background-color: #ccc1d9">**定义（向量）**</span> 既有大小又有方向的量称为**向量**（或**矢量**）。记作 $\vec{AB}$ 或 $\vec{a}$。

- **向量的模**：向量的大小，记作 $|\vec{a}|$ 或 $|\vec{AB}|$
- **单位向量**：模等于 1 的向量，记作 $\vec{a}^0$ 或 $\vec{e}_a$
- **零向量**：模等于 0 的向量，记作 $\vec{0}$

### 2.2 向量的坐标表示

<span style="background-color: #ccc1d9">**定义（向量的坐标）**</span> 若向量 $\vec{a}$ 在三条坐标轴上的投影分别为 $a_x$、$a_y$、$a_z$，则称有序实数 $(a_x, a_y, a_z)$ 为向量 $\vec{a}$ 的坐标，记作 $\vec{a} = (a_x, a_y, a_z)$。

<span style="background-color: #8db3e2">**定理（向量的模的坐标公式）**</span>

$$|\vec{a}| = \sqrt{a_x^2 + a_y^2 + a_z^2}$$

---

## 三、向量的线性运算

### 3.1 向量的加法

<span style="background-color: #ccc1d9">**定义（向量加法）**</span> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$，则

$$\vec{a} + \vec{b} = (a_x + b_x, a_y + b_y, a_z + b_z)$$

**几何意义**：平行四边形法则或三角形法则。

### 3.2 向量的减法

<span style="background-color: #ccc1d9">**定义（向量减法）**</span>

$$\vec{a} - \vec{b} = (a_x - b_x, a_y - b_y, a_z - b_z)$$

### 3.3 向量的数乘

<span style="background-color: #ccc1d9">**定义（向量数乘）**</span> 设 $\lambda$ 为实数，向量 $\vec{a} = (a_x, a_y, a_z)$，则

$$\lambda\vec{a} = (\lambda a_x, \lambda a_y, \lambda a_z)$$

<span style="background-color: #8db3e2">**定理（数乘的几何意义）**</span>
- $\lambda > 0$ 时，$\lambda\vec{a}$ 与 $\vec{a}$ 同向，模扩大 $|\lambda|$ 倍
- $\lambda < 0$ 时，$\lambda\vec{a}$ 与 $\vec{a}$ 反向，模扩大 $|\lambda|$ 倍
- $\lambda = 0$ 时，$\lambda\vec{a} = \vec{0}$

---

## 四、向量的数量积（点积、内积）

### 4.1 数量积的定义

<span style="background-color: #ccc1d9">**定义（数量积）**</span> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$，称

$$\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z$$

为向量 $\vec{a}$ 与 $\vec{b}$ 的**数量积**（或**点积**、**内积**）。

### 4.2 数量积的性质

<span style="background-color: #8db3e2">**定理（数量积的性质）**</span>

1. $\vec{a} \cdot \vec{b} = \vec{b} \cdot \vec{a}$（交换律）
2. $\vec{a} \cdot (\vec{b} + \vec{c}) = \vec{a} \cdot \vec{b} + \vec{a} \cdot \vec{c}$（分配律）
3. $(\lambda\vec{a}) \cdot \vec{b} = \lambda(\vec{a} \cdot \vec{b})$（结合律）
4. $\vec{a} \cdot \vec{a} = |\vec{a}|^2$

### 4.3 数量积的几何应用

<span style="background-color: #8db3e2">**定理（夹角公式）**</span> 两向量夹角余弦为：

$$\cos\theta = \frac{\vec{a} \cdot \vec{b}}{|\vec{a}| |\vec{b}|} = \frac{a_x b_x + a_y b_y + a_z b_z}{\sqrt{a_x^2 + a_y^2 + a_z^2} \cdot \sqrt{b_x^2 + b_y^2 + b_z^2}}$$

### 4.4 两向量垂直的条件

<span style="background-color: #8db3e2">**定理（垂直条件）**</span> $\vec{a} \perp \vec{b} \Leftrightarrow \vec{a} \cdot \vec{b} = 0$

---

## 五、向量的向量积（叉积、外积）

### 5.1 向量积的定义

<span style="background-color: #ccc1d9">**定义（向量积）**</span> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$，则

$$\vec{a} \times \vec{b} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ a_x & a_y & a_z \\ b_x & b_y & b_z \end{vmatrix}$$

$$= (a_y b_z - a_z b_y, a_z b_x - a_x b_z, a_x b_y - a_y b_x)$$

### 5.2 向量积的性质

<span style="background-color: #8db3e2">**定理（向量积的性质）**</span>

1. $\vec{a} \times \vec{b} \perp \vec{a}$ 且 $\vec{a} \times \vec{b} \perp \vec{b}$
2. $|\vec{a} \times \vec{b}| = |\vec{a}| |\vec{b}| \sin\theta$（表示以 $\vec{a}$、$\vec{b}$ 为边的平行四边形面积）
3. $\vec{a} \times \vec{b} = -\vec{b} \times \vec{a}$（反交换律）
4. $\vec{a} \times \vec{a} = \vec{0}$

### 5.3 两向量平行的条件

<span style="background-color: #8db3e2">**定理（平行条件）**</span> $\vec{a} \parallel \vec{b} \Leftrightarrow \vec{a} \times \vec{b} = \vec{0}$

---

## 六、向量的混合积

### 6.1 混合积的定义

<span style="background-color: #ccc1d9">**定义（混合积）**</span> 设 $\vec{a} = (a_x, a_y, a_z)$，$\vec{b} = (b_x, b_y, b_z)$，$\vec{c} = (c_x, c_y, c_z)$，称

$$(\vec{a} \times \vec{b}) \cdot \vec{c} = \begin{vmatrix} a_x & a_y & a_z \\ b_x & b_y & b_z \\ c_x & c_y & c_z \end{vmatrix}$$

为三个向量的**混合积**，记作 $[\vec{a}\vec{b}\vec{c}]$。

### 6.2 混合积的几何意义

<span style="background-color: #8db3e2">**定理（混合积的几何意义）**</span> $|(\vec{a} \times \vec{b}) \cdot \vec{c}|$ 等于以 $\vec{a}$、$\vec{b}$、$\vec{c}$ 为棱的平行六面体的体积。

---

## 七、向量的夹角与方向余弦

### 7.1 方向角与方向余弦

<span style="background-color: #ccc1d9">**定义（方向角）**</span> 向量 $\vec{a}$ 与三条坐标轴正向的夹角 $\alpha$、$\beta$、$\gamma$ 称为 $\vec{a}$ 的**方向角**。

<span style="background-color: #ccc1d9">**定义（方向余弦）**</span>

$$\cos\alpha = \frac{a_x}{|\vec{a}|}, \quad \cos\beta = \frac{a_y}{|\vec{a}|}, \quad \cos\gamma = \frac{a_z}{|\vec{a}|}$$

<span style="background-color: #8db3e2">**定理（方向余弦的性质）**</span>

$$\cos^2\alpha + \cos^2\beta + \cos^2\gamma = 1$$

---

## 八、平面方程

### 8.1 平面方程的各种形式

#### （1）点法式方程

<span style="background-color: #ccc1d9">**定义（平面的点法式）**</span> 已知平面 $\Pi$ 上一点 $M_0(x_0, y_0, z_0)$ 和它的一个法向量 $\vec{n} = (A, B, C)$，则平面 $\Pi$ 的方程为：

$$A(x - x_0) + B(y - y_0) + C(z - z_0) = 0$$

#### （2）一般式方程

<span style="background-color: #ccc1d9">**定义（平面的一般式）**</span>

$$Ax + By + Cz + D = 0$$

其中 $\vec{n} = (A, B, C)$ 为平面的法向量。

#### （3）截距式方程

<span style="background-color: #ccc1d9">**定义（平面的截距式）**</span>

$$\frac{x}{a} + \frac{y}{b} + \frac{z}{c} = 1 \quad (a, b, c \neq 0)$$

其中 $a$、$b$、$c$ 分别为平面在 $x$、$y$、$z$ 轴上的截距。

---

## 九、直线方程

### 9.1 直线方程的各种形式

#### （1）点向式（对称式）方程

<span style="background-color: #ccc1d9">**定义（直线的点向式）**</span> 已知直线 $L$ 上一点 $M_0(x_0, y_0, z_0)$ 和它的一个方向向量 $\vec{s} = (m, n, p)$，则直线 $L$ 的方程为：

$$\frac{x - x_0}{m} = \frac{y - y_0}{n} = \frac{z - z_0}{p}$$

#### （2）参数式方程

<span style="background-color: #ccc1d9">**定义（直线的参数式）**</span>

$$x = x_0 + mt, \quad y = y_0 + nt, \quad z = z_0 + pt$$

#### （3）一般式方程

<span style="background-color: #ccc1d9">**定义（直线的一般式）**</span> 直线可以看作两平面的交线：

$$\begin{cases} A_1x + B_1y + C_1z + D_1 = 0 \\ A_2x + B_2y + C_2z + D_2 = 0 \end{cases}$$

---

## 十、平面与平面的关系

### 10.1 两平面平行

<span style="background-color: #8db3e2">**定理（平面平行的条件）**</span> 两平面 $\Pi_1: A_1x + B_1y + C_1z + D_1 = 0$ 和 $\Pi_2: A_2x + B_2y + C_2z + D_2 = 0$ 平行的充要条件是：

$$\frac{A_1}{A_2} = \frac{B_1}{B_2} = \frac{C_1}{C_2} \neq \frac{D_1}{D_2}$$

### 10.2 两平面垂直

<span style="background-color: #8db3e2">**定理（平面垂直的条件）**</span> 两平面垂直的充要条件是：

$$A_1A_2 + B_1B_2 + C_1C_2 = 0$$

### 10.3 两平面的夹角

<span style="background-color: #8db3e2">**定理（平面夹角公式）**</span> 两平面的夹角 $\theta$ 满足：

$$\cos\theta = \frac{|A_1A_2 + B_1B_2 + C_1C_2|}{\sqrt{A_1^2 + B_1^2 + C_1^2} \cdot \sqrt{A_2^2 + B_2^2 + C_2^2}}$$

---

## 十一、平面与直线的位置关系

### 11.1 直线与平面平行

<span style="background-color: #8db3e2">**定理（直线与平面平行的条件）**</span> 直线 $L: \frac{x - x_0}{m} = \frac{y - y_0}{n} = \frac{z - z_0}{p}$ 与平面 $\Pi: Ax + By + Cz + D = 0$ 平行的充要条件是：

$$Am + Bn + Cp = 0$$

### 11.2 直线与平面垂直

<span style="background-color: #8db3e2">**定理（直线与平面垂直的条件）**</span> 直线与平面垂直的充要条件是：

$$\frac{A}{m} = \frac{B}{n} = \frac{C}{p}$$

### 11.3 直线与平面的夹角

<span style="background-color: #8db3e2">**定理（直线与平面夹角公式）**</span> 直线与平面的夹角 $\varphi$ 满足：

$$\sin\varphi = \frac{|Am + Bn + Cp|}{\sqrt{A^2 + B^2 + C^2} \cdot \sqrt{m^2 + n^2 + p^2}}$$

---

## 十二、直线与直线的位置关系

### 12.1 两直线平行

<span style="background-color: #8db3e2">**定理（直线平行的条件）**</span> 两直线平行的充要条件是它们的方向向量平行。

### 12.2 两直线垂直

<span style="background-color: #8db3e2">**定理（直线垂直的条件）**</span> 两直线垂直的充要条件是它们的方向向量垂直。

### 12.3 两直线的夹角

<span style="background-color: #8db3e2">**定理（异面直线夹角公式）**</span> 设两直线 $L_1$ 和 $L_2$ 的方向向量分别为 $\vec{s}_1 = (m_1, n_1, p_1)$ 和 $\vec{s}_2 = (m_2, n_2, p_2)$，则两直线夹角 $\theta$ 满足：

$$\cos\theta = \frac{|m_1 m_2 + n_1 n_2 + p_1 p_2|}{\sqrt{m_1^2 + n_1^2 + p_1^2} \cdot \sqrt{m_2^2 + n_2^2 + p_2^2}}$$

---

## 十三、点到平面的距离

<span style="background-color: #8db3e2">**定理（点到平面的距离公式）**</span> 点 $P(x_0, y_0, z_0)$ 到平面 $Ax + By + Cz + D = 0$ 的距离为：

$$d = \frac{|Ax_0 + By_0 + Cz_0 + D|}{\sqrt{A^2 + B^2 + C^2}}$$

---

## 十四、点到直线的距离

<span style="background-color: #8db3e2">**定理（点到直线的距离公式）**</span> 点 $P(x_0, y_0, z_0)$ 到直线 $L: \frac{x - x_1}{m} = \frac{y - y_1}{n} = \frac{z - z_1}{p}$ 的距离为：

$$d = \frac{| \vec{PM_0} \times \vec{s} |}{|\vec{s}|} = \frac{\sqrt{(y_0 - y_1)p - (z_0 - z_1)n)^2 + (z_0 - z_1)m - (x_0 - x_1)p)^2 + (x_0 - x_1)n - (y_0 - y_1)m)^2}}{\sqrt{m^2 + n^2 + p^2}}$$

其中 $M_0(x_1, y_1, z_1)$ 为直线上一点，$\vec{s} = (m, n, p)$ 为直线的方向向量。

---

## 十五、曲面方程的概念

<span style="background-color: #ccc1d9">**定义（曲面方程）**</span> 若空间曲面 $S$ 与三元方程 $F(x, y, z) = 0$ 满足：曲面上任意点的坐标都满足该方程，不在曲面上的点的坐标都不满足该方程，则称 $F(x, y, z) = 0$ 为曲面 $S$ 的方程。

---

## 十六、常用二次曲面

### 16.1 椭球面

<span style="background-color: #ccc1d9">**定义（椭球面）**</span>

$$\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c^2} = 1 \quad (a, b, c > 0)$$

当 $a = b = c$ 时为球面。

### 16.2 双曲面

#### （1）单叶双曲面

$$\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = 1$$

#### （2）双叶双曲面

$$\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c^2} = -1$$

### 16.3 抛物面

#### （1）椭圆抛物面

$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = z$$

#### （2）双曲抛物面（马鞍面）

$$\frac{x^2}{a^2} - \frac{y^2}{b^2} = z$$

### 16.4 柱面

<span style="background-color: #ccc1d9">**定义（柱面）**</span> 平行于定直线并沿定曲线移动的直线形成的轨迹。

**常见柱面方程**：
- 圆柱面：$x^2 + y^2 = R^2$
- 椭圆柱面：$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$
- 抛物柱面：$y^2 = 2px$

### 16.5 锥面

<span style="background-color: #ccc1d9">**定义（圆锥面）**</span>

$$\frac{x^2}{a^2} + \frac{y^2}{a^2} = \frac{z^2}{c^2} \quad \text{或} \quad x^2 + y^2 = \frac{c^2}{z^2}$$

---

## 十七、空间曲线方程

### 17.1 空间曲线的一般式方程

<span style="background-color: #ccc1d9">**定义（空间曲线的一般式）**</span>

$$\begin{cases} F(x, y, z) = 0 \\ G(x, y, z) = 0 \end{cases}$$

### 17.2 空间曲线的参数式方程

<span style="background-color: #ccc1d9">**定义（空间曲线的参数式）**</span>

$$x = x(t), \quad y = y(t), \quad z = z(t)$$

**螺旋线参数方程**：

$$x = a\cos\theta, \quad y = a\sin\theta, \quad z = b\theta$$

---

## 十八、典型例题

### 例题1：向量的数量积

**题目**：已知 $\vec{a} = (1, 2, -1)$，$\vec{b} = (2, -1, 3)$，求 $\vec{a} \cdot \vec{b}$。

**思路**：直接利用数量积坐标公式计算。

**解答**：

$$\vec{a} \cdot \vec{b} = 1 \times 2 + 2 \times (-1) + (-1) \times 3 = 2 - 2 - 3 = -3$$

**总结**：数量积就是对应坐标乘积之和。

---

### 例题2：求平面方程

**题目**：求过点 $(1, -2, 3)$ 且与向量 $\vec{n} = (2, -1, 4)$ 垂直的平面方程。

**思路**：利用平面的点法式方程。

**解答**：

由点法式：$2(x - 1) + (-1)(y + 2) + 4(z - 3) = 0$

即 $2x - 2 - y - 2 + 4z - 12 = 0$

化简得 $2x - y + 4z - 16 = 0$

**总结**：已知平面上一店和法向量，直接用法式方程。

---

### 例题3：求直线方程

**题目**：求过两点 $A(1, 0, 2)$ 和 $B(2, 1, 1)$ 的直线方程。

**思路**：利用直线的点向式，先求方向向量 $\vec{AB}$。

**解答**：

方向向量 $\vec{AB} = (2-1, 1-0, 1-2) = (1, 1, -1)$

由点向式方程：

$$\frac{x - 1}{1} = \frac{y - 0}{1} = \frac{z - 2}{-1}$$

**总结**：两点确定一条直线，方向向量为两点坐标差。

---

### 例题4：点到平面距离

**题目**：求点 $P(1, 2, 3)$ 到平面 $2x + y - 2z + 1 = 0$ 的距离。

**思路**：直接代入点到平面距离公式。

**解答**：

$$d = \frac{|2 \times 1 + 1 \times 2 - 2 \times 3 + 1|}{\sqrt{2^2 + 1^2 + (-2)^2}} = \frac{|2 + 2 - 6 + 1|}{\sqrt{4 + 1 + 4}} = \frac{|-1|}{\sqrt{9}} = \frac{1}{3}$$

**总结**：点到平面距离公式是高考重点。

---

### 例题5：判断直线与平面的位置关系

**题目**：判断直线 $\frac{x-1}{2} = \frac{y}{-1} = \frac{z+1}{3}$ 与平面 $x + y - z + 1 = 0$ 的位置关系。

**思路**：计算方向向量与法向量的点积。

**解答**：

直线的方向向量 $\vec{s} = (2, -1, 3)$，平面的法向量 $\vec{n} = (1, 1, -1)$

$\vec{s} \cdot \vec{n} = 2 \times 1 + (-1) \times 1 + 3 \times (-1) = 2 - 1 - 3 = -2 \neq 0$

由于点积不为零，直线与平面既不平行也不垂直，而是斜交。

**总结**：$\vec{s} \cdot \vec{n} = 0$ 时直线与平面平行，$\vec{s}$ 与 $\vec{n}$ 平行时直线与平面垂直。

---

## 九、解题方法总结

### 9.1 向量运算

1. **加法/减法**：对应坐标相加减
2. **数乘**：每个坐标乘以倍数
3. **数量积**：对应坐标乘积之和
4. **向量积**：行列式计算
5. **混合积**：三阶行列式

### 9.2 平面与直线方程

| 类型 | 方程形式 | 关键要素 |
|------|---------|----------|
| 平面点法式 | $A(x-x_0)+B(y-y_0)+C(z-z_0)=0$ | 一点 + 法向量 |
| 平面一般式 | $Ax+By+Cz+D=0$ | 法向量 $(A,B,C)$ |
| 直线点向式 | $\frac{x-x_0}{m}=\frac{y-y_0}{n}=\frac{z-z_0}{p}$ | 一点 + 方向向量 |
| 直线参数式 | $x=x_0+mt$ 等 | 参数 $t$ |

### 9.3 位置关系判断

- **垂直**：数量积为零（向量垂直）或法向量垂直（平面垂直）
- **平行**：向量积为零（向量平行）或法向量平行（平面平行）

---

## 参考答案提示

1. $\vec{a} \cdot \vec{b} = -3$

2. $2x - y + 4z - 16 = 0$

3. $\frac{x - 1}{1} = \frac{y}{1} = \frac{z - 2}{-1}$

4. $d = \frac{1}{3}$

5. 直线与平面斜交

---

> **注**：本 Lecture 内容涵盖向量代数和空间解析几何的基本概念、平面与直线方程、各种位置关系的判定公式及典型例题。建议结合《基础过关660题》对应章节进行练习巩固。
