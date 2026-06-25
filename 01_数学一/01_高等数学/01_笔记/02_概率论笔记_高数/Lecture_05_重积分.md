---
title: Lecture 05 - 重积分
subject: 高等数学
chapter: 第六章
lecture: 05
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 05: 重积分

## 一、二重积分的概念与性质

### 1.1 二重积分的定义

<span style="background-color: #ccc1d9">**定义（二重积分）**</span> 设 $f(x,y)$ 是有界闭区域 $D$ 上的有界函数，将区域 $D$ 任意分成 $n$ 个小区域 $\Delta \sigma_1, \Delta \sigma_2, \ldots, \Delta \sigma_n$，在每个小区域 $\Delta \sigma_i$ 上任取一点 $(\xi_i, \eta_i)$，作和

$$S = \sum_{i=1}^{n} f(\xi_i, \eta_i) \Delta \sigma_i$$

若当各小区域的直径最大值 $\lambda \to 0$ 时，这个和的极限存在，且与分法及取点法无关，则称此极限为函数 $f(x,y)$ 在区域 $D$ 上的**二重积分**，记作

$$\iint_D f(x,y) \, d\sigma = \lim_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i, \eta_i) \Delta \sigma_i$$

### 1.2 二重积分的几何意义

二重积分 $\iint_D f(x,y) \, d\sigma$ 表示以曲面 $z = f(x,y)$ 为顶、以区域 $D$ 为底的曲顶柱体的体积。

当 $f(x,y) \geq 0$ 时，二重积分表示体积；当 $f(x,y) \leq 0$ 时，二重积分表示体积的负值。

### 1.3 二重积分的性质

<span style="background-color: #8db3e2">**定理（线性运算）**</span>
$$\iint_D [kf(x,y) + mg(x,y)] \, d\sigma = k\iint_D f(x,y) \, d\sigma + m\iint_D g(x,y) \, d\sigma$$

<span style="background-color: #8db3e2">**定理（区域可加性）**</span> 若 $D = D_1 \cup D_2$，$D_1 \cap D_2 = \varnothing$，则

$$\iint_D f(x,y) \, d\sigma = \iint_{D_1} f(x,y) \, d\sigma + \iint_{D_2} f(x,y) \, d\sigma$$

<span style="background-color: #8db3e2">**定理（保号性）**</span> 若在 $D$ 上 $f(x,y) \leq g(x,y)$，则

$$\iint_D f(x,y) \, d\sigma \leq \iint_D g(x,y) \, d\sigma$$

<span style="background-color: #8db3e2">**定理（估值定理）**</span> 若 $m \leq f(x,y) \leq M$，则

$$m \cdot S_D \leq \iint_D f(x,y) \, d\sigma \leq M \cdot S_D$$

其中 $S_D$ 为区域 $D$ 的面积。

<span style="background-color: #8db3e2">**定理（积分中值定理）**</span> 若 $f(x,y)$ 在有界闭区域 $D$ 上连续，则存在 $(\xi,\eta) \in D$，使得

$$\iint_D f(x,y) \, d\sigma = f(\xi,\eta) \cdot S_D$$

---

## 二、二重积分的计算

### 2.1 直角坐标计算

**X-型区域**：区域 $D$ 由 $x = a$，$x = b$，$y = \varphi_1(x)$，$y = \varphi_2(x)$ 围成（$\varphi_1(x) \leq \varphi_2(x)$）。

$$\iint_D f(x,y) \, d\sigma = \int_a^b \left[\int_{\varphi_1(x)}^{\varphi_2(x)} f(x,y) \, dy\right] dx = \int_a^b \, dx \int_{\varphi_1(x)}^{\varphi_2(x)} f(x,y) \, dy$$

**Y-型区域**：区域 $D$ 由 $y = c$，$y = d$，$x = \psi_1(y)$，$x = \psi_2(y)$ 围成（$\psi_1(y) \leq \psi_2(y)$）。

$$\iint_D f(x,y) \, d\sigma = \int_c^d \left[\int_{\psi_1(y)}^{\psi_2(y)} f(x,y) \, dx\right] dy = \int_c^d \, dy \int_{\psi_1(y)}^{\psi_2(y)} f(x,y) \, dx$$

### 2.2 极坐标计算

<span style="background-color: #ccc1d9">**定义（极坐标）**</span> 点 $(x,y)$ 的极坐标表示为 $x = r\cos\theta$，$y = r\sin\theta$，面积元素 $d\sigma = r \, dr \, d\theta$。

**极坐标下的二重积分**：
$$\iint_D f(x,y) \, d\sigma = \iint_D f(r\cos\theta, r\sin\theta) \cdot r \, dr \, d\theta$$

**适用情形**：
1. 区域边界由极坐标方程表示
2. 被积函数形式为 $f(x^2+y^2)$、$f(x/y)$、$f(y/x)$
3. 区域为圆域、圆环域或部分圆域

**积分次序选择原则**：
- 先 $r$ 后 $\theta$：适用于边界由 $r = r(\theta)$ 描述的区域
- 若 $\theta$ 的范围易确定，且对每个 $\theta$，$r$ 的下限和上限是 $\theta$ 的函数

### 2.3 交换积分次序

交换积分次序是计算二重积分的重要技巧：
1. 由累次积分画出区域 $D$
2. 根据区域 $D$ 确定新的积分次序和积分限

---

## 三、三重积分的概念

### 3.1 三重积分的定义

<span style="background-color: #ccc1d9">**定义（三重积分）**</span> 设 $f(x,y,z)$ 是空间有界闭区域 $\Omega$ 上的有界函数，将 $\Omega$ 任意分成 $n$ 个小区域 $\Delta v_1, \Delta v_2, \ldots, \Delta v_n$，在每个小区域上任取一点 $(\xi_i, \eta_i, \zeta_i)$，作和

$$S = \sum_{i=1}^{n} f(\xi_i, \eta_i, \zeta_i) \Delta v_i$$

若当各小区域直径最大值 $\lambda \to 0$ 时，这个和的极限存在，则称此极限为 $f(x,y,z)$ 在 $\Omega$ 上的**三重积分**，记作

$$\iiint_\Omega f(x,y,z) \, dv = \lim_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i, \eta_i, \zeta_i) \Delta v_i$$

### 3.2 三重积分的物理意义

三重积分 $\iiint_\Omega f(x,y,z) \, dv$ 可以表示：
- 当 $f(x,y,z)$ 为密度函数时，表示空间物体 $\Omega$ 的质量
- 当 $f(x,y,z) = 1$ 时，表示物体 $\Omega$ 的体积

---

## 四、三重积分的计算

### 4.1 直角坐标计算

**投影法（先一后二）**：将 $\Omega$ 投影到 $xy$ 平面得区域 $D_{xy}$，对每个 $(x,y) \in D_{xy}$，$z$ 的范围为 $z_1(x,y) \leq z \leq z_2(x,y)$，则

$$\iiint_\Omega f(x,y,z) \, dv = \iint_{D_{xy}} \left[\int_{z_1(x,y)}^{z_2(x,y)} f(x,y,z) \, dz\right] d\sigma$$

**截面法（先二后一）**：用平面 $z = z_0$ 截 $\Omega$ 得区域 $D_z$，则

$$\iiint_\Omega f(x,y,z) \, dv = \int_{z_1}^{z_2} \left[\iint_{D_z} f(x,y,z) \, d\sigma\right] dz$$

### 4.2 柱面坐标计算

<span style="background-color: #ccc1d9">**定义（柱面坐标）**</span> 空间点 $(x,y,z)$ 的柱面坐标为 $(r,\theta,z)$，其中
$$x = r\cos\theta, \quad y = r\sin\theta, \quad z = z$$

体积元素 $dv = r \, dr \, d\theta \, dz$。

**适用情形**：
1. 积分区域在 $xy$ 平面的投影是圆域或圆环域
2. 被积函数含有 $x^2+y^2$ 或 $f(x^2+y^2)$

### 4.3 球面坐标计算

<span style="background-color: #ccc1d9">**定义（球面坐标）**</span> 空间点 $(x,y,z)$ 的球面坐标为 $(r,\varphi,\theta)$，其中
$$x = r\sin\varphi\cos\theta, \quad y = r\sin\varphi\sin\theta, \quad z = r\cos\varphi$$

体积元素 $dv = r^2\sin\varphi \, dr \, d\varphi \, d\theta$。

**适用情形**：
1. 积分区域是球形或球壳
2. 被积函数含有 $x^2+y^2+z^2$

**$\varphi$ 的范围**：$\varphi$ 是与 $z$ 轴正方向的夹角，$0 \leq \varphi \leq \pi$。

---

## 五、重积分的应用

### 5.1 体积

<span style="background-color: #8db3e2">**定理**</span> 空间区域 $\Omega$ 的体积为

$$V = \iiint_\Omega 1 \, dv$$

### 5.2 质量

若空间物体 $\Omega$ 的密度函数为 $\rho(x,y,z)$，则物体质量为

$$m = \iiint_\Omega \rho(x,y,z) \, dv$$

### 5.3 重心

<span style="background-color: #ccc1d9">**定义（重心）**</span> 物体的重心坐标 $(\bar{x}, \bar{y}, \bar{z})$ 为

$$\bar{x} = \frac{\iiint_\Omega x\rho(x,y,z) \, dv}{m}, \quad \bar{y} = \frac{\iiint_\Omega y\rho(x,y,z) \, dv}{m}, \quad \bar{z} = \frac{\iiint_\Omega z\rho(x,y,z) \, dv}{m}$$

### 5.4 转动惯量

<span style="background-color: #ccc1d9">**定义（转动惯量）**</span> 物体关于 $x$ 轴的转动惯量为

$$I_x = \iiint_\Omega (y^2+z^2)\rho(x,y,z) \, dv$$

类似地有 $I_y$，$I_z$。

---

## 六、典型例题

### 例题1：交换积分次序

**题目**（660题104）：交换积分次序 $\int_0^1 \, dx \int_0^{x^2} f(x,y) \, dy + \int_1^3 \, dx \int_0^{\frac{1}{2}(3-x)} f(x,y) \, dy$。

**思路**：根据积分上下限画出区域 $D$，确定新的积分次序。

**解答**：
第一个积分区域 $D_1$：$0 \leq x \leq 1$，$0 \leq y \leq x^2$
第二个积分区域 $D_2$：$1 \leq x \leq 3$，$0 \leq y \leq \frac{1}{2}(3-x)$

由 $y = x^2$ 得 $x = \sqrt{y}$，由 $y = \frac{1}{2}(3-x)$ 得 $x = 3 - 2y$

合并区域 $D = D_1 \cup D_2$，可表示为 $0 \leq y \leq 1$，$\sqrt{y} \leq x \leq 3 - 2y$（需验证交点）

交换次序得：
$$\int_0^1 \, dy \int_{\sqrt{y}}^{3-2y} f(x,y) \, dx$$

**总结**：交换积分次序的关键是根据原积分限正确画出区域 $D$。

---

### 例题2：极坐标计算二重积分

**题目**（660题107）：设 $D$ 为圆域 $x^2+y^2 \leq 2x+2y$，则 $\iint_D xy \, d\sigma$。

**思路**：将圆域化为标准形式，用极坐标计算。

**解答**：
圆 $x^2+y^2 = 2x+2y$ 化为 $(x-1)^2 + (y-1)^2 = 2$

在极坐标中 $x = r\cos\theta$，$y = r\sin\theta$，圆方程化为 $r = 2(\cos\theta + \sin\theta)$

由 $r \geq 0$ 得 $\cos\theta + \sin\theta \geq 0$，即 $\theta \in [-\frac{\pi}{4}, \frac{3\pi}{4}]$

$$\iint_D xy \, d\sigma = \int_{-\pi/4}^{3\pi/4} \int_0^{2(\cos\theta+\sin\theta)} r\cos\theta \cdot r\sin\theta \cdot r \, dr \, d\theta$$

$$= \int_{-\pi/4}^{3\pi/4} \cos\theta\sin\theta \cdot \frac{r^4}{4}\bigg|_0^{2(\cos\theta+\sin\theta)} d\theta$$

$$= 4\int_{-\pi/4}^{3\pi/4} \cos\theta\sin\theta(\cos\theta+\sin\theta)^4 d\theta$$

利用对称性化简计算。

**总结**：极坐标计算时注意积分区域的极坐标表示和极角的取值范围。

---

### 例题3：三重积分计算

**题目**（660题113）：计算 $\int_0^{\sqrt[4]{\theta}} \, d\theta \int_0^{\cos\theta} r^2 \, dr + \int_1^{\sqrt[3]{z}} \, dx \int_0^{\sqrt[3]{z-x}} \sqrt{x^2+y^2} \, dy$。

**思路**：这是两个累次积分的和，需要分别计算。

**解答**：
第一项：$\int_0^{\sqrt[4]{\theta}} \, d\theta \int_0^{\cos\theta} r^2 \, dr = \int_0^{\sqrt[4]{\theta}} \frac{r^3}{3}\bigg|_0^{\cos\theta} d\theta = \frac{1}{3}\int_0^{\sqrt[4]{\theta}} \cos^3\theta \, d\theta$

第二项需要仔细分析积分区域后计算。

**总结**：复杂的累次积分需先确定积分区域，再选择合适的坐标系。

---

### 例题4：三重积分的截面法

**题目**：计算 $\iiint_\Omega z \, dv$，其中 $\Omega$ 由平面 $z = 1$，$z = 2$ 及锥面 $z = \sqrt{x^2+y^2}$ 围成。

**思路**：用截面法（先二后一）计算。

**解答**：
用平面 $z = z_0$（$1 \leq z_0 \leq 2$）截立体，截面为圆域 $x^2+y^2 \leq z_0^2$，面积 $S(z_0) = \pi z_0^2$

$$\iiint_\Omega z \, dv = \int_1^2 z \cdot S(z) \, dz = \int_1^2 z \cdot \pi z^2 \, dz = \pi\int_1^2 z^3 \, dz = \pi\cdot\frac{z^4}{4}\bigg|_1^2 = \frac{15\pi}{4}$$

**总结**：当被积函数仅是 $z$ 的函数，且截面面积易表示时，截面法比投影法更方便。

---

### 例题5：对称性应用

**题目**（660题108）：$\iint_{x^2+y^2 \leq 1} (x^2+2y) \, d\sigma$。

**思路**：利用区域对称性和函数奇偶性。

**解答**：
区域 $D: x^2+y^2 \leq 1$ 关于 $y$ 轴对称。

对于 $x^2$ 项：$x^2$ 是偶函数，在对称区域上积分 $\iint_D x^2 \, d\sigma$ 非零。

对于 $2y$ 项：$y$ 是奇函数，关于 $y$ 轴对称的区域上积分为零。

$$\iint_D x^2 \, d\sigma = \iint_D y^2 \, d\sigma = \frac{1}{2}\iint_D (x^2+y^2) \, d\sigma = \frac{1}{2}\int_0^{2\pi} \int_0^1 r^2 \cdot r \, dr \, d\theta$$

$$= \frac{1}{2} \cdot 2\pi \cdot \frac{1}{4} = \frac{\pi}{4}$$

所以原积分 $= \frac{\pi}{4}$。

**总结**：利用对称性可大大简化重积分计算。

---

### 例题6：球面坐标应用

**题目**：计算 $\iiint_\Omega (x^2+y^2+z^2) \, dv$，其中 $\Omega: x^2+y^2+z^2 \leq 2z$。

**思路**：用球面坐标计算。

**解答**：
球面 $x^2+y^2+z^2 = 2z$ 化为 $r^2 = 2r\cos\varphi$，即 $r = 2\cos\varphi$

在球面坐标中：$0 \leq r \leq 2\cos\varphi$，$0 \leq \varphi \leq \frac{\pi}{2}$，$0 \leq \theta \leq 2\pi$

被积函数 $x^2+y^2+z^2 = r^2$

$$dv = r^2\sin\varphi \, dr \, d\varphi \, d\theta$$

$$\iiint_\Omega r^2 \, dv = \int_0^{2\pi} d\theta \int_0^{\pi/2} \sin\varphi \, d\varphi \int_0^{2\cos\varphi} r^4 \, dr$$

$$= 2\pi \int_0^{\pi/2} \sin\varphi \cdot \frac{r^5}{5}\bigg|_0^{2\cos\varphi} d\varphi = \frac{64\pi}{5}\int_0^{\pi/2} \sin\varphi \cos^5\varphi \, d\varphi$$

$$= \frac{64\pi}{5} \cdot \frac{1}{6} = \frac{32\pi}{15}$$

**总结**：球面坐标适用于球形或球壳区域。

---

## 七、解题方法总结

### 7.1 二重积分计算

| 方法 | 适用情形 |
|------|----------|
| 直角坐标（先 $y$ 后 $x$） | 区域为 X-型 |
| 直角坐标（先 $x$ 后 $y$） | 区域为 Y-型 |
| 极坐标 | 区域边界为圆弧，被积函数含 $x^2+y^2$ |

### 7.2 三重积分计算

| 方法 | 适用情形 |
|------|----------|
| 直角坐标（投影法） | 区域在 $xy$ 平面投影易得 |
| 直角坐标（截面法） | 被积函数仅是 $z$ 的函数 |
| 柱面坐标 | 投影是圆域，被积函数含 $x^2+y^2$ |
| 球面坐标 | 区域是球形或球壳，被积函数含 $x^2+y^2+z^2$ |

### 7.3 常用技巧

1. **利用对称性**：区域对称+函数奇偶性
2. **轮换对称性**：$x \leftrightarrow y$ 互换区域不变
3. **坐标变换**：化简积分区域或被积函数

---

## 八、练习题精选

### 基础练习

1. 计算 $\iint_D x^2 y \, d\sigma$，其中 $D: 0 \leq x \leq 1$，$0 \leq y \leq 1$。

2. 将 $\int_0^1 \, dx \int_x^{\sqrt{x}} f(x,y) \, dy$ 交换积分次序。

3. 计算 $\iint_D \sqrt{x^2+y^2} \, d\sigma$，其中 $D: x^2+y^2 \leq 4$。

4. 计算 $\iiint_\Omega xyz \, dv$，其中 $\Omega: 0 \leq x,y,z \leq 1$。

### 提高练习

5. 计算 $\iint_D \sin\sqrt{x^2+y^2} \, d\sigma$，其中 $D: \pi^2 \leq x^2+y^2 \leq 4\pi^2$。

6. 计算 $\iiint_\Omega \sqrt{x^2+y^2} \, dv$，其中 $\Omega$ 由 $z = \sqrt{x^2+y^2}$ 与 $z = 1$ 围成。

7. 计算 $\iiint_\Omega z \, dv$，其中 $\Omega: x^2+y^2+z^2 \leq R^2$，$z \geq 0$。

8. 计算 $\iint_D (x+y) \, d\sigma$，其中 $D$ 由 $y = x$、$y = x+1$、$y = 1$、$y = 3$ 围成。

---

## 参考答案提示

1. $\frac{1}{6}$（提示：直接积分）

2. $\int_0^1 \, dy \int_{y^2}^{y} f(x,y) \, dx$

3. $\frac{16\pi}{3}$（提示：极坐标）

4. $\frac{1}{16}$（提示：三次积分直接计算）

5. $-2\pi^3$（提示：极坐标，注意 $r$ 的范围）

6. $\frac{\pi}{6}$（提示：柱面坐标或截面法）

7. $\frac{\pi R^4}{4}$（提示：截面法或球面坐标）

8. $4$（提示：平移变换或直接计算）

---

> **注**：本 Lecture 内容涵盖重积分的基本概念、计算方法和典型例题。建议结合《基础过关660题》第104-120题进行练习巩固。
