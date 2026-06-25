---
title: Lecture 54：空间平面与直线
tags: [考研, 数学一, 高等数学, 数学, 空间解析几何, 平面方程, 直线方程, 距离公式]
categories: 高等数学
date: 2026-06-16
---
---

# Lecture 54：空间平面与直线

## 一、平面方程

> [!important|purple] 定义：平面的点法式方程
> 已知平面上一点 $M_0(x_0, y_0, z_0)$ 和法向量 $\boldsymbol{n} = (A, B, C)$，平面方程为：
> $$A(x - x_0) + B(y - y_0) + C(z - z_0) = 0$$

> [!important|purple] 定义：平面的一般式方程
> $$Ax + By + Cz + D = 0$$
> 其中 $\boldsymbol{n} = (A, B, C)$ 为法向量。
>
> 特殊情况：
> - $D = 0$：平面过原点
> - $A = 0$：平面平行于 $x$ 轴
> - $A = B = 0$：平面平行于 $xOy$ 平面，方程为 $Cz + D = 0$

> [!important|purple] 定义：平面的截距式方程
> $$\frac{x}{a} + \frac{y}{b} + \frac{z}{c} = 1$$
> 其中 $a, b, c$ 分别为平面在 $x, y, z$ 轴上的截距（要求 $abc \neq 0$）。

**三点确定平面：** 过三点 $A, B, C$ 的平面方程可用混合积表示：
$$\begin{vmatrix} x - x_A & y - y_A & z - z_A \\ x_B - x_A & y_B - y_A & z_B - z_A \\ x_C - x_A & y_C - y_A & z_C - z_A \end{vmatrix} = 0$$

---

## 二、直线方程

> [!important|purple] 定义：直线的对称式方程（点向式）
> 已知直线上一点 $M_0(x_0, y_0, z_0)$ 和方向向量 $\boldsymbol{s} = (m, n, p)$，直线方程为：
> $$\frac{x - x_0}{m} = \frac{y - y_0}{n} = \frac{z - z_0}{p}$$

> [!important|purple] 定义：直线的参数方程
> $$\begin{cases} x = x_0 + mt \\ y = y_0 + nt \\ z = z_0 + pt \end{cases} \quad (t \in \mathbb{R})$$

> [!important|purple] 定义：直线的一般式方程（两平面交线）
> $$\begin{cases} A_1 x + B_1 y + C_1 z + D_1 = 0 \\ A_2 x + B_2 y + C_2 z + D_2 = 0 \end{cases}$$
> 直线的方向向量为 $\boldsymbol{s} = \boldsymbol{n}_1 \times \boldsymbol{n}_2$，其中 $\boldsymbol{n}_i = (A_i, B_i, C_i)$。

**两点确定直线：** 过两点 $M_1(x_1,y_1,z_1)$，$M_2(x_2,y_2,z_2)$ 的直线方程：
$$\frac{x - x_1}{x_2 - x_1} = \frac{y - y_1}{y_2 - y_1} = \frac{z - z_1}{z_2 - z_1}$$

---

## 三、点到平面的距离

> [!important|blue] 定理：点到平面距离公式
> 点 $M_0(x_0, y_0, z_0)$ 到平面 $Ax + By + Cz + D = 0$ 的距离为：
> $$d = \frac{|Ax_0 + By_0 + Cz_0 + D|}{\sqrt{A^2 + B^2 + C^2}}$$

#### 例题 1

求点 $(1, 2, 3)$ 到平面 $2x - y + 2z - 6 = 0$ 的距离。

**解：**
$$d = \frac{|2 \times 1 - 1 \times 2 + 2 \times 3 - 6|}{\sqrt{4 + 1 + 4}} = \frac{|2 - 2 + 6 - 6|}{3} = 0$$

点在平面上！

---

## 四、点到直线的距离

> [!important|blue] 定理：点到直线距离公式
> 点 $M_1$ 到过点 $M_0$、方向向量为 $\boldsymbol{s}$ 的直线的距离为：
> $$d = \frac{|\overrightarrow{M_0M_1} \times \boldsymbol{s}|}{|\boldsymbol{s}|}$$
>
> 若直线为 $\dfrac{x - x_0}{m} = \dfrac{y - y_0}{n} = \dfrac{z - z_0}{p}$，点为 $(x_1, y_1, z_1)$，则
> $$d = \frac{\sqrt{\begin{vmatrix} y_1 - y_0 & z_1 - z_0 \\ n & p \end{vmatrix}^2 + \begin{vmatrix} z_1 - z_0 & x_1 - x_0 \\ p & m \end{vmatrix}^2 + \begin{vmatrix} x_1 - x_0 & y_1 - y_0 \\ m & n \end{vmatrix}^2}}{\sqrt{m^2 + n^2 + p^2}}$$

#### 例题 2

求点 $P(1, 0, -1)$ 到直线 $\dfrac{x}{1} = \dfrac{y - 1}{2} = \dfrac{z}{-1}$ 的距离。

**解：** 直线上一点 $M_0(0, 1, 0)$，方向向量 $\boldsymbol{s} = (1, 2, -1)$。

$$\overrightarrow{M_0P} = (1, -1, -1)$$

$$\overrightarrow{M_0P} \times \boldsymbol{s} = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ 1 & -1 & -1 \\ 1 & 2 & -1 \end{vmatrix} = (1+2)\boldsymbol{i} - (-1+1)\boldsymbol{j} + (2+1)\boldsymbol{k} = (3, 0, 3)$$

$$d = \frac{|(3, 0, 3)|}{|(1, 2, -1)|} = \frac{\sqrt{9+0+9}}{\sqrt{1+4+1}} = \frac{3\sqrt{2}}{\sqrt{6}} = \frac{3\sqrt{2}}{\sqrt{6}} = \frac{3}{\sqrt{3}} = \sqrt{3}$$

---

## 五、两平面的位置关系

设 $\pi_1: A_1x + B_1y + C_1z + D_1 = 0$，$\pi_2: A_2x + B_2y + C_2z + D_2 = 0$。

> [!important|blue] 定理：两平面的位置关系
>
> **法向量：** $\boldsymbol{n}_1 = (A_1, B_1, C_1)$，$\boldsymbol{n}_2 = (A_2, B_2, C_2)$
>
> | 条件 | 关系 |
> |:---:|:---:|
> | $\dfrac{A_1}{A_2} = \dfrac{B_1}{B_2} = \dfrac{C_1}{C_2}$ | 平行（或重合） |
> | $\dfrac{A_1}{A_2} = \dfrac{B_1}{B_2} = \dfrac{C_1}{C_2} = \dfrac{D_1}{D_2}$ | 重合 |
> | $\boldsymbol{n}_1 \cdot \boldsymbol{n}_2 = 0$ | 垂直 |
> | 以上都不满足 | 斜交 |
>
> **两平面的夹角（二面角）：**
> $$\cos\theta = \frac{|\boldsymbol{n}_1 \cdot \boldsymbol{n}_2|}{|\boldsymbol{n}_1||\boldsymbol{n}_2|} = \frac{|A_1 A_2 + B_1 B_2 + C_1 C_2|}{\sqrt{A_1^2+B_1^2+C_1^2}\sqrt{A_2^2+B_2^2+C_2^2}}$$
>
> 注意取绝对值，夹角取 $[0, \frac{\pi}{2}]$。

---

## 六、两直线的位置关系

设 $L_1: \dfrac{x - x_1}{m_1} = \dfrac{y - y_1}{n_1} = \dfrac{z - z_1}{p_1}$，$L_2: \dfrac{x - x_2}{m_2} = \dfrac{y - y_2}{n_2} = \dfrac{z - z_2}{p_2}$。

> [!important|blue] 定理：两直线的位置关系
>
> **方向向量：** $\boldsymbol{s}_1 = (m_1, n_1, p_1)$，$\boldsymbol{s}_2 = (m_2, n_2, p_2)$
>
> | 条件 | 关系 |
> |:---:|:---:|
> | $\boldsymbol{s}_1 \parallel \boldsymbol{s}_2$ 且 $\overrightarrow{M_1M_2} \parallel \boldsymbol{s}_1$ | 重合 |
> | $\boldsymbol{s}_1 \parallel \boldsymbol{s}_2$ 且 $\overrightarrow{M_1M_2} \not\parallel \boldsymbol{s}_1$ | 平行（不重合） |
> | $\boldsymbol{s}_1 \times \boldsymbol{s}_2 \cdot \overrightarrow{M_1M_2} = 0$（但不平行） | 相交 |
> | $\boldsymbol{s}_1 \times \boldsymbol{s}_2 \cdot \overrightarrow{M_1M_2} \neq 0$ | 异面 |
>
> **两直线的夹角：**
> $$\cos\theta = \frac{|\boldsymbol{s}_1 \cdot \boldsymbol{s}_2|}{|\boldsymbol{s}_1||\boldsymbol{s}_2|}$$

**异面直线的距离：** 两异面直线 $L_1, L_2$ 的距离为公垂线段的长度：
$$d = \frac{|(\boldsymbol{s}_1 \times \boldsymbol{s}_2) \cdot \overrightarrow{M_1M_2}|}{|\boldsymbol{s}_1 \times \boldsymbol{s}_2|}$$

---

## 七、平面与直线的位置关系

设平面 $\pi: Ax + By + Cz + D = 0$，直线 $L: \dfrac{x - x_0}{m} = \dfrac{y - y_0}{n} = \dfrac{z - z_0}{p}$。

> [!important|blue] 定理：平面与直线的位置关系
>
> **法向量** $\boldsymbol{n} = (A, B, C)$，**方向向量** $\boldsymbol{s} = (m, n, p)$。
>
> | 条件 | 关系 |
> |:---:|:---:|
> | $\boldsymbol{n} \cdot \boldsymbol{s} = 0$ 且点在平面上 | 直线在平面上 |
> | $\boldsymbol{n} \cdot \boldsymbol{s} = 0$ 且点不在平面上 | 平行（不相交） |
> | $\boldsymbol{n} \parallel \boldsymbol{s}$（即 $\dfrac{A}{m} = \dfrac{B}{n} = \dfrac{C}{p}$） | 垂直 |
> | 以上都不满足 | 斜交 |
>
> **直线与平面的夹角：** 设 $\varphi$ 为直线与平面的夹角（$0 \le \varphi \le \frac{\pi}{2}$），
> $$\sin\varphi = \frac{|\boldsymbol{n} \cdot \boldsymbol{s}|}{|\boldsymbol{n}||\boldsymbol{s}|} = \frac{|Am + Bn + Cp|}{\sqrt{A^2+B^2+C^2}\sqrt{m^2+n^2+p^2}}$$
>
> 注意：直线与平面的夹角用 $\sin$，不是 $\cos$！

---

## 八、典型例题

#### 例题 3

求过点 $(1, 2, 3)$ 且平行于平面 $x - 2y + z = 4$ 的平面方程。

**解：** 平行平面有相同法向量 $\boldsymbol{n} = (1, -2, 1)$。

点法式：$1(x-1) - 2(y-2) + 1(z-3) = 0$

化简：$x - 2y + z - 1 + 4 - 3 = 0$，即 $x - 2y + z = 0$。

#### 例题 4

求过两点 $A(1, 0, 0)$，$B(0, 1, 0)$ 且垂直于平面 $x + y + z = 1$ 的平面方程。

**解：** $\overrightarrow{AB} = (-1, 1, 0)$，已知平面法向量 $\boldsymbol{n}_1 = (1, 1, 1)$。

所求平面法向量 $\boldsymbol{n} = \overrightarrow{AB} \times \boldsymbol{n}_1 = \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ -1 & 1 & 0 \\ 1 & 1 & 1 \end{vmatrix} = (1, 1, -2)$。

过点 $A(1, 0, 0)$：$1(x-1) + 1(y-0) - 2(z-0) = 0$，即 $x + y - 2z = 1$。

#### 例题 5

将直线 $\begin{cases} x + y + z = 1 \\ 2x - y + 3z = 4 \end{cases}$ 化为对称式方程。

**解：**

方向向量 $\boldsymbol{s} = \boldsymbol{n}_1 \times \boldsymbol{n}_2 = (1,1,1) \times (2,-1,3)$

$= \begin{vmatrix} \boldsymbol{i} & \boldsymbol{j} & \boldsymbol{k} \\ 1 & 1 & 1 \\ 2 & -1 & 3 \end{vmatrix} = (3+1)\boldsymbol{i} - (3-2)\boldsymbol{j} + (-1-2)\boldsymbol{k} = (4, -1, -3)$

取直线上一点：令 $z = 0$，解 $\begin{cases} x + y = 1 \\ 2x - y = 4 \end{cases}$，得 $x = \dfrac{5}{3}$，$y = -\dfrac{2}{3}$。

对称式：$\dfrac{x - \frac{5}{3}}{4} = \dfrac{y + \frac{2}{3}}{-1} = \dfrac{z}{-3}$

#### 例题 6

求直线 $\dfrac{x-1}{2} = \dfrac{y}{-1} = \dfrac{z+1}{2}$ 与平面 $x - y + 2z = 3$ 的交点。

**解：** 参数化：$x = 1 + 2t$，$y = -t$，$z = -1 + 2t$。

代入平面：$(1+2t) - (-t) + 2(-1+2t) = 3$

$1 + 2t + t - 2 + 4t = 3$，$7t = 4$，$t = \dfrac{4}{7}$。

交点：$\left(\dfrac{15}{7}, -\dfrac{4}{7}, \dfrac{1}{7}\right)$。

#### 例题 7

求两平行平面 $2x - 2y + z + 5 = 0$ 与 $2x - 2y + z - 3 = 0$ 之间的距离。

**解：** 在第一个平面上取一点，令 $x = 0, y = 0$，得 $z = -5$，点 $(0, 0, -5)$。

到第二个平面的距离：
$$d = \frac{|2 \times 0 - 2 \times 0 + (-5) - 3|}{\sqrt{4+4+1}} = \frac{|-8|}{3} = \frac{8}{3}$$

---

## 九、求解技巧总结

> 1. **求平面**：找到法向量 + 一个点 → 点法式。法向量可由叉积、已知条件获得。
> 2. **求直线**：找到方向向量 + 一个点 → 对称式。方向向量可由叉积（两平面交线）或已知条件获得。
> 3. **距离问题**：点到平面用公式，点到直线用叉积，两平行平面间距离用公式，异面直线间距离用混合积。

---

## 十、易错点总结

> 1. **点到平面距离公式中分子要加绝对值**：$d = \dfrac{|Ax_0 + By_0 + Cz_0 + D|}{\sqrt{A^2+B^2+C^2}}$。
> 2. **直线与平面的夹角用 $\sin$**，不是 $\cos$。两平面夹角和两直线夹角用 $\cos$。
> 3. **一般式转对称式**：方向向量用叉积 $\boldsymbol{n}_1 \times \boldsymbol{n}_2$，再取直线上的一个点（通常令某个变量为 0 解方程组）。
> 4. **判定直线与平面关系时**：$\boldsymbol{n} \cdot \boldsymbol{s} = 0$ 只说明平行或直线在平面上，还需检验点是否在平面上来区分。
> 5. **截距式要求 $a, b, c$ 都非零**：如果平面过原点或平行于某坐标轴，不能用截距式。
> 6. **两平行平面间距离**：在第一个平面上取任意点，求到第二个平面的距离即可。注意两个方程的 $D$ 值不同但 $A, B, C$ 成比例时才平行。
> 7. **方向向量的选取**：直线的一般式方程中，方向向量是 $\boldsymbol{n}_1 \times \boldsymbol{n}_2$，不是 $\boldsymbol{n}_1$ 或 $\boldsymbol{n}_2$。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/10-向量代数与空间解析几何/Lecture 53：向量代数]] — 向量
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/11-曲线积分与曲面积分/Lecture 59：第一类曲面积分]] — 曲面积分
