---
title: Lecture 1：行列式的定义与性质
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 1：行列式的定义与性质

## 一、行列式的定义（逆序数法）

### 1.1 排列与逆序数

> [!definition|purple] 逆序数
> 设 $p_1 p_2 \cdots p_n$ 是 $1, 2, \cdots, n$ 的一个排列，若 $i < j$ 而 $p_i > p_j$，则称 $(p_i, p_j)$ 构成一个**逆序**。
> 一个排列中所有逆序的总和称为该排列的**逆序数**，记为 $\tau(p_1 p_2 \cdots p_n)$。

**计算方法：**

对排列中的每个元素 $p_i$，计算其后面比它小的元素个数 $t_i$，则
$$
\tau(p_1 p_2 \cdots p_n) = t_1 + t_2 + \cdots + t_n
$$

**示例：**

计算排列 $\tau(3\,1\,5\,2\,4)$：
- 3 后面比 3 小的：1, 2 → $t_1 = 2$
- 1 后面比 1 小的：无 → $t_2 = 0$
- 5 后面比 5 小的：2, 4 → $t_3 = 2$
- 2 后面比 2 小的：无 → $t_4 = 0$
- 4 后面比 4 小的：无 → $t_5 = 0$

所以 $\tau(3\,1\,5\,2\,4) = 2 + 0 + 2 + 0 + 0 = 4$。

> [!tip|blue] 奇排列与偶排列
> - 逆序数为**奇数**的排列称为**奇排列**
> - 逆序数为**偶数**的排列称为**偶排列**
> - $n$ 阶排列总数为 $n!$，其中奇排列和偶排列各占一半，即 $\frac{n!}{2}$ 个

### 1.2 行列式的逆序数定义

> [!definition|purple] n阶行列式的定义
> $$
> D = \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix} = \sum_{j_1 j_2 \cdots j_n} (-1)^{\tau(j_1 j_2 \cdots j_n)} a_{1 j_1} a_{2 j_2} \cdots a_{n j_n}
> $$
> 其中求和对所有 $n$ 阶排列 $j_1 j_2 \cdots j_n$ 进行，共 $n!$ 项。

**理解要点：**
1. 行列式是 $n!$ 项的代数和
2. 每一项是不同行不同列的 $n$ 个元素的乘积
3. 每一项的符号由列指标排列的逆序数决定
4. 行列式的值是一个**数**

### 1.3 低阶行列式的直接计算

**2阶行列式：**
$$
\begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc
$$

**3阶行列式（对角线法则，仅适用于3阶）：**
$$
\begin{vmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{vmatrix} = a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32} - a_{13}a_{22}a_{31} - a_{12}a_{21}a_{33} - a_{11}a_{23}a_{32}
$$

> [!warning|red] 易错点
> 对角线法则**仅适用于2阶和3阶**行列式！4阶及以上行列式不能用对角线法则。

---

## 二、行列式的7条性质

> [!definition|purple] 性质1：转置不变性
> $$
> D^T = D
> $$
> 即行列式转置后值不变。行与列的地位相同。

> [!definition|purple] 性质2：换行（列）变号
> 交换行列式的任意两行（列），行列式的值**变号**。

**推论：** 如果行列式有两行（列）完全相同，则行列式的值为 $0$。

> [!definition|purple] 性质3：提公因子
> 行列式的某一行（列）的公因子可以提到行列式外面：
> $$
> \begin{vmatrix} \vdots & \vdots & & \vdots \\ ka_{i1} & ka_{i2} & \cdots & ka_{in} \\ \vdots & \vdots & & \vdots \end{vmatrix} = k \begin{vmatrix} \vdots & \vdots & & \vdots \\ a_{i1} & a_{i2} & \cdots & a_{in} \\ \vdots & \vdots & & \vdots \end{vmatrix}
> $$

**推论：** 如果行列式某一行（列）的元素全为 $0$，则行列式的值为 $0$。

> [!definition|purple] 性质4：拆行（列）
> 如果行列式某一行（列）的元素都是两个数之和，则可以拆成两个行列式之和：
> $$
> \begin{vmatrix} a_{i1}+b_{i1} & a_{i2}+b_{i2} & \cdots & a_{in}+b_{in} \end{vmatrix} = \begin{vmatrix} a_{i1} & a_{i2} & \cdots & a_{in} \end{vmatrix} + \begin{vmatrix} b_{i1} & b_{i2} & \cdots & b_{in} \end{vmatrix}
> $$
> （其余行不变）

> [!definition|purple] 性质5：倍加不变性
> 把行列式的某一行（列）的 $k$ 倍加到另一行（列）上，行列式的值**不变**。

这是**行列式计算中最重要的性质**，是上三角化法的基础。

> [!definition|purple] 性质6：比例行列式
> 如果行列式有两行（列）对应成比例，则行列式的值为 $0$。

> [!definition|purple] 性质7：展开性质
> 行列式等于它的某一行（列）的各元素与其代数余子式乘积之和（详见下节展开定理）。

### 性质应用示例

**例1：** 利用性质计算
$$
D = \begin{vmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 1 & 1 & 1 \end{vmatrix}
$$

观察第2行是第1行的2倍（两行成比例），由性质6得 $D = 0$。

**例2：** 计算
$$
D = \begin{vmatrix} 1+a & 1 & 1 \\ 1 & 1+b & 1 \\ 1 & 1 & 1+c \end{vmatrix} \quad (abc \neq 0)
$$

利用性质4拆分第1列：
$$
D = \begin{vmatrix} 1 & 1 & 1 \\ 1 & 1+b & 1 \\ 1 & 1 & 1+c \end{vmatrix} + \begin{vmatrix} a & 1 & 1 \\ 0 & 1+b & 1 \\ 0 & 1 & 1+c \end{vmatrix}
$$

第一个行列式：第1列倍加到第2、3列：
$$
= \begin{vmatrix} 1 & 0 & 0 \\ 1 & b & 0 \\ 1 & 0 & c \end{vmatrix} = bc
$$

第二个行列式按第1列展开：$= a[(1+b)(1+c) - 1] = a(b+c+bc)$

所以 $D = bc + ab + ac + abc = abc + ab + ac + bc$。

---

## 三、行列式按行（列）展开定理

### 3.1 余子式与代数余子式

> [!definition|purple] 余子式
> 在 $n$ 阶行列式中，划去元素 $a_{ij}$ 所在的第 $i$ 行和第 $j$ 列后，剩余元素按原来位置排列构成的 $n-1$ 阶行列式，称为 $a_{ij}$ 的**余子式**，记为 $M_{ij}$。

> [!definition|purple] 代数余子式
> $$
> A_{ij} = (-1)^{i+j} M_{ij}
> $$
> 称为元素 $a_{ij}$ 的**代数余子式**。

**符号规律（棋盘格）：**
$$
\begin{pmatrix} + & - & + & - & \cdots \\ - & + & - & + & \cdots \\ + & - & + & - & \cdots \\ \vdots & \vdots & \vdots & \vdots & \ddots \end{pmatrix}
$$

### 3.2 展开定理

> [!theorem|blue] 行列式按行展开定理
> $n$ 阶行列式 $D$ 等于其任意一行的各元素与对应代数余子式乘积之和：
> $$
> D = a_{i1}A_{i1} + a_{i2}A_{i2} + \cdots + a_{in}A_{in} = \sum_{j=1}^{n} a_{ij} A_{ij} \quad (i = 1, 2, \cdots, n)
> $$

> [!theorem|blue] 行列式按列展开定理
> $$
> D = a_{1j}A_{1j} + a_{2j}A_{2j} + \cdots + a_{nj}A_{nj} = \sum_{i=1}^{n} a_{ij} A_{ij} \quad (j = 1, 2, \cdots, n)
> $$

### 3.3 错行展开（降阶技巧）

> [!theorem|blue] 异行异列消零定理
> 行列式某一行（列）的元素与另一行（列）对应元素的代数余子式乘积之和等于零：
> $$
> \sum_{j=1}^{n} a_{ij} A_{kj} = 0 \quad (i \neq k)
> $$
> $$
> \sum_{i=1}^{n} a_{ij} A_{ik} = 0 \quad (j \neq k)
> $$

**综合两个定理，可用 Kronecker delta 符号统一表示为：**
$$
\sum_{j=1}^{n} a_{ij} A_{kj} = D \cdot \delta_{ik} = \begin{cases} D, & i = k \\ 0, & i \neq k \end{cases}
$$

### 3.4 展开定理的应用技巧

**核心策略：先化零再展开**

通过行列式性质5，将某一行（列）尽可能多的元素化为 $0$，再沿该行（列）展开，从而降低行列式的阶数。

**例3：** 计算4阶行列式
$$
D = \begin{vmatrix} 1 & 2 & 0 & 1 \\ 1 & 3 & 5 & 0 \\ 0 & 1 & 5 & 6 \\ 1 & 2 & 3 & 4 \end{vmatrix}
$$

**解：**

第1行已经有1个零，我们设法把第1列其余元素也化零。

$r_2 - r_1, r_4 - r_1$：
$$
D = \begin{vmatrix} 1 & 2 & 0 & 1 \\ 0 & 1 & 5 & -1 \\ 0 & 1 & 5 & 6 \\ 0 & 0 & 3 & 3 \end{vmatrix}
$$

按第1列展开：$D = 1 \cdot \begin{vmatrix} 1 & 5 & -1 \\ 1 & 5 & 6 \\ 0 & 3 & 3 \end{vmatrix}$

$r_2 - r_1$：
$$
= \begin{vmatrix} 1 & 5 & -1 \\ 0 & 0 & 7 \\ 0 & 3 & 3 \end{vmatrix}
$$

按第1列展开：$= 1 \cdot \begin{vmatrix} 0 & 7 \\ 3 & 3 \end{vmatrix} = 1 \cdot (0 \cdot 3 - 7 \cdot 3) = -21$

所以 $D = -21$。

---

## 四、特殊行列式

### 4.1 上（下）三角行列式

> [!theorem|blue] 三角行列式的值
> $$
> \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ 0 & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & a_{nn} \end{vmatrix} = a_{11} a_{22} \cdots a_{nn} = \prod_{i=1}^{n} a_{ii}
> $$
> 上三角（或下三角）行列式的值等于**主对角线元素之积**。

### 4.2 对角行列式

$$
\begin{vmatrix} a_{11} & 0 & \cdots & 0 \\ 0 & a_{22} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & a_{nn} \end{vmatrix} = a_{11} a_{22} \cdots a_{nn}
$$

### 4.3 副对角线行列式

> [!theorem|blue]
> $$
> \begin{vmatrix} 0 & \cdots & 0 & a_{1n} \\ 0 & \cdots & a_{2,n-1} & 0 \\ \vdots & \ddots & \vdots & \vdots \\ a_{n1} & \cdots & 0 & 0 \end{vmatrix} = (-1)^{\frac{n(n-1)}{2}} a_{1n} a_{2,n-1} \cdots a_{n1}
> $$

---

## 五、易错点总结

> [!warning|red] 常见错误清单
> 1. **对角线法则仅限2、3阶**：4阶及以上不能用对角线法
> 2. **代数余子式带符号**：$A_{ij} = (-1)^{i+j} M_{ij}$，忘记 $(-1)^{i+j}$ 是常见错误
> 3. **展开时选零多的行/列**：先化零再展开，不要盲目按第一行展开
> 4. **倍加操作不改变行列式值**：但倍乘某行要乘以相应倍数
> 5. **交换两行变号**：如果做多次交换，奇数次变号、偶数次不变号
> 6. **副对角线行列式的符号**：$(-1)^{n(n-1)/2}$，不是 $(-1)^n$
> 7. **拆行列式只能拆一行（列）**：不能同时拆多行
> 8. **余子式 $M_{ij}$ 不带符号，代数余子式 $A_{ij}$ 带符号**：注意区分

---

## 六、本讲小结

| 内容 | 核心公式 |
|------|---------|
| 逆序数定义 | $\sum (-1)^{\tau} a_{1j_1} \cdots a_{nj_n}$ |
| 转置不变 | $D^T = D$ |
| 换行变号 | 交换两行 → $D$ 变为 $-D$ |
| 倍加不变 | 某行加另一行的 $k$ 倍 → $D$ 不变 |
| 按行展开 | $D = \sum_j a_{ij} A_{ij}$ |
| 错行消零 | $\sum_j a_{ij} A_{kj} = 0 \; (i \neq k)$ |

> [!tip|blue] 考研重点
> 行列式性质是整个线性代数的基础工具，必须熟练掌握。特别是性质5（倍加不变性）是计算行列式的核心手段。展开定理是连接行列式与矩阵（伴随矩阵）的桥梁。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/01-行列式/Lecture 2：行列式的计算]] — 行列式计算
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 3：矩阵的定义及其基本运算]] — 矩阵基础
