---
title: Lecture 01 - 行列式
subject: 线性代数
chapter: 第一章
lecture: 01
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 01: 行列式

## 一、行列式的定义

### 1.1 二阶行列式

<span style="background-color: #ccc1d9">**定义（二阶行列式）**</span> 设 $a_{11}, a_{12}, a_{21}, a_{22}$ 为四个数，称

$$\begin{vmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{vmatrix} = a_{11}a_{22} - a_{12}a_{21}$$

为**二阶行列式**。

### 1.2 三阶行列式

<span style="background-color: #ccc1d9">**定义（三阶行列式）**</span> 设九个数排列成三行三列，称

$$\begin{vmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix}$$

为**三阶行列式**，其值为：

$$a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31} - a_{12}a_{21}a_{33} - a_{11}a_{23}a_{32}$$

### 1.3 n阶行列式

<span style="background-color: #ccc1d9">**定义（n阶行列式）**</span> n阶行列式定义为

$$|A| = \sum_{j=1}^{n} a_{1j} A_{1j}$$

其中 $A_{1j}$ 为元素 $a_{1j}$ 的**代数余子式**。

<span style="background-color: #ccc1d9">**定义（余子式与代数余子式）**</span>
- **余子式** $M_{ij}$：在n阶行列式中，去掉第 $i$ 行第 $j$ 列后剩下的 $(n-1)$ 阶行列式
- **代数余子式** $A_{ij} = (-1)^{i+j} M_{ij}$

---

## 二、行列式的性质

<span style="background-color: #8db3e2">**性质1**</span> 行列式与它的转置行列式相等，即 $|A| = |A^T|$。

<span style="background-color: #8db3e2">**性质2**</span> 互换行列式的两行（或两列），行列式变号。

<span style="background-color: #8db3e2">**性质3**</span> 行列式的某一行（列）的公因子可以提到行列式外面。

$$\begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \vdots & \vdots & & \vdots \\ ka_{i1} & ka_{i2} & \cdots & ka_{in} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix} = k \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \vdots & \vdots & & \vdots \\ a_{i1} & a_{i2} & \cdots & a_{in} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix}$$

<span style="background-color: #8db3e2">**性质4**</span> 若行列式的某一行（列）的所有元素都是零，则行列式等于零。

<span style="background-color: #8db3e2">**性质5**</span> 若行列式有两行（列）相同，则行列式等于零。

<span style="background-color: #8db3e2">**性质6**</span> 若行列式有两行（列）成比例，则行列式等于零。

<span style="background-color: #8db3e2">**性质7**</span> 若行列式的某一行（列）的各元素都是两数之和，则行列式可拆分为两个行列式之和。

<span style="background-color: #8db3e2">**性质8**</span> 把行列式的某一行（列）的各元素乘以同一数 $k$ 后加到另一行（列）对应元素上，行列式不变。

---

## 三、行列式的展开定理

<span style="background-color: #8db3e2">**定理（行列式按行展开）**</span> 行列式等于它的任意一行各元素与其对应的代数余子式的乘积之和：

$$|A| = a_{i1}A_{i1} + a_{i2}A_{i2} + \cdots + a_{in}A_{in}$$

<span style="background-color: #8db3e2">**定理（行列式按列展开）**</span> 行列式等于它的任意一列各元素与其对应的代数余子式的乘积之和：

$$|A| = a_{1j}A_{1j} + a_{2j}A_{2j} + \cdots + a_{nj}A_{nj}$$

<span style="background-color: #8db3e2">**定理（异行展开为零）**</span> 行列式某一行各元素与另一行对应元素的代数余子式的乘积之和为零：

$$a_{i1}A_{j1} + a_{i2}A_{j2} + \cdots + a_{in}A_{jn} = 0 \quad (i \neq j)$$

---

## 四、行列式的计算方法

### 4.1 化为对角形或三角形

利用行列式的性质，通过初等变换将行列式化为上三角形或下三角形，则行列式等于对角元素的乘积。

**上三角形行列式**：

$$\begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ 0 & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & a_{nn} \end{vmatrix} = a_{11}a_{22}\cdots a_{nn}$$

### 4.2 按行（列）展开

选择含有较多零元素的行（列）展开，可简化计算。

### 4.3 分块行列式

<span style="background-color: #8db3e2">**定理**</span> 设 $A$ 为 $m$ 阶方阵，$B$ 为 $n$ 阶方阵，$C$ 为 $m \times n$ 矩阵，则

$$\begin{vmatrix} A & C \\ 0 & B \end{vmatrix} = |A||B|$$

$$\begin{vmatrix} A & 0 \\ C & B \end{vmatrix} = |A||B|$$

### 4.4 特殊行列式

**对角行列式**：

$$\begin{vmatrix} a_{11} & 0 & \cdots & 0 \\ 0 & a_{22} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & a_{nn} \end{vmatrix} = a_{11}a_{22}\cdots a_{nn}$$

**副对角行列式**：

$$\begin{vmatrix} 0 & 0 & \cdots & a_{1n} \\ 0 & 0 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ a_{n1} & 0 & \cdots & 0 \end{vmatrix} = (-1)^{\frac{n(n-1)}{2}} a_{1n}a_{2,n-1}\cdots a_{n1}$$

---

## 五、克拉默法则

<span style="background-color: #8db3e2">**定理（克拉默法则）**</span> 若线性方程组

$$\begin{cases} a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\ a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\ \vdots \\ a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = b_n \end{cases}$$

的系数行列式 $D = |A| \neq 0$，则方程组有唯一解：

$$x_j = \frac{D_j}{D} \quad (j = 1, 2, \cdots, n)$$

其中 $D_j$ 是将 $D$ 的第 $j$ 列换成常数项 $b_1, b_2, \cdots, b_n$ 所得的行列式。

---

## 六、典型例题

### 例题1：特殊行列式的计算

**题目**：计算 $\begin{vmatrix} 0 & 2 & 2 & 2 \\ 2 & 0 & 2 & 2 \\ 2 & 2 & 0 & 2 \\ 2 & 2 & 2 & 0 \end{vmatrix}$。

**思路**：各行元素之和相同，可利用行列式性质。

**解答**：
各行元素之和为 $6$，将第2、3、4列加到第1列：

$$\begin{vmatrix} 6 & 2 & 2 & 2 \\ 6 & 0 & 2 & 2 \\ 6 & 2 & 0 & 2 \\ 6 & 2 & 2 & 0 \end{vmatrix} = 6 \begin{vmatrix} 1 & 2 & 2 & 2 \\ 1 & 0 & 2 & 2 \\ 1 & 2 & 0 & 2 \\ 1 & 2 & 2 & 0 \end{vmatrix}$$

各行减第1行：

$$= 6 \begin{vmatrix} 1 & 2 & 2 & 2 \\ 0 & -2 & 0 & 0 \\ 0 & 0 & -2 & 0 \\ 0 & 0 & 0 & -2 \end{vmatrix} = 6 \times 1 \times (-2) \times (-2) \times (-2) = -48$$

**总结**：各行元素之和相同的行列式，可先求和再化简。

---

### 例题2：行列式展开的应用

**题目**：多项式 $f(x) = \begin{vmatrix} 1 & 2 & 3 & 4 \\ 2 & x & 4 & 1 \\ 3 & 4 & x & 2 \\ 4 & 1 & 2 & 3 \end{vmatrix}$ 中，$x^2$ 项的系数为多少？

**思路**：按含 $x$ 的行或列展开，找出 $x^2$ 的来源。

**解答**：
含 $x$ 的元素在第2行第2列和第3行第3列。

按第2行展开：$f(x) = 2A_{21} + xA_{22} + 4A_{23} + 1A_{24}$

$x^2$ 只可能来自 $xA_{22}$，其中 $A_{22} = (-1)^{2+2} \begin{vmatrix} 1 & 3 & 4 \\ 3 & x & 2 \\ 4 & 2 & 3 \end{vmatrix}$

再按第2行展开：$A_{22} = 3M_{21} + xM_{22} + 2M_{23}$

$x^2$ 来自 $xM_{22}$，其中 $M_{22} = \begin{vmatrix} 1 & 4 \\ 4 & 3 \end{vmatrix} = 3 - 16 = -13$

所以 $x^2$ 的系数为 $(-1)^{2+2} \times (-13) = -13$

**总结**：行列式展开时，注意代数余子式的符号。

---

### 例题3：行列式与矩阵运算

**题目**：设 $A$ 为三阶矩阵，互换矩阵 $A$ 的1、2行，再将第1行的2倍加到第2行得矩阵 $B$。若 $|A| = 3$，求 $|A + B|$。

**思路**：利用初等变换与行列式的关系。

**解答**：
设 $A$ 的第1、2行互换后为 $A_1$，则 $|A_1| = -|A| = -3$

将 $A_1$ 的第1行的2倍加到第2行得 $B$，行列式不变，所以 $|B| = |A_1| = -3$

$A + B$ 的计算需要具体分析。设 $A = \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix}$（按行表示）

则 $A_1 = \begin{bmatrix} a_2 \\ a_1 \\ a_3 \end{bmatrix}$，$B = \begin{bmatrix} a_2 \\ a_1 + 2a_2 \\ a_3 \end{bmatrix}$

$A + B = \begin{bmatrix} a_1 + a_2 \\ a_2 + a_1 + 2a_2 \\ a_3 + a_3 \end{bmatrix} = \begin{bmatrix} a_1 + a_2 \\ a_1 + 3a_2 \\ 2a_3 \end{bmatrix}$

$|A + B| = 2 \begin{vmatrix} a_1 + a_2 \\ a_1 + 3a_2 \\ a_3 \end{vmatrix} = 2 \begin{vmatrix} a_1 + a_2 \\ 2a_2 \\ a_3 \end{vmatrix}$（第2行减第1行）

$= 2 \times 2 \begin{vmatrix} a_1 + a_2 \\ a_2 \\ a_3 \end{vmatrix} = 4 \begin{vmatrix} a_1 \\ a_2 \\ a_3 \end{vmatrix} = 4|A| = 12$

**总结**：行列式的初等变换性质：互换变号，倍乘提因子，倍加不变。

---

### 例题4：行列式与向量运算

**题目**：设3阶矩阵 $A = [\alpha_1, \alpha_2, \alpha_3]$，其中 $\alpha_1, \alpha_2, \alpha_3$ 为3维列向量。若 $|A| = \frac{1}{2}$，求 $|\alpha_1 + \alpha_2, \alpha_2 + \alpha_3, \alpha_3 + \alpha_1|$。

**思路**：利用行列式的线性性质。

**解答**：
设 $B = [\alpha_1 + \alpha_2, \alpha_2 + \alpha_3, \alpha_3 + \alpha_1]$

$B = [\alpha_1, \alpha_2, \alpha_3] \begin{bmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{bmatrix} = AC$

所以 $|B| = |A||C|$

$|C| = \begin{vmatrix} 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{vmatrix} = 1 + 1 + 0 - 0 - 1 - 0 = 2$

因此 $|B| = \frac{1}{2} \times 2 = 1$

**总结**：行列式与矩阵乘法的关系：$|AB| = |A||B|$。

---

## 七、解题方法总结

### 7.1 行列式计算的主要方法

| 类型 | 方法 |
|------|------|
| 数字行列式 | 化为三角形、按行展开 |
| 含参数行列式 | 按含参数的行展开 |
| 特殊结构行列式 | 利用性质、分块行列式 |
| 向量行列式 | 矩阵乘法关系 |

### 7.2 常见易错点

1. **展开时忘记符号**：代数余子式 $A_{ij} = (-1)^{i+j}M_{ij}$
2. **初等变换对行列式的影响**：互换变号，倍乘提因子，倍加不变
3. **行列式乘法**：$|AB| = |A||B|$，但 $|A + B| \neq |A| + |B|$
4. **克拉默法则条件**：必须 $|A| \neq 0$

---

## 八、练习题精选

### 基础练习

1. 计算 $\begin{vmatrix} 1 & 2 & 3 & 4 \\ 1 & 2^2 & 3^2 & 4^2 \\ 1 & 2^3 & 3^3 & 4^3 \\ 9 & 8 & 7 & 6 \end{vmatrix}$。

2. 设n阶行列式 $D = \begin{vmatrix} n & n-1 & \cdots & 1 \\ 0 & 0 & \cdots & 2 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & n-1 & \cdots & n \end{vmatrix}$（特殊结构），求其值。

3. 设 $A$ 为三阶矩阵，$|A| = 2$，求 $|2A|$。

### 提高练习

4. 设n阶矩阵 $A = [\alpha_1, \alpha_2, \cdots, \alpha_n]$，$B = [\alpha_n, \alpha_1, \cdots, \alpha_{n-1}]$，若 $|A| = 1$，求 $|A - B|$。

5. 设 $A$ 为n阶方阵，$A^2 - A = E$，证明 $A$ 可逆并求 $A^{-1}$。

---

## 参考答案提示

1. 利用范德蒙行列式公式或行列式性质

2. 利用行列式性质，化为三角形

3. $|2A| = 2^3|A| = 8 \times 2 = 16$

4. $|A - B| = 0$（提示：$A - B$ 的列向量线性相关）

5. $A^{-1} = A - E$（提示：由 $A^2 - A = E$ 得 $A(A - E) = E$）

---

> **注**：本 Lecture 内容涵盖行列式的定义、性质、计算方法及典型例题。建议结合《基础过关660题》第361-367题进行练习巩固。