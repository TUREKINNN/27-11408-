---
title: "Lecture 18：特征值与特征向量"
subject: 线性代数
chapter: 05-特征值与特征向量
difficulty: hard
exam_focus: true
created: 2026-06-16
---

# Lecture 18：特征值与特征向量

## 一、特征值与特征向量的定义

### 1.1 定义

> 设 $A$ 是 $n$ 阶方阵，若存在**数** $\lambda$ 和**非零向量** $\xi$，使得
>
> $$A\xi = \lambda\xi$$
>
> 则称 $\lambda$ 为 $A$ 的一个**特征值**，$\xi$ 为 $A$ 对应于特征值 $\lambda$ 的一个**特征向量**。

> - 特征向量 $\xi$ **必须是非零向量**，零向量不是特征向量
> - 特征值 $\lambda$ 可以是零
> - 一个特征值可以对应**多个**线性无关的特征向量

### 1.2 几何含义

$A\xi = \lambda\xi$ 的含义：矩阵 $A$ 对向量 $\xi$ 的作用等价于将 $\xi$ **拉伸 $\lambda$ 倍**（$\lambda < 0$ 时还包括反向）。

> 特征向量是矩阵 $A$ 变换下**方向不变**（或恰好反向）的非零向量，特征值 $\lambda$ 就是伸缩倍数。

---

## 二、特征方程与求法

### 2.1 特征方程

> $A\xi = \lambda\xi$ 可改写为 $(A - \lambda I)\xi = 0$。
>
> 此方程有**非零解** $\xi$ 的充要条件是：
>
> $$\boxed{|A - \lambda I| = 0}$$
>
> 这就是 $A$ 的**特征方程**，它是关于 $\lambda$ 的 $n$ 次多项式。

$|A - \lambda I|$ 称为 $A$ 的**特征多项式**，记为 $f(\lambda) = |A - \lambda I|$。

### 2.2 求特征值和特征向量的步骤

>
> **第一步**：写出特征方程 $|A - \lambda I| = 0$
>
> **第二步**：展开行列式，求解关于 $\lambda$ 的 $n$ 次方程，得到全部特征值 $\lambda_1, \lambda_2, \ldots, \lambda_n$（含重根）
>
> **第三步**：对每个特征值 $\lambda_i$，解齐次方程组 $(A - \lambda_i I)x = 0$，求基础解系
>
> **第四步**：基础解系中的向量就是对应于 $\lambda_i$ 的**线性无关的特征向量**，通解（去掉零向量）就是全部特征向量

### 2.3 $|A - \lambda I|$ 的展开

对 $n$ 阶矩阵 $A$，特征多项式为：

$$f(\lambda) = |A - \lambda I| = (-1)^n \lambda^n + (-1)^{n-1} a_1 \lambda^{n-1} + \cdots + a_n$$

其中：
- $a_1 = \text{tr}(A) = a_{11} + a_{22} + \cdots + a_{nn}$（迹）
- $a_n = |A|$（行列式）

> 对 2 阶矩阵 $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$：
>
> $$|A - \lambda I| = \lambda^2 - (a+d)\lambda + (ad - bc) = \lambda^2 - \text{tr}(A)\lambda + |A|$$
>
> 对 3 阶矩阵可用对角线法则或按行/列展开。

---

## 三、特征值的性质

### 3.1 基本性质

>
> 设 $n$ 阶矩阵 $A$ 的特征值为 $\lambda_1, \lambda_2, \ldots, \lambda_n$（含重根按重数计），则：
>
> **(1)** 特征值之和 = 迹：
> $$\sum_{i=1}^n \lambda_i = \lambda_1 + \lambda_2 + \cdots + \lambda_n = \text{tr}(A) = a_{11} + a_{22} + \cdots + a_{nn}$$
>
> **(2)** 特征值之积 = 行列式：
> $$\prod_{i=1}^n \lambda_i = \lambda_1 \lambda_2 \cdots \lambda_n = |A|$$
>
> **(3)** $A$ 可逆 $\iff$ $A$ 的所有特征值都不为零（$0$ 不是 $A$ 的特征值）

**证明思路**：特征多项式 $f(\lambda) = |A - \lambda I| = (-\lambda)^n + \text{tr}(A)(-\lambda)^{n-1} + \cdots + |A|$

又由 Vieta 定理：$f(\lambda) = (\lambda_1 - \lambda)(\lambda_2 - \lambda) \cdots (\lambda_n - \lambda)$

比较系数即得。

### 3.2 特征值的传递性质

>
> 若 $\lambda$ 是 $A$ 的特征值，$\xi$ 是对应的特征向量，则：
>
> | 表达式 | 特征值 | 特征向量 |
> |--------|--------|----------|
> | $kA$ | $k\lambda$ | $\xi$ |
> | $A^m$ | $\lambda^m$ | $\xi$ |
> | $A^T$ | $\lambda$ | 一般不同 |
> | $f(A) = a_0 I + a_1 A + \cdots + a_m A^m$ | $f(\lambda)$ | $\xi$ |
> | $A^{-1}$（$A$ 可逆） | $\dfrac{1}{\lambda}$ | $\xi$ |
> | $A^*$（伴随矩阵） | $\dfrac{|A|}{\lambda}$ | $\xi$ |

**推导**：以 $A^2$ 为例，$A^2 \xi = A(A\xi) = A(\lambda\xi) = \lambda(A\xi) = \lambda^2 \xi$。

> $A^T$ 与 $A$ 有**相同的特征值**，但特征向量一般不同。$A$ 的特征向量 $\xi$ 满足 $A\xi = \lambda\xi$，但 $A^T\xi$ 一般不等于 $\lambda\xi$。

### 3.3 不同特征值对应的特征向量线性无关

> 属于**不同特征值**的特征向量**线性无关**。
>
> 更强的结论：设 $\lambda_1, \lambda_2, \ldots, \lambda_m$ 是 $A$ 的**互不相同**的特征值，$\xi_{i1}, \ldots, \xi_{ik_i}$ 是 $\lambda_i$ 对应的线性无关的特征向量，则
>
> $$\xi_{11}, \ldots, \xi_{1k_1}, \xi_{21}, \ldots, \xi_{2k_2}, \ldots, \xi_{m1}, \ldots, \xi_{mk_m}$$
>
> 线性无关。

**证明思路**（2个特征值的情形）：

设 $A\xi_1 = \lambda_1 \xi_1$，$A\xi_2 = \lambda_2 \xi_2$，$\lambda_1 \neq \lambda_2$。

令 $k_1 \xi_1 + k_2 \xi_2 = 0$，两边左乘 $A$：
$k_1 \lambda_1 \xi_1 + k_2 \lambda_2 \xi_2 = 0$

从两个方程消去 $\xi_2$：$k_1(\lambda_1 - \lambda_2)\xi_1 = 0$。

因为 $\lambda_1 \neq \lambda_2$ 且 $\xi_1 \neq 0$，所以 $k_1 = 0$，从而 $k_2 = 0$。✓

---

## 四、特征向量的性质

### 4.1 特征子空间

> 对特征值 $\lambda_i$，齐次方程组 $(A - \lambda_i I)x = 0$ 的**解空间**
>
> $$V_{\lambda_i} = \{x \mid (A - \lambda_i I)x = 0\}$$
>
> 称为 $\lambda_i$ 的**特征子空间**。
>
> $\dim(V_{\lambda_i}) = n - r(A - \lambda_i I)$

特征子空间中的所有非零向量都是 $\lambda_i$ 对应的特征向量。

### 4.2 特征值的重数

> - **代数重数**：特征值 $\lambda_i$ 作为特征方程的根的重数
> - **几何重数**：$\lambda_i$ 对应的特征子空间的维数 $= n - r(A - \lambda_i I)$
>
> **重要不等式**：
> $$\boxed{1 \leq \text{几何重数} \leq \text{代数重数}}$$

> 几何重数 $\leq$ 代数重数，等号不一定成立。只有当等号对所有特征值都成立时，$A$ 才能相似对角化。

### 4.3 实对称矩阵的特殊性质

> 若 $A$ 是**实对称矩阵**，则：
> 1. $A$ 的特征值**全是实数**
> 2. 属于**不同特征值**的特征向量**正交**
> 3. 每个特征值的几何重数 = 代数重数

---

## 五、典型例题

### 例1：求 2 阶矩阵的特征值和特征向量

设 $A = \begin{pmatrix} 3 & 1 \\ 1 & 3 \end{pmatrix}$，求特征值和特征向量。

**解**：

**第一步**：特征方程

$$|A - \lambda I| = \begin{vmatrix} 3-\lambda & 1 \\ 1 & 3-\lambda \end{vmatrix} = (3-\lambda)^2 - 1 = \lambda^2 - 6\lambda + 8 = 0$$

**第二步**：解方程 $(\lambda - 2)(\lambda - 4) = 0$，得 $\lambda_1 = 2$，$\lambda_2 = 4$。

验证：$\text{tr}(A) = 6 = 2 + 4$ ✓，$|A| = 8 = 2 \times 4$ ✓

**第三步**：求特征向量

$\lambda_1 = 2$：$(A - 2I)x = 0$，即 $\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix} x = 0$

基础解系：$\xi_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$

$\lambda_2 = 4$：$(A - 4I)x = 0$，即 $\begin{pmatrix} -1 & 1 \\ 1 & -1 \end{pmatrix} x = 0$

基础解系：$\xi_2 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$


### 例2：求 3 阶矩阵的特征值和特征向量

设 $A = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 3 & 1 \\ 0 & 1 & 3 \end{pmatrix}$，求全部特征值和特征向量。

**解**：

$$|A - \lambda I| = (2-\lambda)[(3-\lambda)^2 - 1] = (2-\lambda)(\lambda^2 - 6\lambda + 8) = (2-\lambda)(2-\lambda)(4-\lambda)$$

特征值：$\lambda_1 = 2$（二重），$\lambda_2 = 4$（一重）。

$\lambda_1 = 2$：$(A - 2I)x = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 1 & 1 \\ 0 & 1 & 1 \end{pmatrix} x = 0$

基础解系：$\xi_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$，$\xi_2 = \begin{pmatrix} 0 \\ 1 \\ -1 \end{pmatrix}$

$\lambda_2 = 4$：$(A - 4I)x = \begin{pmatrix} -2 & 0 & 0 \\ 0 & -1 & 1 \\ 0 & 1 & -1 \end{pmatrix} x = 0$

基础解系：$\xi_3 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}$


### 例3：利用特征值性质求解

设 3 阶矩阵 $A$ 的特征值为 $1, -1, 2$，求 $|A^2 + 2A - I|$。

**解**：

$A^2 + 2A - I$ 的特征值分别为：

- 对 $\lambda = 1$：$1^2 + 2(1) - 1 = 2$
- 对 $\lambda = -1$：$(-1)^2 + 2(-1) - 1 = -2$
- 对 $\lambda = 2$：$2^2 + 2(2) - 1 = 7$

$$|A^2 + 2A - I| = 2 \times (-2) \times 7 = -28$$

### 例4：已知特征值求参数

设 $A = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 0 & a \\ 0 & a & 0 \end{pmatrix}$ 有特征值 $\lambda = 2$（三重），求 $a$。

**解**：

特征多项式：$|A - \lambda I| = (2 - \lambda)(\lambda^2 - a^2)$

$\lambda = 2$ 代入：$(2 - 2)(4 - a^2) = 0$ 恒成立。

要使 $\lambda = 2$ 是三重根，需 $\lambda^2 - a^2 = (\lambda - 2)(\lambda + 2)$... 

不对，需 $\lambda^2 - a^2 = (\lambda - 2)^2$？这不可能。

实际上 $(2 - \lambda)(\lambda^2 - a^2) = 0$ 的根为 $\lambda = 2, \pm a$。

要使三个根都是 2，需 $a = 2$ 且 $-a = 2$，不可能。

所以不存在这样的 $a$。题意可能是 $\lambda = 2$ 为一个特征值，求 $|A|$ 等。


### 例5：抽象矩阵的特征值

设 $A^2 = A$（幂等矩阵），$A \neq 0$，$A \neq I$，求 $A$ 的特征值。

**解**：

设 $A\xi = \lambda\xi$，则 $A^2\xi = \lambda^2\xi$。

又 $A^2 = A$，所以 $\lambda^2\xi = \lambda\xi$，即 $(\lambda^2 - \lambda)\xi = 0$。

因为 $\xi \neq 0$，所以 $\lambda^2 - \lambda = 0$，$\lambda = 0$ 或 $\lambda = 1$。

又 $A \neq 0$，所以 $\lambda = 0$ 不是唯一特征值（否则 $A = 0$）。

又 $A \neq I$，所以 $\lambda = 1$ 不是唯一特征值。

**结论**：$A$ 的特征值只能是 $0$ 和 $1$，且两者都必须出现。

---

## 六、易错点总结

> $A \cdot 0 = \lambda \cdot 0$ 恒成立，但 $0$ **不是**特征向量。特征向量定义中要求 $\xi \neq 0$。

> $\sum \lambda_i = \text{tr}(A)$ 和 $\prod \lambda_i = |A|$ 中，特征值按**代数重数**计算。例如 $\lambda = 2$ 是二重根，求和时要加两次。

> $A$ 和 $A^T$ 有相同的特征值，但特征向量一般不同。不能想当然地认为 $A^T\xi = \lambda\xi$。

> 特征子空间的维数 $\geq 1$，当几何重数 $> 1$ 时，有多个线性无关的特征向量。但一个特征向量只能对应一个特征值。

> 对含参数的行列式，展开时注意符号和系数，特别是对角线上的元素容易算错。

---

## 七、知识框架

```
特征值与特征向量
├── 定义：Aξ = λξ，ξ ≠ 0
├── 求法
│   ├── 特征方程 |A - λI| = 0
│   ├── 求特征值
│   └── 对每个λ解 (A - λI)x = 0
├── 特征值性质
│   ├── ∑λᵢ = tr(A)
│   ├── ∏λᵢ = |A|
│   ├── A可逆 ⟺ 0不是特征值
│   └── f(A)的特征值 = f(λ)
├── 特征向量性质
│   ├── 不同特征值的特征向量线性无关
│   ├── 1 ≤ 几何重数 ≤ 代数重数
│   └── 实对称矩阵：特征值全实数，不同特征值的特征向量正交
└── 应用
    ├── 判断矩阵可逆
    ├── 求矩阵多项式的行列式
    └── 为相似对角化做准备
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/05-特征值与特征向量/Lecture 19：相似]] — 相似
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/06-二次型/Lecture 20：二次型的定义与矩阵表示]] — 二次型
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/01-行列式/Lecture 1：行列式的定义与性质]] — 行列式
