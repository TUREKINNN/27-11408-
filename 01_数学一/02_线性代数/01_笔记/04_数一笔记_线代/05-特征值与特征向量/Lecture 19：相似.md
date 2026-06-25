---
title: "Lecture 19：相似"
subject: 线性代数
chapter: 05-特征值与特征向量
difficulty: hard
exam_focus: true
created: 2026-06-16
---

# Lecture 19：相似

## 一、相似矩阵的定义

### 1.1 定义

> 设 $A, B$ 都是 $n$ 阶矩阵，若存在**可逆矩阵** $P$，使得
>
> $$\boxed{P^{-1}AP = B}$$
>
> 则称 $A$ 与 $B$ **相似**，记为 $A \sim B$，$P$ 称为**相似变换矩阵**。

> - $P$ 必须是**可逆矩阵**
> - 相似关系是**等价关系**（自反、对称、传递）

### 1.2 相似的等价表述

> $A \sim B$ 意味着 $A$ 和 $B$ 是**同一个线性变换**在**不同基**下的矩阵表示。
>
> $P$ 就是从旧基到新基的**过渡矩阵**。

---

## 二、相似矩阵的性质

### 2.1 基本性质

>
> 若 $A \sim B$，则 $A$ 与 $B$ 有：
>
> | 性质 | 表达式 |
> |------|--------|
> | **相同行列式** | $|A| = |B|$ |
> | **相同秩** | $r(A) = r(B)$ |
> | **相同迹** | $\text{tr}(A) = \text{tr}(B)$ |
> | **相同特征值** | $\lambda(A) = \lambda(B)$ |
> | **相同特征多项式** | $|A - \lambda I| = |B - \lambda I|$ |
> | **相同行列式因子** | 各阶行列式因子相同 |

**证明**（以特征值为例）：

$|B - \lambda I| = |P^{-1}AP - \lambda I| = |P^{-1}(A - \lambda I)P| = |P^{-1}| \cdot |A - \lambda I| \cdot |P| = |A - \lambda I|$

### 2.2 进一步性质

>
> 若 $A \sim B$，则：
>
> | 运算 | 结论 |
> |------|------|
> | $A^m \sim B^m$ | 幂次 |
> | $A^T \sim B^T$ | 转置 |
> | $kA \sim kB$ | 数乘 |
> | $f(A) \sim f(B)$ | 多项式 |
> | $A^{-1} \sim B^{-1}$ | 逆（若可逆） |
> | $A^* \sim B^*$ | 伴随矩阵 |

> 相似矩阵**不一定**有相同的特征向量！特征向量与基的选择有关。

---

## 三、相似对角化

### 3.1 可相似对角化的条件

>
> $n$ 阶矩阵 $A$ **可相似对角化** $\iff$ $A$ 有 $n$ 个**线性无关的特征向量**。
>
> 等价条件：
> - $A$ 的每个特征值的**几何重数 = 代数重数**
> - 各特征子空间的维数之和 $= n$

> - 若 $A$ 有 $n$ 个**互不相同**的特征值，则 $A$ **一定可对角化**
> - 但有重特征值的矩阵**也可能**可对角化（只要几何重数 = 代数重数）

### 3.2 对角化的步骤

>
> **第一步**：求 $A$ 的所有特征值 $\lambda_1, \lambda_2, \ldots, \lambda_s$（含重根）
>
> **第二步**：对每个 $\lambda_i$，解 $(A - \lambda_i I)x = 0$，求基础解系
>
> **第三步**：检查线性无关特征向量总数是否为 $n$
> - 若 $< n$，则 $A$ **不可对角化**
> - 若 $= n$，继续
>
> **第四步**：令 $P = (\xi_1, \xi_2, \ldots, \xi_n)$，则
>
> $$P^{-1}AP = \Lambda = \text{diag}(\lambda_1, \lambda_2, \ldots, \lambda_n)$$
>
> 其中 $\Lambda$ 对角线上元素的顺序与 $P$ 中列向量的顺序**一一对应**。

> - $P$ 的列是**特征向量**，$\Lambda$ 对角线是对应的**特征值**
> - $\Lambda$ 中对角元素的**排列顺序**必须与 $P$ 中列向量的顺序一致
> - $P$ 的取法不唯一（特征向量可以取不同倍数、不同排列），但 $\Lambda$ 的对角线元素集合唯一（不计顺序）

### 3.3 对角化的应用

>
> 若 $P^{-1}AP = \Lambda$，则 $A = P\Lambda P^{-1}$，所以
>
> $$A^k = P\Lambda^k P^{-1} = P \begin{pmatrix} \lambda_1^k & & \\ & \ddots & \\ & & \lambda_n^k \end{pmatrix} P^{-1}$$
>
> 这在计算矩阵的高次幂时非常有用。

---

## 四、实对称矩阵的正交对角化

### 4.1 基本定理

>
> 若 $A$ 是**实对称矩阵**，则：
>
> 1. $A$ 的特征值**全是实数**
> 2. $A$ **一定可对角化**（每个特征值的几何重数 = 代数重数）
> 3. 存在**正交矩阵** $Q$，使得
>
> $$\boxed{Q^T A Q = Q^{-1}AQ = \Lambda = \text{diag}(\lambda_1, \lambda_2, \ldots, \lambda_n)}$$
>
> 即实对称矩阵**一定可以正交对角化**。

### 4.2 正交对角化的步骤

>
> **第一步**：求特征值 $\lambda_1, \ldots, \lambda_s$（同一般对角化）
>
> **第二步**：对每个 $\lambda_i$，解 $(A - \lambda_i I)x = 0$，求基础解系（同一般对角化）
>
> **第三步**：对每个特征子空间的基，进行 **Schmidt 正交化** 再**单位化**
> - 单重特征值：直接单位化即可（该子空间只有一维）
> - 多重特征值：先 Schmidt 正交化，再逐个单位化
>
> **第四步**：将所有单位正交特征向量排成矩阵 $Q$，则 $Q$ 为正交矩阵，且 $Q^T A Q = \Lambda$

>
> 设 $A\xi = \lambda\xi$，取共轭：$\bar{A}\bar{\xi} = \bar{\lambda}\bar{\xi}$。
>
> 因为 $A$ 实对称，$\bar{A} = A$，$A^T = A$。
>
> 取 $\bar{\xi}^T A\xi = \lambda \bar{\xi}^T \xi$，又 $\bar{\xi}^T A\xi = (A\bar{\xi})^T \xi = \bar{\lambda}\bar{\xi}^T\xi$。
>
> 所以 $\lambda \bar{\xi}^T\xi = \bar{\lambda}\bar{\xi}^T\xi$。
>
> 因为 $\xi \neq 0$，$\bar{\xi}^T\xi = |\xi_1|^2 + \cdots + |\xi_n|^2 > 0$。
>
> 所以 $\lambda = \bar{\lambda}$，即 $\lambda$ 是实数。✓

### 4.3 Schmidt 正交化公式回顾

设 $\alpha_1, \alpha_2, \ldots, \alpha_m$ 线性无关：

$$\beta_1 = \alpha_1$$

$$\beta_2 = \alpha_2 - \frac{(\alpha_2, \beta_1)}{(\beta_1, \beta_1)} \beta_1$$

$$\beta_3 = \alpha_3 - \frac{(\alpha_3, \beta_1)}{(\beta_1, \beta_1)} \beta_1 - \frac{(\alpha_3, \beta_2)}{(\beta_2, \beta_2)} \beta_2$$

单位化：$\eta_i = \dfrac{\beta_i}{|\beta_i|}$

> 必须按 $\beta_1, \beta_2, \ldots$ 的顺序逐个正交化，不能跳步。

---

## 五、典型例题

### 例1：判断矩阵是否可对角化

设 $A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$，判断是否可对角化。

**解**：

特征方程：$(1-\lambda)^2 = 0$，$\lambda = 1$（二重）。

$(A - I)x = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} x = 0$

基础解系只有一个向量 $\xi = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$。

几何重数 = 1 $<$ 代数重数 = 2。

**$A$ 不可对角化**。

### 例2：对角化矩阵

设 $A = \begin{pmatrix} 4 & 0 & 0 \\ 0 & 3 & 1 \\ 0 & 1 & 3 \end{pmatrix}$，求 $P$ 使 $P^{-1}AP = \Lambda$。

**解**：

特征方程：$(4-\lambda)[(3-\lambda)^2 - 1] = (4-\lambda)(2-\lambda)(4-\lambda) = 0$

$\lambda_1 = 2$（一重），$\lambda_2 = 4$（二重）。

$\lambda_1 = 2$：$(A-2I)x = 0$ → $\xi_1 = \begin{pmatrix} 0 \\ 1 \\ -1 \end{pmatrix}$

$\lambda_2 = 4$：$(A-4I)x = 0$ → $\xi_2 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$，$\xi_3 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}$

3个线性无关特征向量，可对角化。

$$P = \begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 1 \\ -1 & 0 & 1 \end{pmatrix}, \quad \Lambda = \begin{pmatrix} 2 & & \\ & 4 & \\ & & 4 \end{pmatrix}$$

### 例3：正交对角化实对称矩阵

设 $A = \begin{pmatrix} 2 & -1 & -1 \\ -1 & 2 & -1 \\ -1 & -1 & 2 \end{pmatrix}$，求正交矩阵 $Q$ 使得 $Q^T A Q = \Lambda$。

**解**：

特征方程：$|A - \lambda I| = -\lambda(\lambda - 3)^2 = 0$

$\lambda_1 = 0$（一重），$\lambda_2 = 3$（二重）。

$\lambda_1 = 0$：$Ax = 0$ → $\xi_1 = \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}$，单位化：$\eta_1 = \frac{1}{\sqrt{3}}\begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}$

$\lambda_2 = 3$：$(A - 3I)x = 0$ → 基础解系 $\alpha_1 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}$，$\alpha_2 = \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}$

Schmidt 正交化：

$\beta_1 = \alpha_1 = \begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}$

$\beta_2 = \alpha_2 - \frac{(\alpha_2, \beta_1)}{(\beta_1, \beta_1)}\beta_1 = \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix} - \frac{1}{2}\begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} -1/2 \\ -1/2 \\ 1 \end{pmatrix}$

单位化：$\eta_2 = \frac{1}{\sqrt{2}}\begin{pmatrix} -1 \\ 1 \\ 0 \end{pmatrix}$，$\eta_3 = \frac{1}{\sqrt{6}}\begin{pmatrix} -1 \\ -1 \\ 2 \end{pmatrix}$

$$Q = \begin{pmatrix} \frac{1}{\sqrt{3}} & \frac{-1}{\sqrt{2}} & \frac{-1}{\sqrt{6}} \\ \frac{1}{\sqrt{3}} & \frac{1}{\sqrt{2}} & \frac{-1}{\sqrt{6}} \\ \frac{1}{\sqrt{3}} & 0 & \frac{2}{\sqrt{6}} \end{pmatrix}, \quad \Lambda = \begin{pmatrix} 0 & & \\ & 3 & \\ & & 3 \end{pmatrix}$$

### 例4：利用对角化计算高次幂

设 $A = \begin{pmatrix} 3 & 1 \\ 1 & 3 \end{pmatrix}$，求 $A^{100}$。

**解**：

由例1（Lecture 18）：$\lambda_1 = 2, \xi_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$；$\lambda_2 = 4, \xi_2 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$

$P = \begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix}$，$P^{-1} = \frac{1}{2}\begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}$

$$A^{100} = P \begin{pmatrix} 2^{100} & 0 \\ 0 & 4^{100} \end{pmatrix} P^{-1} = \frac{1}{2}\begin{pmatrix} 2^{100} + 4^{100} & -2^{100} + 4^{100} \\ -2^{100} + 4^{100} & 2^{100} + 4^{100} \end{pmatrix}$$

### 例5：判断不可对角化的矩阵

设 $A = \begin{pmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{pmatrix}$，判断是否可对角化。

**解**：

特征方程：$(2-\lambda)^3 = 0$，$\lambda = 2$（三重）。

$(A - 2I)x = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix} x = 0$

基础解系只有 $\xi = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$，几何重数 = 1 $<$ 代数重数 = 3。

**$A$ 不可对角化**。这是典型的 Jordan 块。

---

## 六、易错点总结

> 有相同特征值的矩阵**不一定**相似。例如 $A = I$ 和 $B = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$ 特征值都是 1,1，但 $A \sim I \neq B$（$B$ 不可对角化）。
>
> 正确说法：相似 $\Rightarrow$ 相同特征值，反之不然。

> 一般矩阵即使可对角化，变换矩阵 $P$ 也不一定是正交矩阵。只有**实对称矩阵**才能保证正交对角化。

> 属于**不同特征值**的特征向量已经正交（实对称矩阵），不需要正交化。只需对**同一特征值**的多个特征向量做正交化。

> $P = (\xi_1, \xi_2, \xi_3)$ 时，$\Lambda = \text{diag}(\lambda_1, \lambda_2, \lambda_3)$，其中 $\lambda_i$ 是 $\xi_i$ 对应的特征值。顺序不能错。

> 对同一矩阵 $A$，$P$ 的选取不唯一。特征向量可以乘以任意非零常数，可以重新排列。但 $\Lambda$ 的对角线元素集合唯一。

---

## 七、知识框架

```
相似
├── 定义：P⁻¹AP = B，P可逆
├── 相似矩阵性质
│   ├── 相同行列式、秩、迹
│   ├── 相同特征值和特征多项式
│   └── 运算保持相似
├── 相似对角化
│   ├── 条件：n个线性无关特征向量
│   ├── 等价条件：每个λᵢ的几何重数=代数重数
│   ├── 步骤：求λ→求ξ→组成P
│   └── 应用：A^k = PΛᵏP⁻¹
├── 实对称矩阵
│   ├── 特征值全实数
│   ├── 一定可对角化
│   ├── 不同特征值的特征向量正交
│   └── 正交对角化：Q⁻¹AQ = Λ
└── 与Jordan标准形的关系
    └── 不可对角化 → Jordan块
```

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/05-特征值与特征向量/Lecture 18：特征值与特征向量]] — 特征值
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/06-二次型/Lecture 20：二次型的定义与矩阵表示]] — 二次型
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 9：矩阵的秩]] — 秩
