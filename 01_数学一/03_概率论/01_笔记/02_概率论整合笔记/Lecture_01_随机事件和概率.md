---
title: Lecture 01 - 随机事件和概率
subject: 概率论与数理统计
chapter: 第一章
lecture: 01
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇 
  - 王式安《概率论与数理统计基础》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 01: 随机事件和概率

## 一、随机事件

### 1.1 随机试验与样本空间

<span style="background-color: #ccc1d9">**定义（随机试验）**</span> 满足以下三个条件的试验称为**随机试验**：
1. 可以在相同条件下重复进行
2. 每次试验的可能结果不止一个，且事先明确所有可能结果
3. 试验前不能确定出现哪个结果

<span style="background-color: #ccc1d9">**定义（样本空间）**</span> 随机试验的所有可能结果组成的集合称为**样本空间**，记作 $\Omega$ 或 $S$。每个可能结果称为**样本点**。

### 1.2 随机事件

<span style="background-color: #ccc1d9">**定义（随机事件）**</span> 样本空间的子集称为**随机事件**，简称**事件**。

**事件的分类**：
- **基本事件**：只含一个样本点的事件
- **复合事件**：含多个样本点的事件
- **必然事件**：$\Omega$，每次试验必然发生
- **不可能事件**：$\emptyset$，每次试验不可能发生

### 1.3 事件的关系与运算

<span style="background-color: #ccc1d9">**定义（事件的关系）**</span>

| 关系 | 符号 | 含义 |
|------|------|------|
| 包含 | $A \subset B$ | $A$ 发生则 $B$ 必发生 |
| 相等 | $A = B$ | $A \subset B$ 且 $B \subset A$ |
| 和（并） | $A \cup B$ 或 $A + B$ | $A$ 或 $B$ 至少一个发生 |
| 积（交） | $A \cap B$ 或 $AB$ | $A$ 和 $B$ 都发生 |
| 差 | $A - B$ | $A$ 发生但 $B$ 不发生 |
| 对立（补） | $\bar{A}$ 或 $A^c$ | $A$ 不发生 |
| 互不相容（互斥） | $AB = \emptyset$ | $A$ 和 $B$ 不能同时发生 |

<span style="background-color: #8db3e2">**定理（事件的运算律）**</span>

1. **交换律**：$A \cup B = B \cup A$，$AB = BA$
2. **结合律**：$(A \cup B) \cup C = A \cup (B \cup C)$，$(AB)C = A(BC)$
3. **分配律**：$A(B \cup C) = AB \cup AC$，$A \cup BC = (A \cup B)(A \cup C)$
4. **对偶律（德摩根律）**：$\overline{A \cup B} = \bar{A}\bar{B}$，$\overline{AB} = \bar{A} \cup \bar{B}$

---

## 二、概率的定义与性质

### 2.1 概率的定义

<span style="background-color: #ccc1d9">**定义（概率的公理化定义）**</span> 设 $\Omega$ 为样本空间，若对于每个事件 $A$，都有一个实数 $P(A)$ 与之对应，且满足：

1. **非负性**：$P(A) \geq 0$
2. **规范性**：$P(\Omega) = 1$
3. **可列可加性**：若 $A_1, A_2, \cdots$ 互不相容，则 $P(A_1 \cup A_2 \cup \cdots) = P(A_1) + P(A_2) + \cdots$

则称 $P(A)$ 为事件 $A$ 的**概率**。

### 2.2 概率的基本性质

<span style="background-color: #8db3e2">**定理**</span> 概率具有以下性质：

1. $P(\emptyset) = 0$
2. 若 $A \subset B$，则 $P(A) \leq P(B)$
3. $0 \leq P(A) \leq 1$
4. $P(\bar{A}) = 1 - P(A)$
5. $P(A \cup B) = P(A) + P(B) - P(AB)$
6. 若 $A$ 和 $B$ 互斥，则 $P(A \cup B) = P(A) + P(B)$

<span style="background-color: #8db3e2">**定理（加法公式）**</span>

$$P(A_1 \cup A_2 \cup \cdots \cup A_n) = \sum_{i=1}^{n} P(A_i) - \sum_{i<j} P(A_iA_j) + \sum_{i<j<k} P(A_iA_jA_k) - \cdots + (-1)^{n-1} P(A_1A_2\cdots A_n)$$

---

## 三、古典概型

### 3.1 古典概型的定义

<span style="background-color: #ccc1d9">**定义（古典概型）**</span> 若随机试验满足：
1. 样本空间 $\Omega$ 只有有限个样本点
2. 每个样本点出现的可能性相等

则称为**古典概型**。

<span style="background-color: #8db3e2">**定理（古典概型的概率计算）**</span>

$$P(A) = \frac{A \text{中包含的样本点数}}{\Omega \text{中样本点总数}} = \frac{|A|}{|\Omega|}$$

### 3.2 排列与组合

<span style="background-color: #ccc1d9">**定义（排列）**</span> 从 $n$ 个不同元素中取出 $m$ 个（$m \leq n$）排成一列，称为**排列**，排列数为：

$$P_n^m = n(n-1)(n-2)\cdots(n-m+1) = \frac{n!}{(n-m)!}$$

<span style="background-color: #ccc1d9">**定义（组合）**</span> 从 $n$ 个不同元素中取出 $m$ 个（$m \leq n$）组成一组，称为**组合**，组合数为：

$$C_n^m = \binom{n}{m} = \frac{n!}{m!(n-m)!}$$

---

## 四、条件概率

### 4.1 条件概率的定义

<span style="background-color: #ccc1d9">**定义（条件概率）**</span> 设 $A$ 和 $B$ 为两个事件，$P(B) > 0$，则称

$$P(A|B) = \frac{P(AB)}{P(B)}$$

为**事件 $A$ 在事件 $B$ 发生条件下的条件概率**。

### 4.2 乘法公式

<span style="background-color: #8db3e2">**定理（乘法公式）**</span>

$$P(AB) = P(B)P(A|B) = P(A)P(B|A)$$

推广形式：

$$P(A_1A_2\cdots A_n) = P(A_1)P(A_2|A_1)P(A_3|A_1A_2)\cdots P(A_n|A_1A_2\cdots A_{n-1})$$

---

## 五、全概率公式与贝叶斯公式

### 5.1 全概率公式

<span style="background-color: #ccc1d9">**定义（完备事件组）**</span> 若事件组 $B_1, B_2, \cdots, B_n$ 满足：
1. $B_1, B_2, \cdots, B_n$ 互不相容
2. $B_1 \cup B_2 \cup \cdots \cup B_n = \Omega$

则称 $B_1, B_2, \cdots, B_n$ 为**完备事件组**。

<span style="background-color: #8db3e2">**定理（全概率公式）**</span> 若 $B_1, B_2, \cdots, B_n$ 为完备事件组，且 $P(B_i) > 0$，则对于任意事件 $A$：

$$P(A) = \sum_{i=1}^{n} P(B_i)P(A|B_i)$$

### 5.2 贝叶斯公式

<span style="background-color: #8db3e2">**定理（贝叶斯公式）**</span> 若 $B_1, B_2, \cdots, B_n$ 为完备事件组，且 $P(B_i) > 0$，$P(A) > 0$，则：

$$P(B_i|A) = \frac{P(B_i)P(A|B_i)}{\sum_{j=1}^{n} P(B_j)P(A|B_j)}$$

---

## 六、事件的独立性

### 6.1 独立性的定义

<span style="background-color: #ccc1d9">**定义（独立性）**</span> 若事件 $A$ 和 $B$ 满足

$$P(AB) = P(A)P(B)$$

则称 $A$ 和 $B$ **相互独立**。

<span style="background-color: #8db3e2">**定理**</span> 若 $A$ 和 $B$ 相互独立，则：
- $A$ 和 $\bar{B}$ 相互独立
- $\bar{A}$ 和 $B$ 相互独立
- $\bar{A}$ 和 $\bar{B}$ 相互独立

### 6.2 多个事件的独立性

<span style="background-color: #ccc1d9">**定义（n个事件的独立性）**</span> 若 $n$ 个事件 $A_1, A_2, \cdots, A_n$ 满足：

$$P(A_iA_j) = P(A_i)P(A_j) \quad (i \neq j)$$

$$P(A_iA_jA_k) = P(A_i)P(A_j)P(A_k) \quad (i \neq j \neq k)$$

$$\cdots$$

$$P(A_1A_2\cdots A_n) = P(A_1)P(A_2)\cdots P(A_n)$$

则称 $A_1, A_2, \cdots, A_n$ **相互独立**。

<span style="background-color: #ccc1d9">**定义（两两独立）**</span> 若 $n$ 个事件 $A_1, A_2, \cdots, A_n$ 仅满足

$$P(A_iA_j) = P(A_i)P(A_j) \quad (i \neq j)$$

则称 $A_1, A_2, \cdots, A_n$ **两两独立**。

**注意**：相互独立 $\Rightarrow$ 两两独立，但两两独立 $\not\Rightarrow$ 相互独立。

---

## 七、典型例题

### 例题1：概率的基本计算

**题目**：已知事件 $A$ 和 $B$ 仅发生一个的概率为 0.3，且 $P(A) + P(B) = 0.5$，求 $A$ 和 $B$ 至少有一个不发生的概率。

**思路**：利用概率的基本公式，分析事件关系。

**解答**：
"仅发生一个"即 $A\bar{B} \cup \bar{A}B$

$P(A\bar{B} \cup \bar{A}B) = P(A\bar{B}) + P(\bar{A}B) = P(A) - P(AB) + P(B) - P(AB) = P(A) + P(B) - 2P(AB) = 0.3$

所以 $P(A) + P(B) - 2P(AB) = 0.3$

由 $P(A) + P(B) = 0.5$，得 $0.5 - 2P(AB) = 0.3$

$P(AB) = 0.1$

"至少有一个不发生"即 $\bar{A} \cup \bar{B} = \overline{AB}$

$P(\bar{A} \cup \bar{B}) = 1 - P(AB) = 1 - 0.1 = 0.9$

**总结**：注意事件的对立关系，$\bar{A} \cup \bar{B} = \overline{AB}$。

---

### 例题2：概率的取值范围

**题目**：对事件 $A$ 和 $B$，已知 $P(A) = 0.6$, $P(B) = 0.7$，求 $P(AB)$ 和 $P(A \cup B)$ 的可能取值范围。

**思路**：利用概率的基本性质确定取值范围。

**解答**：
$P(AB)$ 的范围：
- 最大值：当 $A \subset B$ 时，$P(AB) = P(A) = 0.6$
- 最小值：由 $P(A \cup B) \leq 1$，$P(A) + P(B) - P(AB) \leq 1$，得 $P(AB) \geq P(A) + P(B) - 1 = 0.3$

所以 $0.3 \leq P(AB) \leq 0.6$

$P(A \cup B)$ 的范围：
- 最大值：$P(A \cup B) \leq 1$
- 最小值：当 $A \subset B$ 时，$P(A \cup B) = P(B) = 0.7$

所以 $0.7 \leq P(A \cup B) \leq 1$

**总结**：概率取值范围的关键是分析事件之间的包含关系。

---

### 例题3：条件概率的应用

**题目**：设 $A$ 和 $B$ 为随机事件，已知 $P(A) = \frac{1}{4}$, $P(A|B) = \frac{1}{2}$, $P(B|A) = \frac{1}{3}$，求 $P(A \cup B)$。

**思路**：利用条件概率和乘法公式。

**解答**：
由 $P(A|B) = \frac{P(AB)}{P(B)} = \frac{1}{2}$，得 $P(AB) = \frac{1}{2}P(B)$

由 $P(B|A) = \frac{P(AB)}{P(A)} = \frac{1}{3}$，得 $P(AB) = \frac{1}{3}P(A) = \frac{1}{3} \times \frac{1}{4} = \frac{1}{12}$

所以 $\frac{1}{2}P(B) = \frac{1}{12}$，$P(B) = \frac{1}{6}$

$P(A \cup B) = P(A) + P(B) - P(AB) = \frac{1}{4} + \frac{1}{6} - \frac{1}{12} = \frac{3}{12} + \frac{2}{12} - \frac{1}{12} = \frac{4}{12} = \frac{1}{3}$

**总结**：条件概率公式 $P(A|B) = \frac{P(AB)}{P(B)}$ 是解题的关键。

---

### 例题4：独立性的应用

**题目**：独立地将一枚均匀硬币重复掷5次，求正、反面都至少出现2次的概率。

**思路**：利用独立性，分析可能情况。

**解答**：
设正面出现次数为 $X$，则 $X \sim B(5, \frac{1}{2})$

"正、反面都至少出现2次"即 $2 \leq X \leq 3$

$P(X = 2) = C_5^2 \left(\frac{1}{2}\right)^5 = \frac{10}{32} = \frac{5}{16}$

$P(X = 3) = C_5^3 \left(\frac{1}{2}\right)^5 = \frac{10}{32} = \frac{5}{16}$

$P(2 \leq X \leq 3) = \frac{5}{16} + \frac{5}{16} = \frac{10}{16} = \frac{5}{8}$

**总结**：独立重复试验可用二项分布模型。

---

### 例题5：全概率公式

**题目**：已知甲袋有3个白球、6个黑球，乙袋有5个白球、4个黑球。先从甲袋中任取一球放入乙袋，然后再从乙袋中任取一球放回甲袋，求甲袋中白球数不变的概率。

**思路**：利用全概率公式，分析两种情况。

**解答**：
设 $A$ 为"从甲袋取白球"，$B$ 为"从甲袋取黑球"

$P(A) = \frac{3}{9} = \frac{1}{3}$，$P(B) = \frac{6}{9} = \frac{2}{3}$

甲袋白球数不变有两种情况：
1. 从甲袋取白球放入乙袋，再从乙袋取白球放回甲袋
2. 从甲袋取黑球放入乙袋，再从乙袋取黑球放回甲袋

情况1：$P_1 = P(A) \times \frac{6}{10} = \frac{1}{3} \times \frac{6}{10} = \frac{6}{30} = \frac{1}{5}$

情况2：$P_2 = P(B) \times \frac{5}{10} = \frac{2}{3} \times \frac{5}{10} = \frac{10}{30} = \frac{1}{3}$

总概率：$P = P_1 + P_2 = \frac{1}{5} + \frac{1}{3} = \frac{3}{15} + \frac{5}{15} = \frac{8}{15}$

**总结**：分步骤的概率问题，可用全概率公式分解。

---

## 八、解题方法总结

### 8.1 概率计算的主要方法

| 类型 | 方法 |
|------|------|
| 古典概型 | 计数原理、排列组合 |
| 条件概率 | 条件概率公式、乘法公式 |
| 复合事件 | 加法公式、对偶律 |
| 分步骤事件 | 全概率公式 |
| 后验概率 | 贝叶斯公式 |
| 独立事件 | 概率乘法 |

### 8.2 常见易错点

1. **互斥与独立的区别**：互斥是 $AB = \emptyset$，独立是 $P(AB) = P(A)P(B)$
2. **条件概率公式**：$P(A|B) = \frac{P(AB)}{P(B)}$，注意 $P(B) > 0$
3. **对立事件**：$P(\bar{A}) = 1 - P(A)$，不是 $P(\bar{A}) = P(\text{其他})$
4. **德摩根律**：$\overline{A \cup B} = \bar{A}\bar{B}$，$\overline{AB} = \bar{A} \cup \bar{B}$

---

## 九、练习题精选

### 基础练习

1. 已知 $P(A \cup B) = \frac{3}{5}$, $P(\bar{A} \cup B) = \frac{9}{10}$，求 $P(B)$。

2. 设随机事件 $A$ 和 $B$ 满足 $A \subset C$, $P(B) = P(C) = \frac{1}{3}$，且 $B$ 和 $C$ 相互独立，求 $P(A \cup B|\bar{C})$。

3. 随机地抛掷甲、乙两个均匀骰子，求甲骰子出现的点数大于乙骰子出现的点数的概率。

### 提高练习

4. 一射手对同一目标独立地进行四次射击。若至少命中一次的概率为 $\frac{15}{16}$，求该射手对同一目标独立地进行四次射击中至少没命中一次的概率。

5. 已知人群中血型为 A、B、O、AB 型的人占比分别为 $a, b, c, d$（$a + b + c + d = 1$）。O 型血为"万能输血者"，AB 型为"万能受血者"，其他情况则只有同型才能输血。现从人群中任选1人为输血者，再任选另1人为受血者，求输血配对成功的概率。

---

## 参考答案提示

1. $P(B) = \frac{1}{2}$（提示：$P(\bar{A} \cup B) = P(\bar{A}) + P(B) - P(\bar{A}B)$）

2. $P(A \cup B|\bar{C}) = P(A|\bar{C}) + P(B|\bar{C})$（提示：利用条件概率和独立性）

3. $\frac{5}{12}$（提示：枚举所有36种情况，甲>乙的有15种）

4. $\frac{15}{16}$（提示：设命中概率为 $p$，由 $1 - (1-p)^4 = \frac{15}{16}$ 求 $p$）

5. $c + d + a^2 + b^2$（提示：万能输血者+万能受血者+同型配对）

---

> **注**：本 Lecture 内容涵盖随机事件、概率定义、条件概率、独立性及典型例题。建议结合《基础过关660题》第511-520题进行练习巩固。