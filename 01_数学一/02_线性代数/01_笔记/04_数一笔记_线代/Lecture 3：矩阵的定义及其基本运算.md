---
title: Lecture 3：矩阵的定义及其基本运算
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 3：矩阵的定义及其基本运算

## 一、矩阵的定义

> [!definition|purple] 矩阵
> 由 $m \times n$ 个数 $a_{ij}$（$i=1,2,\cdots,m$；$j=1,2,\cdots,n$）排成的 $m$ 行 $n$ 列的数表
> $$
> A = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}
> $$
> 称为 $m \times n$ **矩阵**，简记为 $A = (a_{ij})_{m \times n}$ 或 $A_{m \times n}$。

**特殊矩阵：**
- **零矩阵** $O$：所有元素为 $0$
- **单位矩阵** $I$（或 $E$）：主对角线为 $1$，其余为 $0$
- **对角矩阵** $\text{diag}(\lambda_1, \lambda_2, \cdots, \lambda_n)$
- **数量矩阵** $kI$：主对角线全为 $k$
- **行矩阵**（行向量）：$1 \times n$ 矩阵
- **列矩阵**（列向量）：$m \times 1$ 矩阵

---

## 二、矩阵的加法与数乘

### 2.1 矩阵加法

> [!definition|purple] 矩阵加法
> 设 $A = (a_{ij})_{m \times n}$，$B = (b_{ij})_{m \times n}$，则
> $$
> A + B = (a_{ij} + b_{ij})_{m \times n}
> $$
> 即对应位置的元素相加。**只有同型矩阵才能相加。**

**运算律：**
- $A + B = B + A$（交换律）
- $(A + B) + C = A + (B + C)$（结合律）
- $A + O = A$
- $A + (-A) = O$

### 2.2 数乘矩阵

> [!definition|purple] 数乘
> 设 $k$ 为数，$A = (a_{ij})_{m \times n}$，则
> $$
> kA = (ka_{ij})_{m \times n}
> $$
> 即 $k$ 乘以矩阵的每一个元素。

**运算律：**
- $k(A + B) = kA + kB$
- $(k + l)A = kA + lA$
- $(kl)A = k(lA)$
- $1 \cdot A = A$

> [!warning|red] 易错点
> $|kA| = k^n |A|$（$n$ 为矩阵的阶数），不是 $k|A|$！这是考研高频易错点。

---

## 三、矩阵乘法

### 3.1 矩阵乘法的定义

> [!definition|purple] 矩阵乘法
> 设 $A = (a_{ij})_{m \times s}$，$B = (b_{ij})_{s \times n}$，则乘积 $AB = C = (c_{ij})_{m \times n}$，其中
> $$
> c_{ij} = \sum_{k=1}^{s} a_{ik} b_{kj} = a_{i1}b_{1j} + a_{i2}b_{2j} + \cdots + a_{is}b_{sj}
> $$
> 即 $C$ 的第 $i$ 行第 $j$ 列元素等于 $A$ 的第 $i$ 行与 $B$ 的第 $j$ 列的对应元素乘积之和。

**乘法条件：** $A$ 的列数 = $B$ 的行数（"左行右列"匹配）

### 3.2 矩阵乘法的性质

> [!theorem|blue] 矩阵乘法运算律
> - $(AB)C = A(BC)$（结合律）
> - $A(B + C) = AB + AC$（左分配律）
> - $(B + C)A = BA + CA$（右分配律）
> - $k(AB) = (kA)B = A(kB)$
> - $IA = AI = A$

### 3.3 矩阵乘法不满足交换律

> [!warning|red] 核心要点
> 矩阵乘法一般**不满足交换律**，即 $AB \neq BA$。

**原因：**
1. $AB$ 有意义时 $BA$ 不一定有意义（维度不匹配）
2. 即使都有意义，$AB$ 与 $BA$ 的阶数可能不同
3. 即使同阶，元素值也可能不同

**例1：** 设 $A = \begin{pmatrix} 1 & 1 \\ 0 & 0 \end{pmatrix}$，$B = \begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix}$

$$
AB = \begin{pmatrix} 2 & 0 \\ 0 & 0 \end{pmatrix}, \quad BA = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}
$$

显然 $AB \neq BA$。

> [!definition|purple] 可交换
> 若 $AB = BA$，则称 $A$ 与 $B$ **可交换**。
>
> 特别地，任何矩阵与 $kI$（数量矩阵）可交换。

### 3.4 矩阵乘法的特殊性质

> [!warning|red] 矩阵乘法的"反直觉"性质
> 1. $AB = O \not\Rightarrow A = O$ 或 $B = O$（矩阵乘法有**零因子**）
> 2. $AB = AC \not\Rightarrow B = C$（矩阵乘法**不能消去**，除非 $A$ 可逆）
> 3. $A^2 = O \not\Rightarrow A = O$（例如 $A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$）
> 4. $A^2 = A \not\Rightarrow A = O$ 或 $A = I$（幂等矩阵）

**例2：** 验证 $AB = O$ 不必 $A = O$ 或 $B = O$

$$
A = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}
$$

$$
AB = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = O
$$

---

## 四、矩阵的幂

> [!definition|purple] 矩阵的幂
> $$
> A^n = \underbrace{A \cdot A \cdots A}_{n \text{ 个}}, \quad A^0 = I
> $$

**性质：**
- $A^m \cdot A^n = A^{m+n}$
- $(A^m)^n = A^{mn}$
- 一般 $(AB)^n \neq A^n B^n$（因为 $AB \neq BA$）
- 当 $AB = BA$ 时，$(AB)^n = A^n B^n$

### 例题

**例3：** 设 $A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$，求 $A^n$。

**解：**
$$
A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad A^3 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}
$$

归纳可得：
$$
A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}
$$

**例4：** 设 $A = \begin{pmatrix} \lambda & 1 & 0 \\ 0 & \lambda & 1 \\ 0 & 0 & \lambda \end{pmatrix}$，求 $A^n$。

**解：** 令 $A = \lambda I + N$，其中 $N = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{pmatrix}$。

注意 $N^2 = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$，$N^3 = O$。

由于 $\lambda I$ 与 $N$ 可交换：
$$
A^n = (\lambda I + N)^n = \sum_{k=0}^{n} \binom{n}{k} (\lambda I)^{n-k} N^k = \lambda^n I + n\lambda^{n-1} N + \frac{n(n-1)}{2}\lambda^{n-2} N^2
$$

$$
= \begin{pmatrix} \lambda^n & n\lambda^{n-1} & \frac{n(n-1)}{2}\lambda^{n-2} \\ 0 & \lambda^n & n\lambda^{n-1} \\ 0 & 0 & \lambda^n \end{pmatrix}
$$

---

## 五、矩阵的转置

> [!definition|purple] 矩阵的转置
> 将矩阵 $A$ 的行与列互换，得到的矩阵称为 $A$ 的**转置矩阵**，记为 $A^T$。
> 若 $A = (a_{ij})_{m \times n}$，则 $A^T = (a_{ji})_{n \times m}$。

> [!theorem|blue] 转置的运算律
> 1. $(A^T)^T = A$
> 2. $(A + B)^T = A^T + B^T$
> 3. $(kA)^T = kA^T$
> 4. $(AB)^T = B^T A^T$（**注意顺序翻转！**）

> [!warning|red] 易错点
> $(AB)^T = B^T A^T$，顺序**翻转**！不要写成 $A^T B^T$。
> 更一般地，$(A_1 A_2 \cdots A_k)^T = A_k^T \cdots A_2^T A_1^T$。

### 对称矩阵与反对称矩阵

> [!definition|purple] 对称矩阵
> 若 $A^T = A$，则称 $A$ 为**对称矩阵**，即 $a_{ij} = a_{ji}$。

> [!definition|purple] 反对称矩阵
> 若 $A^T = -A$，则称 $A$ 为**反对称矩阵**，即 $a_{ij} = -a_{ji}$。
>
> 反对称矩阵的主对角线元素必为 $0$（因为 $a_{ii} = -a_{ii}$，故 $a_{ii} = 0$）。

> [!theorem|blue] 分解定理
> 任何方阵都可以唯一分解为对称矩阵和反对称矩阵之和：
> $$
> A = \frac{A + A^T}{2} + \frac{A - A^T}{2}
> $$
> 其中 $\frac{A + A^T}{2}$ 对称，$\frac{A - A^T}{2}$ 反对称。

---

## 六、方阵的行列式

> [!theorem|blue] 方阵行列式的性质
> 设 $A, B$ 为 $n$ 阶方阵，$k$ 为数，则：
> 1. $|A^T| = |A|$
> 2. $|kA| = k^n |A|$（不是 $k|A|$！）
> 3. $|AB| = |A| \cdot |B|$
> 4. $|A^n| = |A|^n$

> [!warning|red] 关键公式
> $|AB| = |A| \cdot |B|$，但 $|A + B| \neq |A| + |B|$！
> $|kA| = k^n |A|$，**指数 $n$ 不能忘记**。

---

## 七、易错点总结

> [!warning|red] 常见错误清单
> 1. **矩阵乘法不满足交换律**：$AB \neq BA$（一般情况）
> 2. **$AB = O$ 不意味 $A = O$ 或 $B = O$**
> 3. **$(AB)^T = B^T A^T$**：顺序翻转
> 4. **$|kA| = k^n |A|$**：指数是阶数 $n$
> 5. **$|A+B| \neq |A| + |B|$**
> 6. **矩阵乘法有零因子**：不能随便消去
> 7. **矩阵与行列式的区别**：矩阵是数表，行列式是数
> 8. **矩阵相等要求对应元素都相等**

---

## 八、本讲小结

| 运算 | 公式/性质 | 注意事项 |
|------|---------|---------|
| 加法 | $A+B=(a_{ij}+b_{ij})$ | 同型才能加 |
| 数乘 | $kA=(ka_{ij})$ | $\|kA\|=k^n\|A\|$ |
| 乘法 | $c_{ij}=\sum_k a_{ik}b_{kj}$ | 不满足交换律 |
| 转置 | $(AB)^T=B^TA^T$ | 顺序翻转 |

> [!tip|blue] 考研重点
> 矩阵乘法不满足交换律是线性代数区别于普通代数的根本特征。由此产生的 $AB=O \not\Rightarrow A=O$ 或 $B=O$，以及 $AB=AC \not\Rightarrow B=C$ 等"反直觉"结论，是考研选择题的高频考点。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 4：矩阵的逆]] — 逆矩阵
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/01-行列式/Lecture 1：行列式的定义与性质]] — 行列式
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 5：伴随矩阵]] — 伴随矩阵
