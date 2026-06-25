---
title: Lecture 04 - 线性方程组
subject: 线性代数
chapter: 第四章
lecture: 04
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 04: 线性方程组

## 一、线性方程组的表示形式

### 1.1 一般形式

<span style="background-color: #ccc1d9">**定义（线性方程组）**</span> 含有 $m$ 个方程、$n$ 个未知量的线性方程组可表示为

$$\begin{cases} a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\ a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\ \vdots \\ a_{m1}x_1 + a_{m2}x_2 + \cdots + a_{mn}x_n = b_m \end{cases}$$

### 1.2 矩阵形式

记 $\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$，$\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}$，$\mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_m \end{bmatrix}$，则方程组可写为

$$\mathbf{A}\mathbf{x} = \mathbf{b}$$

### 1.3 增广矩阵

<span style="background-color: #ccc1d9">**定义（增广矩阵）**</span> 将系数矩阵 $\mathbf{A}$ 与常数向量 $\mathbf{b}$ 合并，记作

$$\bar{\mathbf{A}} = [\mathbf{A}, \mathbf{b}] = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\ a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\ \vdots & \vdots & & \vdots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} & b_m \end{bmatrix}$$

---

## 二、克拉默法则

<span style="background-color: #8db3e2">**定理（克拉默法则）**</span> 若线性方程组 $\mathbf{A}\mathbf{x} = \mathbf{b}$ 的系数行列式 $D = |\mathbf{A}| \neq 0$，则方程组有唯一解：

$$x_j = \frac{D_j}{D} \quad (j = 1, 2, \cdots, n)$$

其中 $D_j$ 是将 $D$ 的第 $j$ 列换成常数项 $b_1, b_2, \cdots, b_n$ 所得的行列式。

<span style="background-color: #8db3e2">**注意**</span> 克拉默法则只适用于方程个数等于未知量个数且系数行列式不为零的情况。

---

## 三、齐次线性方程组

### 3.1 齐次方程组的表示

<span style="background-color: #ccc1d9">**定义（齐次线性方程组）**</span> 常数项全为零的线性方程组称为**齐次线性方程组**：

$$\mathbf{A}\mathbf{x} = \mathbf{0}$$

### 3.2 解的结构

<span style="background-color: #8db3e2">**定理**</span> 齐次线性方程组的解集构成一个向量空间（解空间）。

<span style="background-color: #8db3e2">**性质**</span>
- 若 $\mathbf{x}_1, \mathbf{x}_2$ 是齐次方程组的解，则 $k_1\mathbf{x}_1 + k_2\mathbf{x}_2$ 也是其解
- 齐次方程组总有零解 $\mathbf{x} = \mathbf{0}$

### 3.3 有非零解的条件

<span style="background-color: #8db3e2">**定理**</span> 齐次线性方程组 $\mathbf{A}_{m \times n}\mathbf{x} = \mathbf{0}$ 有非零解的充要条件是 $r(\mathbf{A}) < n$（即系数矩阵的秩小于未知量的个数）。

<span style="background-color: #8db3e2">**推论**</span>
- 当 $m < n$（方程个数小于未知量个数）时，方程组必有非零解
- 当 $\mathbf{A}$ 为 $n$ 阶方阵时，有非零解 $\Leftrightarrow$ $|\mathbf{A}| = 0$

---

## 四、非齐次线性方程组

### 4.1 有解的条件

<span style="background-color: #8db3e2">**定理**</span> 非齐次线性方程组 $\mathbf{A}\mathbf{x} = \mathbf{b}$ 有解的充要条件是 $r(\mathbf{A}) = r(\bar{\mathbf{A}})$。

<span style="background-color: #8db3e2">**进一步**</span>
- 若 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) = n$，则方程组有唯一解
- 若 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) < n$，则方程组有无穷多解

### 4.2 解的结构

<span style="background-color: #8db3e2">**定理**</span> 非齐次线性方程组的通解等于其一个特解加上对应的齐次方程组的通解：

$$\mathbf{x} = \mathbf{x}^* + \mathbf{x}_h$$

其中 $\mathbf{x}^*$ 是非齐次方程组的一个特解，$\mathbf{x}_h$ 是齐次方程组 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的通解。

---

## 五、线性方程组解的性质

<span style="background-color: #8db3e2">**性质1**</span> 若 $\mathbf{x}_1, \mathbf{x}_2$ 是 $\mathbf{A}\mathbf{x} = \mathbf{b}$ 的解，则 $\mathbf{x}_1 - \mathbf{x}_2$ 是 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解。

<span style="background-color: #8db3e2">**性质2**</span> 若 $\mathbf{x}_1, \mathbf{x}_2$ 是 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解，则 $k_1\mathbf{x}_1 + k_2\mathbf{x}_2$ 也是 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解。

<span style="background-color: #8db3e2">**性质3**</span> 若 $\mathbf{x}_1$ 是 $\mathbf{A}\mathbf{x} = \mathbf{b}$ 的解，$\mathbf{x}_2$ 是 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解，则 $\mathbf{x}_1 + \mathbf{x}_2$ 是 $\mathbf{A}\mathbf{x} = \mathbf{b}$ 的解。

---

## 六、基础解系与通解

### 6.1 基础解系的定义

<span style="background-color: #ccc1d9">**定义（基础解系）**</span> 若齐次线性方程组 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解空间的一组基 $\boldsymbol{\eta}_1, \boldsymbol{\eta}_2, \cdots, \boldsymbol{\eta}_{n-r}$（其中 $r = r(\mathbf{A})$）满足：
1. $\boldsymbol{\eta}_1, \boldsymbol{\eta}_2, \cdots, \boldsymbol{\eta}_{n-r}$ 线性无关
2. 方程组的任一解都可以由 $\boldsymbol{\eta}_1, \boldsymbol{\eta}_2, \cdots, \boldsymbol{\eta}_{n-r}$ 线性表示

则称 $\boldsymbol{\eta}_1, \boldsymbol{\eta}_2, \cdots, \boldsymbol{\eta}_{n-r}$ 为该方程组的**基础解系**。

### 6.2 基础解系的求法

<span style="background-color: #8db3e2">**步骤**</span>
1. 求系数矩阵 $\mathbf{A}$ 的秩 $r$
2. 将 $\mathbf{A}$ 化为行阶梯形矩阵，确定自由未知量
3. 对自由未知量分别取单位向量，得到基础解系

### 6.3 通解的表示

<span style="background-color: #8db3e2">**通解形式**</span> 齐次方程组的通解为

$$\mathbf{x} = k_1\boldsymbol{\eta}_1 + k_2\boldsymbol{\eta}_2 + \cdots + k_{n-r}\boldsymbol{\eta}_{n-r}$$

非齐次方程组的通解为

$$\mathbf{x} = \mathbf{x}^* + k_1\boldsymbol{\eta}_1 + k_2\boldsymbol{\eta}_2 + \cdots + k_{n-r}\boldsymbol{\eta}_{n-r}$$

---

## 七、典型例题

### 例题1：基础解系与通解

**题目**（660题-398）设 $\mathbf{A}$ 是 $5 \times 4$ 矩阵，若 $\boldsymbol{\eta}_{1}, \boldsymbol{\eta}_{2}$ 是齐次方程组 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的基础解系，则 $r(\mathbf{A}^{\mathrm{T}}) =$ ____。

**思路**：利用齐次方程组基础解系与系数矩阵秩的关系。

**解答**：
$\mathbf{A}$ 是 $5 \times 4$ 矩阵，未知量个数 $n = 4$。

基础解系含有 $s = 2$ 个解向量，由 $n - r(\mathbf{A}) = s$ 得

$4 - r(\mathbf{A}) = 2$，所以 $r(\mathbf{A}) = 2$。

$\mathbf{A}^T$ 是 $4 \times 5$ 矩阵，$r(\mathbf{A}^T) = r(\mathbf{A}) = 2$。

**总结**：齐次方程组基础解系所含向量个数 $= n - r(\mathbf{A})$，矩阵转置不改变秩。

---

### 例题2：非齐次方程组的通解

**题目**（660题-399）已知 $\mathbf{A} = \begin{bmatrix} 1 & -2 & 0 \\ 2 & 1 & 5 \\ 0 & 1 & 1 \end{bmatrix}$，$\mathbf{A}^*$ 是 $\mathbf{A}$ 的伴随矩阵，则 $\mathbf{A}^*\mathbf{x} = 0$ 的通解是____。

**思路**：先求 $\mathbf{A}$ 的特征值和特征向量，再求 $\mathbf{A}^*$ 的零空间。

**解答**：
$|\mathbf{A}| = \begin{vmatrix} 1 & -2 & 0 \\ 2 & 1 & 5 \\ 0 & 1 & 1 \end{vmatrix} = \begin{vmatrix} 1 & -2 & 0 \\ 0 & 5 & 5 \\ 0 & 1 & 1 \end{vmatrix} = 5 - 5 = 0$

由 $|\mathbf{A}| = 0$ 知 $r(\mathbf{A}) < 3$，且 $\mathbf{A}^*\mathbf{x} = \mathbf{0}$ 的解即为 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的解。

求 $\mathbf{A}$ 的秩：$\mathbf{A} \rightarrow \begin{bmatrix} 1 & -2 & 0 \\ 0 & 5 & 5 \\ 0 & 1 & 1 \end{bmatrix} \rightarrow \begin{bmatrix} 1 & -2 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 0 \end{bmatrix}$

所以 $r(\mathbf{A}) = 2$，基础解系含 $3 - 2 = 1$ 个向量。

由 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 得 $\begin{cases} x_1 - 2x_2 = 0 \\ x_2 + x_3 = 0 \end{cases}$，解得 $x_1 = 2x_2, x_3 = -x_2$

令 $x_2 = 1$，得基础解系 $\boldsymbol{\eta} = (2, 1, -1)^T$

通解为 $\mathbf{x} = k(2, 1, -1)^T, k \in \mathbb{R}$

**总结**：当 $|\mathbf{A}| = 0$ 时，$\mathbf{A}^*\mathbf{x} = \mathbf{0}$ 与 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 同解。

---

### 例题3：非齐次方程组解的结构

**题目**（660题-400）设线性方程组 $\mathbf{A}_{3 \times 3} \mathbf{x} = \mathbf{b}$ 有唯一解 $\boldsymbol{\xi} = (1,2,3)^T$。方程组 $\mathbf{B}_{3 \times 4} \mathbf{y} = \mathbf{b}$ 有特解 $\boldsymbol{\eta} = (-2,1,4,2)^T$，则方程组(2)的通解是____。

**思路**：利用非齐次方程组解的结构。

**解答**：
由 $\mathbf{A}_{3 \times 3} \mathbf{x} = \mathbf{b}$ 有唯一解知 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) = 3$。

设 $\mathbf{B} = [\mathbf{A}, \mathbf{b}]$（前3列为 $\mathbf{A}$，第4列为 $\mathbf{b}$），则 $\mathbf{B}_{3 \times 4} \mathbf{y} = \mathbf{b}$ 可写为

$$\begin{bmatrix} \mathbf{A} & \mathbf{b} \end{bmatrix} \begin{bmatrix} y_1 \\ y_2 \\ y_3 \\ y_4 \end{bmatrix} = \mathbf{b}$$

即 $y_1\mathbf{A}_1 + y_2\mathbf{A}_2 + y_3\mathbf{A}_3 + y_4\mathbf{b} = \mathbf{b}$

由唯一解 $\boldsymbol{\xi} = (1,2,3)^T$ 知 $\mathbf{A}\boldsymbol{\xi} = \mathbf{b}$，即 $\mathbf{A}_1 + 2\mathbf{A}_2 + 3\mathbf{A}_3 = \mathbf{b}$

所以取 $y_1 = 1, y_2 = 2, y_3 = 3, y_4 = 0$ 可得一个解 $(1,2,3,0)^T$。

$\mathbf{B}$ 的秩仍为3，基础解系含 $4-3=1$ 个向量。

由 $\mathbf{B}\mathbf{y} = \mathbf{0}$ 得 $y_1\mathbf{A}_1 + y_2\mathbf{A}_2 + y_3\mathbf{A}_3 + y_4\mathbf{b} = \mathbf{0}$

即 $y_1\mathbf{A}_1 + y_2\mathbf{A}_2 + y_3\mathbf{A}_3 = -y_4\mathbf{b}$

由 $\mathbf{A}\boldsymbol{\xi} = \mathbf{b}$ 得 $\mathbf{A}(k\boldsymbol{\xi}) = k\mathbf{b}$

所以 $y_1\mathbf{A}_1 + y_2\mathbf{A}_2 + y_3\mathbf{A}_3 = -(y_4)\mathbf{b}$ 的解满足 $(y_1, y_2, y_3) = -y_4(1,2,3)$

令 $y_4 = 1$，得 $(y_1, y_2, y_3, y_4) = (-1,-2,-3,1)$

通解为 $\mathbf{y} = (-2,1,4,2)^T + k(-1,-2,-3,1)^T, k \in \mathbb{R}$

**总结**：非齐次方程组的通解 = 特解 + 齐次方程组的通解。

---

### 例题4：含参数的线性方程组

**题目**（660题-393）已知 $\boldsymbol{\alpha}_{1}=(1,2,1)^{\mathrm{T}},\boldsymbol{\alpha}_{2}=(2,3,a)^{\mathrm{T}},\boldsymbol{\alpha}_{3}=(1,a+2,-2)^{\mathrm{T}},\boldsymbol{\beta}=(1,3,0)^{\mathrm{T}}$。若 $\boldsymbol{\beta}$ 可由 $\boldsymbol{\alpha}_{1},\boldsymbol{\alpha}_{2},\boldsymbol{\alpha}_{3}$ 线性表示，且表示法不唯一，则 $a=$____。

**思路**：表示法不唯一意味着 $\boldsymbol{\alpha}_{1},\boldsymbol{\alpha}_{2},\boldsymbol{\alpha}_{3}$ 线性相关。

**解答**：
$\boldsymbol{\beta}$ 可由 $\boldsymbol{\alpha}_{1},\boldsymbol{\alpha}_{2},\boldsymbol{\alpha}_{3}$ 线性表示，相当于方程组

$x_1\boldsymbol{\alpha}_1 + x_2\boldsymbol{\alpha}_2 + x_3\boldsymbol{\alpha}_3 = \boldsymbol{\beta}$

有解。表示法不唯一意味着解不唯一，即系数矩阵的秩 $< 3$。

构造增广矩阵并化简：

$[\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3, \boldsymbol{\beta}] = \begin{bmatrix} 1 & 2 & 1 & 1 \\ 2 & 3 & a+2 & 3 \\ 1 & a & -2 & 0 \end{bmatrix}$

$\rightarrow \begin{bmatrix} 1 & 2 & 1 & 1 \\ 0 & -1 & a & 1 \\ 0 & a-2 & -3 & -1 \end{bmatrix}$

$\rightarrow \begin{bmatrix} 1 & 2 & 1 & 1 \\ 0 & -1 & a & 1 \\ 0 & 0 & a^2-2a-3 & a-3 \end{bmatrix}$

由 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) < 3$ 得 $a^2 - 2a - 3 = 0$ 且 $a - 3 = 0$（不对，应分开讨论）

实际上，$r(\mathbf{A}) = 3 \Leftrightarrow a^2 - 2a - 3 \neq 0$

$r(\bar{\mathbf{A}}) = 3 \Leftrightarrow a - 3 \neq 0$ 或 $a^2 - 2a - 3 \neq 0$

由表示法不唯一知 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) = 2$

即 $a^2 - 2a - 3 = 0$ 且 $a - 3 = 0$ 无法同时成立？需重新分析。

由 $r(\mathbf{A}) = 2$ 得 $a^2 - 2a - 3 = 0$，即 $a = 3$ 或 $a = -1$。

当 $a = 3$ 时，$a - 3 = 0$，此时 $r(\bar{\mathbf{A}}) = 2 = r(\mathbf{A})$，方程组有解。

验证：当 $a = 3$ 时，$[\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3] = \begin{bmatrix} 1 & 2 & 1 \\ 2 & 3 & 5 \\ 1 & 5 & -2 \end{bmatrix}$，这三个向量线性相关（行列式为0），且 $\boldsymbol{\beta}$ 可由它们表示（因为 $r(\mathbf{A}) = r(\bar{\mathbf{A}}) = 2$）。

当 $a = -1$ 时，$[\boldsymbol{\alpha}_1, \boldsymbol{\alpha}_2, \boldsymbol{\alpha}_3] = \begin{bmatrix} 1 & 2 & 1 \\ 2 & 3 & 1 \\ 1 & -1 & -2 \end{bmatrix}$，$r(\mathbf{A}) = 3$（行列式 $\neq 0$），有唯一表示法。

所以 $a = 3$。

**总结**：表示法不唯一的充要条件是系数矩阵的秩小于未知量个数（秩 $< 3$）。

---

## 八、解题方法总结

### 8.1 方程组求解步骤

| 步骤 | 内容 |
|------|------|
| 1. 判断类型 | 齐次还是非齐次 |
| 2. 求系数矩阵的秩 | 初等行变换化阶梯形 |
| 3. 求增广矩阵的秩 | 判断有解性 |
| 4. 求基础解系 | 令自由变量为单位向量 |
| 5. 写出通解 | 特解 + 齐次通解 |

### 8.2 常见易错点

1. **忽略有解条件**：$r(\mathbf{A}) \neq r(\bar{\mathbf{A}})$ 时无解
2. **基础解系个数错误**：$n - r(\mathbf{A})$ 是齐次方程组的基础解系个数
3. **特解选取错误**：非齐次方程组的特解要代入原方程验证
4. **参数讨论遗漏**：参数可能影响秩，需分情况讨论

---

## 九、练习题精选

### 基础练习

1. 求下列齐次方程组的通解：
   $$\begin{cases} x_1 + x_2 - x_3 = 0 \\ 2x_1 + 3x_2 + x_3 = 0 \end{cases}$$

2. 判断下列非齐次方程组是否有解：
   $$\begin{cases} x_1 + 2x_2 = 1 \\ 2x_1 + 4x_2 = 3 \end{cases}$$

3. 设 $\mathbf{A} = \begin{bmatrix} 1 & 2 & -1 \\ 2 & 4 & -2 \end{bmatrix}$，求 $\mathbf{A}\mathbf{x} = \mathbf{0}$ 的基础解系。

### 提高练习

4. 证明：若 $\mathbf{A}\mathbf{B} = \mathbf{0}$，则 $r(\mathbf{A}) + r(\mathbf{B}) \leq n$。

5. 设 $\mathbf{A}$ 为 $n$ 阶矩阵，$\mathbf{A}^2 = \mathbf{A}$，证明 $\mathbf{A}$ 可以对角化。

---

## 参考答案提示

1. $n - r(\mathbf{A}) = 3 - 2 = 1$，基础解系含1个向量。

   阶梯形：$\begin{bmatrix} 1 & 1 & -1 \\ 0 & 1 & 3 \end{bmatrix}$，令 $x_3 = 1$ 得 $x_2 = -3$，$x_1 = 4$。

   通解：$\mathbf{x} = k(4,-3,1)^T, k \in \mathbb{R}$

2. $r(\mathbf{A}) = 1, r(\bar{\mathbf{A}}) = 2$，无解

3. $\mathbf{A} \rightarrow \begin{bmatrix} 1 & 2 & -1 \\ 0 & 0 & 0 \end{bmatrix}$，基础解系：$\boldsymbol{\eta}_1 = (-2,1,0)^T, \boldsymbol{\eta}_2 = (1,0,1)^T$

4. 提示：将 $\mathbf{B}$ 按列分块，利用齐次方程组的解空间维度

5. 提示：由 $\mathbf{A}^2 = \mathbf{A}$ 得 $\mathbf{A}$ 的特征值只能为 0 或 1，且 $r(\mathbf{A}) + r(\mathbf{E} - \mathbf{A}) = n$

---

> **注**：本 Lecture 内容涵盖线性方程组的求解方法和理论。建议结合《基础过关660题》第384-396题进行练习巩固。
