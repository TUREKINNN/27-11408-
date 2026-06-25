---
title: Lecture 8：等价矩阵
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 8：等价矩阵

## 一、等价矩阵的定义

> [!definition|purple] 等价矩阵
> 设 $A$ 和 $B$ 都是 $m \times n$ 矩阵，若存在 $m$ 阶可逆矩阵 $P$ 和 $n$ 阶可逆矩阵 $Q$，使得
> $$
> PAQ = B
> $$
> 则称 $A$ 与 $B$ **等价**（或相抵），记为 $A \cong B$。

**等价的等价描述：**
- $A$ 可以通过有限次初等变换变为 $B$
- $A$ 可以通过有限次初等行变换和初等列变换变为 $B$

---

## 二、等价矩阵的性质

> [!theorem|blue] 等价矩阵的性质
> **自反性：** $A \cong A$（取 $P = I_m, Q = I_n$）
>
> **对称性：** 若 $A \cong B$，则 $B \cong A$（取 $P^{-1}$ 和 $Q^{-1}$）
>
> **传递性：** 若 $A \cong B$ 且 $B \cong C$，则 $A \cong C$

即等价关系是**等价关系**（满足自反性、对称性、传递性）。

---

## 三、等价矩阵的判定

> [!theorem|blue] 等价矩阵的充要条件
> $m \times n$ 矩阵 $A$ 与 $B$ 等价 $\Leftrightarrow$ $r(A) = r(B)$
>
> 即两个同型矩阵等价，当且仅当它们的**秩相等**。

**证明：**

($\Rightarrow$) 若 $PAQ = B$，$P, Q$ 可逆，则 $r(B) = r(PAQ) = r(A)$（初等变换不改变秩）。

($\Leftarrow$) 若 $r(A) = r(B) = r$，则 $A$ 和 $B$ 都等价于同一标准形 $\begin{pmatrix} I_r & O \\ O & O \end{pmatrix}$，由对称性和传递性得 $A \cong B$。

---

## 四、等价标准形

> [!definition|purple] 等价标准形
> 任何秩为 $r$ 的 $m \times n$ 矩阵 $A$ 都等价于标准形：
> $$
> \begin{pmatrix} I_r & O_{r \times (n-r)} \\ O_{(m-r) \times r} & O_{(m-r) \times (n-r)} \end{pmatrix}
> $$
> 即存在可逆矩阵 $P$（$m$ 阶）和 $Q$（$n$ 阶）使得 $PAQ = \begin{pmatrix} I_r & O \\ O & O \end{pmatrix}$。

**标准形的唯一性：** 对于给定的 $m \times n$ 矩阵，其等价标准形由秩 $r$ 唯一确定。

### 求等价标准形的步骤

1. 通过初等行变换将 $A$ 化为行阶梯形
2. 通过初等列变换进一步化为标准形

**例1：** 求 $A = \begin{pmatrix} 1 & 2 & 3 & 4 \\ 2 & 5 & 7 & 9 \\ 3 & 7 & 10 & 13 \end{pmatrix}$ 的等价标准形。

**解：**

$$
A \xrightarrow{r_2-2r_1, r_3-3r_1} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & 1 \\ 0 & 1 & 1 & 1 \end{pmatrix} \xrightarrow{r_3-r_2} \begin{pmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \end{pmatrix}
$$

$$
\xrightarrow{c_2-2c_1, c_3-3c_1, c_4-4c_1} \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 \end{pmatrix} \xrightarrow{c_3-c_2, c_4-c_2} \begin{pmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 \end{pmatrix}
$$

$r(A) = 2$，标准形为 $\begin{pmatrix} I_2 & O \\ O & O \end{pmatrix}$。

---

## 五、等价矩阵与相似矩阵、合同矩阵的区别

> [!warning|red] 三种"等价"概念的区别
> | 概念 | 定义 | 条件 |
> |------|------|------|
> | **等价** | $PAQ = B$，$P,Q$ 可逆 | $r(A) = r(B)$ |
> | **相似** | $P^{-1}AP = B$，$P$ 可逆 | 特征值相同（更严格） |
> | **合同** | $P^TAP = B$，$P$ 可逆 | 惯性指数相同（针对对称矩阵） |
>
> - 相似 $\Rightarrow$ 等价（因为相似要求 $P^{-1}AP = B$，即用同一个 $P$ 做左乘和右乘）
> - 合同 $\Rightarrow$ 等价
> - 等价 $\not\Rightarrow$ 相似，等价 $\not\Rightarrow$ 合同

---

## 六、秩的性质（与等价相关的补充）

> [!theorem|blue] 矩阵秩的基本性质
> 1. $0 \le r(A_{m \times n}) \le \min(m, n)$
> 2. $r(A) = r(A^T) = r(A^TA) = r(AA^T)$
> 3. $r(A+B) \le r(A) + r(B)$
> 4. $r(AB) \le \min(r(A), r(B))$
> 5. 若 $A$ 可逆，则 $r(AB) = r(B)$，$r(CA) = r(C)$
> 6. $r(A) + r(B) - n \le r(AB)$（Sylvester不等式）
> 7. 若 $AB = O$，则 $r(A) + r(B) \le n$

### 性质7的证明

**证明：** $AB = O$，则 $B$ 的每一列都是 $Ax = 0$ 的解。

$Ax = 0$ 的解空间维数为 $n - r(A)$。

$B$ 的列空间是 $Ax = 0$ 解空间的子空间，故 $r(B) \le n - r(A)$。

即 $r(A) + r(B) \le n$。 $\blacksquare$

### 应用例题

**例2：** 设 $A$ 为 $n$ 阶方阵，$A^2 = I$，证明 $r(A+I) + r(A-I) = n$。

**证明：**

由 $A^2 = I$ 得 $A^2 - I = O$，即 $(A+I)(A-I) = O$。

由性质7：$r(A+I) + r(A-I) \le n$ ... (*)

又 $r(A+I) + r(A-I) \ge r((A+I) - (A-I)) = r(2I) = n$ ... (**)

（利用性质3：$r(P) + r(Q) \ge r(P-Q)$）

由(*)和(**)得 $r(A+I) + r(A-I) = n$。 $\blacksquare$

---

## 七、易错点总结

> [!warning|red] 常见错误清单
> 1. **等价只要求秩相等**：不要与相似（特征值相同）、合同（惯性指数相同）混淆
> 2. **等价矩阵必须同型**：$A$ 和 $B$ 必须是 $m \times n$ 的
> 3. **标准形由秩唯一确定**：秩相同的标准形相同
> 4. **$r(AB) \le \min(r(A), r(B))$**：等号成立需要附加条件（如 $A$ 或 $B$ 可逆）
> 5. **$AB = O \Rightarrow r(A) + r(B) \le n$**：这是考研高频公式
> 6. **等价是矩阵之间的关系**：不是行列式相等
> 7. **初等变换不改变秩**：这是等价理论的基础
> 8. **$r(A^TA) = r(A)$**：这个性质在最小二乘法中有重要应用

---

## 八、本讲小结

| 概念 | 定义 | 判定条件 |
|------|------|---------|
| 等价 | $PAQ = B$ | $r(A) = r(B)$ |
| 标准形 | $\begin{pmatrix} I_r & O \\ O & O \end{pmatrix}$ | 由秩唯一确定 |
| $AB=O$ 的秩关系 | $r(A)+r(B) \le n$ | Sylvester不等式 |

> [!tip|blue] 考研重点
> 等价矩阵的概念是连接初等变换和矩阵秩的桥梁。$AB = O$ 时 $r(A) + r(B) \le n$ 是考研证明题的高频工具。等价、相似、合同三个概念的区别是选择题的常见考点。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 6：初等变换与初等矩阵]] — 初等变换
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 9：矩阵的秩]] — 秩
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/03-向量组/Lecture 12：等价向量组]] — 等价向量组
