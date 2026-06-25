---
title: "Lecture 34：定积分的应用"
chapter: "05-定积分及反常积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 定积分应用, 面积, 旋转体体积, 弧长]
difficulty: ★★★★☆
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 34：定积分的应用

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，解答题高频考点） |
| **分值分布** | 约 10-12 分（解答题 1 题） |
| **题型** | 求面积、旋转体体积、弧长、侧面积 |
| **难度** | 中等（公式要熟，画图很关键） |

---

## 一、元素法（微元法）

> 若所求量 $U$ 满足以下条件：
> 1. $U$ 与变量 $x$ 的变化区间 $[a, b]$ 有关
> 2. $U$ 对区间具有**可加性**（即整体 = 部分之和）
> 3. 在 $[x, x+\mathrm{d}x]$ 上的部分量 $\Delta U \approx f(x)\,\mathrm{d}x$
>
> 则：$U = \displaystyle\int_a^b f(x)\,\mathrm{d}x$
>
> 其中 $f(x)\,\mathrm{d}x$ 称为所求量的**元素**（微元）。

**步骤**：选取变量 → 取微元 → 求积分

---

## 二、平面图形的面积

### 直角坐标下的面积

>
> **情形 1：由 $y = f(x)$，$y = g(x)$，$x = a$，$x = b$ 围成（$f(x) \ge g(x)$）**：
>
> $$\boxed{S = \int_a^b [f(x) - g(x)]\,\mathrm{d}x}$$
>
> **情形 2：由 $x = \varphi(y)$，$x = \psi(y)$，$y = c$，$y = d$ 围成（$\varphi(y) \ge \psi(y)$）**：
>
> $$\boxed{S = \int_c^d [\varphi(y) - \psi(y)]\,\mathrm{d}y}$$

> 求面积一定要先**画图**，确定交点、上下位置关系、积分变量的选择。

### 参数方程下的面积

> 若曲线由参数方程 $x = x(t)$，$y = y(t)$ 给出，$t \in [\alpha, \beta]$：
>
> $$S = \int_\alpha^\beta y(t)\cdot x'(t)\,\mathrm{d}t \quad \text{（注意绝对值）}$$

### 极坐标下的面积

> 由 $r = r(\theta)$，$\theta = \alpha$，$\theta = \beta$ 围成的扇形面积：
>
> $$\boxed{S = \frac{1}{2}\int_\alpha^\beta r^2(\theta)\,\mathrm{d}\theta}$$
>
> 两条极坐标曲线 $r_1(\theta)$ 与 $r_2(\theta)$ 之间的面积（$r_1 \ge r_2$）：
>
> $$S = \frac{1}{2}\int_\alpha^\beta [r_1^2(\theta) - r_2^2(\theta)]\,\mathrm{d}\theta$$

---

## 三、旋转体的体积

### 绕 $x$ 轴旋转

> 曲线 $y = f(x)$（$f(x) \ge 0$），$x \in [a, b]$，绕 $x$ 轴旋转一周所得旋转体体积：
>
> $$\boxed{V_x = \pi\int_a^b [f(x)]^2\,\mathrm{d}x = \pi\int_a^b y^2\,\mathrm{d}x}$$
>
> **几何理解**：每个截面是半径为 $|f(x)|$ 的圆，面积为 $\pi y^2$，沿 $x$ 轴积分。

### 绕 $y$ 轴旋转

>
> **方法 1（壳层法/柱壳法）**：曲线 $y = f(x)$（$f(x) \ge 0$），$x \in [a, b]$（$0 \le a < b$），绕 $y$ 轴旋转：
>
> $$\boxed{V_y = 2\pi\int_a^b x|f(x)|\,\mathrm{d}x}$$
>
> **方法 2（切片法）**：若能表示为 $x = g(y)$，$y \in [c, d]$，绕 $y$ 轴旋转：
>
> $$V_y = \pi\int_c^d [g(y)]^2\,\mathrm{d}y$$

### 绕任意轴旋转

> 绕 $y = k$ 旋转的体积：$V = \pi\int_a^b [f(x) - k]^2\,\mathrm{d}x$
>
> 绕 $x = k$ 旋转的体积（壳层法）：$V = 2\pi\int_a^b |x - k|\cdot|f(x)|\,\mathrm{d}x$

---

## 四、弧长

>
> **直角坐标**：$y = f(x)$，$x \in [a, b]$：
>
> $$\boxed{l = \int_a^b\sqrt{1 + [f'(x)]^2}\,\mathrm{d}x = \int_a^b\sqrt{1 + (y')^2}\,\mathrm{d}x}$$
>
> **参数方程**：$x = x(t)$，$y = y(t)$，$t \in [\alpha, \beta]$：
>
> $$\boxed{l = \int_\alpha^\beta\sqrt{[x'(t)]^2 + [y'(t)]^2}\,\mathrm{d}t}$$
>
> **极坐标**：$r = r(\theta)$，$\theta \in [\alpha, \beta]$：
>
> $$\boxed{l = \int_\alpha^\beta\sqrt{r^2(\theta) + [r'(\theta)]^2}\,\mathrm{d}\theta}$$

> $\mathrm{d}s = \sqrt{(\mathrm{d}x)^2 + (\mathrm{d}y)^2}$，即"勾股定理"的微分形式

---

## 五、旋转体的侧面积

> 曲线 $y = f(x)$（$f(x) \ge 0$），$x \in [a, b]$，绕 $x$ 轴旋转所得侧面积：
>
> $$\boxed{S_{\text{侧}} = 2\pi\int_a^b |y|\sqrt{1 + (y')^2}\,\mathrm{d}x = 2\pi\int_a^b |f(x)|\sqrt{1 + [f'(x)]^2}\,\mathrm{d}x}$$
>
> **参数方程形式**：
> $$S_{\text{侧}} = 2\pi\int_\alpha^\beta |y(t)|\sqrt{[x'(t)]^2 + [y'(t)]^2}\,\mathrm{d}t$$
>
> **极坐标形式**：
> $$S_{\text{侧}} = 2\pi\int_\alpha^\beta r(\theta)\sin\theta\sqrt{r^2(\theta) + [r'(\theta)]^2}\,\mathrm{d}\theta$$

> $S = \int 2\pi \cdot (\text{旋转半径}) \cdot \mathrm{d}s$

---

## 六、公式总结对比表

| 求什么 | 绕 $x$ 轴 | 绕 $y$ 轴 |
|--------|-----------|-----------|
| **体积** | $\pi\int y^2\mathrm{d}x$（切片法） | $2\pi\int xy\,\mathrm{d}x$（壳层法）或 $\pi\int x^2\mathrm{d}y$（切片法） |
| **侧面积** | $2\pi\int |y|\sqrt{1+y'^2}\mathrm{d}x$ | $2\pi\int |x|\sqrt{1+y'^2}\mathrm{d}x$ |
| **弧长** | $\int\sqrt{1+y'^2}\mathrm{d}x$（与旋转轴无关） | 同左 |

---

## 七、典型例题

### 例 1：直角坐标下的面积

**题目**：求曲线 $y = x^2$ 与 $y = 2x$ 围成的面积。

**解**：

联立 $x^2 = 2x$，得 $x = 0$，$x = 2$。

在 $[0, 2]$ 上 $2x \ge x^2$，故：

$$S = \int_0^2 (2x - x^2)\,\mathrm{d}x = \left[x^2 - \frac{x^3}{3}\right]_0^2 = 4 - \frac{8}{3} = \frac{4}{3}$$

$$\boxed{S = \frac{4}{3}}$$

---

### 例 2：旋转体体积

**题目**：求 $y = \sin x$（$0 \le x \le \pi$）绕 $x$ 轴旋转所得体积。

**解**：

$$V_x = \pi\int_0^{\pi}\sin^2 x\,\mathrm{d}x = \pi\int_0^{\pi}\frac{1 - \cos 2x}{2}\,\mathrm{d}x = \pi\cdot\frac{\pi}{2} = \frac{\pi^2}{2}$$

$$\boxed{V_x = \frac{\pi^2}{2}}$$

---

### 例 3：绕 $y$ 轴旋转（壳层法）

**题目**：求 $y = x^2$（$0 \le x \le 1$）绕 $y$ 轴旋转所得体积。

**解**：

用壳层法：

$$V_y = 2\pi\int_0^1 x\cdot x^2\,\mathrm{d}x = 2\pi\int_0^1 x^3\,\mathrm{d}x = 2\pi\cdot\frac{1}{4} = \frac{\pi}{2}$$

验证（切片法）：$x = \sqrt{y}$，$y \in [0, 1]$

$$V_y = \pi\int_0^1 (\sqrt{y})^2\,\mathrm{d}y = \pi\int_0^1 y\,\mathrm{d}y = \frac{\pi}{2} \quad \checkmark$$

$$\boxed{V_y = \frac{\pi}{2}}$$

---

### 例 4：弧长

**题目**：求 $y = \frac{2}{3}x^{3/2}$ 在 $[0, 1]$ 上的弧长。

**解**：

$y' = x^{1/2} = \sqrt{x}$

$$l = \int_0^1\sqrt{1 + x}\,\mathrm{d}x = \frac{2}{3}(1+x)^{3/2}\Big|_0^1 = \frac{2}{3}(2\sqrt{2} - 1)$$

$$\boxed{l = \frac{2}{3}(2\sqrt{2} - 1)}$$

---

### 例 5：旋转体侧面积

**题目**：求 $y = \sqrt{x}$（$0 \le x \le 2$）绕 $x$ 轴旋转所得侧面积。

**解**：

$y' = \frac{1}{2\sqrt{x}}$，$1 + (y')^2 = 1 + \frac{1}{4x} = \frac{4x + 1}{4x}$

$$S = 2\pi\int_0^2 \sqrt{x}\cdot\sqrt{\frac{4x+1}{4x}}\,\mathrm{d}x = 2\pi\int_0^2 \sqrt{x}\cdot\frac{\sqrt{4x+1}}{2\sqrt{x}}\,\mathrm{d}x = \pi\int_0^2\sqrt{4x+1}\,\mathrm{d}x$$

令 $u = 4x + 1$，$\mathrm{d}x = \frac{\mathrm{d}u}{4}$：

$$S = \pi\int_1^9 \sqrt{u}\cdot\frac{\mathrm{d}u}{4} = \frac{\pi}{4}\cdot\frac{2}{3}u^{3/2}\Big|_1^9 = \frac{\pi}{6}(27 - 1) = \frac{13\pi}{3}$$

$$\boxed{S = \frac{13\pi}{3}}$$

---

### 例 6：极坐标下的面积

**题目**：求心形线 $r = 1 + \cos\theta$ 围成的面积。

**解**：

$$S = \frac{1}{2}\int_0^{2\pi}(1 + \cos\theta)^2\,\mathrm{d}\theta = \frac{1}{2}\int_0^{2\pi}(1 + 2\cos\theta + \cos^2\theta)\,\mathrm{d}\theta$$

$$= \frac{1}{2}\int_0^{2\pi}\left(1 + 2\cos\theta + \frac{1 + \cos 2\theta}{2}\right)\mathrm{d}\theta$$

$$= \frac{1}{2}\int_0^{2\pi}\left(\frac{3}{2} + 2\cos\theta + \frac{\cos 2\theta}{2}\right)\mathrm{d}\theta$$

$$= \frac{1}{2}\left[\frac{3}{2}\theta + 2\sin\theta + \frac{\sin 2\theta}{4}\right]_0^{2\pi} = \frac{1}{2}\cdot 3\pi = \frac{3\pi}{2}$$

$$\boxed{S = \frac{3\pi}{2}}$$

---

## 📝 总结

| 应用 | 核心公式 | 关键步骤 |
|------|----------|----------|
| **面积** | $\int[f(x)-g(x)]\mathrm{d}x$ | 画图、找交点、确定上下 |
| **体积（绕 $x$ 轴）** | $\pi\int y^2\mathrm{d}x$ | 确定截面半径 |
| **体积（绕 $y$ 轴）** | $2\pi\int xy\,\mathrm{d}x$ 或 $\pi\int x^2\mathrm{d}y$ | 壳层法或切片法 |
| **弧长** | $\int\sqrt{1+y'^2}\mathrm{d}x$ | 弧长微元 = 勾股定理微分 |
| **侧面积** | $2\pi\int|y|\sqrt{1+y'^2}\mathrm{d}x$ | 侧面积 = 弧长 × 旋转半径 × $2\pi$ |

> 1. 求面积时**一定要画图**，确定被积函数是"上减下"还是"右减左"
> 2. 旋转体体积的壳层法和切片法**选择取决于积分变量**
> 3. 弧长公式中是 $\sqrt{1 + (y')^2}$，**不是** $\sqrt{1 + y'}$
> 4. 极坐标面积公式是 $\frac{1}{2}\int r^2\mathrm{d}\theta$，**不要忘记** $\frac{1}{2}$
> 5. 侧面积与体积的公式**不能混淆**（侧面积有 $\sqrt{1+y'^2}$ 因子）

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 31：定积分的基本概念]] — 定积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 32：定积分的计算：积分上限的函数]] — 计算
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 44：二重积分]] — 二重积分
