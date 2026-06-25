---
title: Lecture 06 - 曲线曲面积分
subject: 高等数学
chapter: 第六章
lecture: 06
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 06: 曲线曲面积分

## 一、第一类曲线积分（对弧长的曲线积分）

### 1.1 定义

<span style="background-color: #ccc1d9">**定义（第一类曲线积分）**</span> 设 $L$ 为空间中的一段光滑曲线弧，$f(x,y,z)$ 在 $L$ 上有定义。将 $L$ 分成 $n$ 段，长度分别为 $\Delta s_1, \Delta s_2, \ldots, \Delta s_n$，在每段上取一点 $(\xi_i, \eta_i, \zeta_i)$，作和

$$\sum_{i=1}^{n} f(\xi_i, \eta_i, \zeta_i) \Delta s_i$$

若当各段弧长的最大值 $\lambda \to 0$ 时，此和的极限存在，则称此极限为 $f(x,y,z)$ 在曲线 $L$ 上的**第一类曲线积分**，记作

$$\int_L f(x,y,z) \, ds$$

### 1.2 计算方法

**参数方程形式**：若曲线 $L$ 由参数方程 $x = x(t)$，$y = y(t)$，$z = z(t)$（$t \in [\alpha, \beta]$）给出，则

$$\int_L f(x,y,z) \, ds = \int_\alpha^\beta f(x(t), y(t), z(t)) \sqrt{[x'(t)]^2 + [y'(t)]^2 + [z'(t)]^2} \, dt$$

**直角坐标系**：若 $y = y(x)$，$x \in [a,b]$，则

$$\int_L f(x,y) \, ds = \int_a^b f(x, y(x)) \sqrt{1 + [y'(x)]^2} \, dx$$

**极坐标系**：若 $r = r(\theta)$，$\theta \in [\alpha, \beta]$，则

$$\int_L f(x,y) \, ds = \int_\alpha^\beta f(r\cos\theta, r\sin\theta) \sqrt{r^2 + [r'(\theta)]^2} \, d\theta$$

### 1.3 应用

- **质量**：若曲线 $L$ 的线密度为 $\rho(x,y,z)$，则质量 $m = \int_L \rho(x,y,z) \, ds$
- **质心**：$\bar{x} = \frac{1}{m}\int_L x\rho \, ds$（类似地有 $\bar{y}$，$\bar{z}$）
- **转动惯量**：$I_L = \int_L (y^2+z^2)\rho \, ds$（关于某轴的转动惯量）

---

## 二、第二类曲线积分（对坐标的曲线积分）

### 2.1 定义

<span style="background-color: #ccc1d9">**定义（第二类曲线积分）**</span> 设 $L$ 为空间中的一段有向光滑曲线弧，$P(x,y,z)$、$Q(x,y,z)$、$R(x,y,z)$ 在 $L$ 上有定义。将 $L$ 分成 $n$ 段，设各段终点的坐标差为 $\Delta x_i, \Delta y_i, \Delta z_i$，作和

$$\sum_{i=1}^{n} [P(\xi_i, \eta_i, \zeta_i)\Delta x_i + Q(\xi_i, \eta_i, \zeta_i)\Delta y_i + R(\xi_i, \eta_i, \zeta_i)\Delta z_i]$$

若当各段弧长的最大值 $\lambda \to 0$ 时，此和的极限存在，则称此极限为向量函数 $\vec{F} = (P, Q, R)$ 在有向曲线 $L$ 上的**第二类曲线积分**，记作

$$\int_L P \, dx + Q \, dy + R \, dz$$

### 2.2 计算方法

**参数方程形式**：若曲线 $L$ 由参数方程 $x = x(t)$，$y = y(t)$，$z = z(t)$ 给出，$t$ 从 $\alpha$ 变到 $\beta$（对应 $L$ 的方向），则

$$\int_L P \, dx + Q \, dy + R \, dz = \int_\alpha^\beta [P(x(t),y(t),z(t))x'(t) + Q(x(t),y(t),z(t))y'(t) + R(x(t),y(t),z(t))z'(t)] \, dt$$

**注意**：第二类曲线积分与曲线的方向有关，改变方向则积分值变号。

### 2.3 两类曲线积分的联系

$$\int_L P \, dx + Q \, dy + R \, dz = \int_L (P\cos\alpha + Q\cos\beta + R\cos\gamma) \, ds$$

其中 $\cos\alpha, \cos\beta, \cos\gamma$ 为曲线切向量的方向余弦。

---

## 三、格林公式

### 3.1 格林公式

<span style="background-color: #8db3e2">**定理（格林公式）**</span> 设闭区域 $D$ 由分段光滑的曲线 $L$ 围成，$P(x,y)$、$Q(x,y)$ 在 $D$ 上有一阶连续偏导数，则

$$\oint_L P \, dx + Q \, dy = \iint_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) \, d\sigma$$

其中 $L$ 是取正向（逆时针方向）的闭曲线。

### 3.2 平面上曲线积分与路径无关的条件

<span style="background-color: #8db3e2">**定理**</span> 设 $D$ 是单连通区域，$P(x,y)$、$Q(x,y)$ 在 $D$ 内有一阶连续偏导数，则以下四个命题等价：

1. $\oint_L P \, dx + Q \, dy = 0$（$L$ 为 $D$ 内任意闭曲线）
2. 曲线积分 $\int_{\widehat{AB}} P \, dx + Q \, dy$ 与路径无关
3. $P \, dx + Q \, dy$ 是某二元函数的全微分
4. 在 $D$ 内恒有 $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$

### 3.3 原函数求法

若 $P \, dx + Q \, dy = df$，则 $f(x,y)$ 为原函数，可用以下方法求：

$$f(x,y) = \int_{(x_0,y_0)}^{(x,y)} P \, dx + Q \, dy$$

取折线路径积分。

---

## 四、第一类曲面积分（对面积的曲面积分）

### 4.1 定义

<span style="background-color: #ccc1d9">**定义（第一类曲面积分）**</span> 设曲面 $\Sigma$ 光滑，$f(x,y,z)$ 在 $\Sigma$ 上有定义。将 $\Sigma$ 分成 $n$ 小块，面积分别为 $\Delta S_1, \Delta S_2, \ldots, \Delta S_n$，在每块上取一点 $(\xi_i, \eta_i, \zeta_i)$，作和

$$\sum_{i=1}^{n} f(\xi_i, \eta_i, \zeta_i) \Delta S_i$$

若当各小块面积最大值 $\lambda \to 0$ 时，此和的极限存在，则称此极限为 $f(x,y,z)$ 在曲面 $\Sigma$ 上的**第一类曲面积分**，记作

$$\iint_\Sigma f(x,y,z) \, dS$$

### 4.2 计算方法

若曲面 $\Sigma$ 由方程 $z = z(x,y)$ 给出，$\Sigma$ 在 $xy$ 平面的投影为 $D_{xy}$，则

$$\iint_\Sigma f(x,y,z) \, dS = \iint_{D_{xy}} f(x,y,z(x,y)) \sqrt{1 + [z_x]^2 + [z_y]^2} \, d\sigma$$

### 4.3 应用

- **质量**：若曲面 $\Sigma$ 的面密度为 $\rho(x,y,z)$，则质量 $m = \iint_\Sigma \rho \, dS$
- **质心**：$\bar{x} = \frac{1}{m}\iint_\Sigma x\rho \, dS$（类似地有 $\bar{y}$，$\bar{z}$）

---

## 五、第二类曲面积分（对坐标的曲面积分）

### 5.1 定义

<span style="background-color: #ccc1d9">**定义（第二类曲面积分）**</span> 设光滑曲面 $\Sigma$ 的法向量为 $\vec{n} = (\cos\alpha, \cos\beta, \cos\gamma)$，向量函数 $\vec{F} = (P, Q, R)$ 在 $\Sigma$ 上有定义，则

$$\iint_\Sigma \vec{F} \cdot d\vec{S} = \iint_\Sigma (P\cos\alpha + Q\cos\beta + R\cos\gamma) \, dS$$

也记作

$$\iint_\Sigma P \, dy \, dz + Q \, dz \, dx + R \, dx \, dy$$

**注意**：第二类曲面积分与曲面的侧（即法向量方向）有关。

### 5.2 计算方法

**投影法**：将曲面积分化为二重积分。

若曲面 $\Sigma$ 由 $z = z(x,y)$ 给出，取上侧，则

$$\iint_\Sigma R(x,y,z) \, dx \, dy = \iint_{D_{xy}} R(x,y,z(x,y)) \, d\sigma$$

类似地：
$$\iint_\Sigma P \, dy \, dz = \iint_{D_{yz}} P(x(y,z),y,z) \, d\sigma$$
$$\iint_\Sigma Q \, dz \, dx = \iint_{D_{xz}} Q(x,y(x,z),z) \, d\sigma$$

### 5.3 两类曲面积分的联系

$$\iint_\Sigma P \, dy \, dz + Q \, dz \, dx + R \, dx \, dy = \iint_\Sigma (P\cos\alpha + Q\cos\beta + R\cos\gamma) \, dS$$

---

## 六、高斯公式

### 6.1 高斯公式

<span style="background-color: #8db3e2">**定理（高斯公式）**</span> 设空间闭区域 $\Omega$ 由分片光滑的闭曲面 $\Sigma$ 围成，$P(x,y,z)$、$Q(x,y,z)$、$R(x,y,z)$ 在 $\Omega$ 上有一阶连续偏导数，则

$$\oint_\Sigma P \, dy \, dz + Q \, dz \, dx + R \, dx \, dy = \iiint_\Omega \left(\frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}\right) \, dv$$

其中 $\Sigma$ 取外侧。

### 6.2 散度

<span style="background-color: #ccc1d9">**定义（散度）**</span> 向量场 $\vec{F} = (P, Q, R)$ 的散度为

$$\text{div} \vec{F} = \frac{\partial P}{\partial x} + \frac{\partial Q}{\partial y} + \frac{\partial R}{\partial z}$$

高斯公式可写为

$$\oint_\Sigma \vec{F} \cdot d\vec{S} = \iiint_\Omega \text{div} \vec{F} \, dv$$

---

## 七、斯托克斯公式

### 7.1 斯托克斯公式

<span style="background-color: #8db3e2">**定理（斯托克斯公式）**</span> 设 $\Sigma$ 为分片光滑的有向曲面，$L$ 为 $\Sigma$ 的边界曲线（取正向），$P$、$Q$、$R$ 在 $\Sigma$（连同 $L$）上有一阶连续偏导数，则

$$\oint_L P \, dx + Q \, dy + R \, dz = \iint_\Sigma \begin{vmatrix} dy \, dz & dz \, dx & dx \, dy \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ P & Q & R \end{vmatrix}$$

或写为

$$\oint_L P \, dx + Q \, dy + R \, dz = \iint_\Sigma \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dy \, dz + \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dz \, dx + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right) dx \, dy$$

### 7.2 旋度

<span style="background-color: #ccc1d9">**定义（旋度）**</span> 向量场 $\vec{F} = (P, Q, R)$ 的旋度为

$$\text{rot} \vec{F} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ P & Q & R \end{vmatrix} = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}, \frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}, \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right)$$

斯托克斯公式可写为

$$\oint_L \vec{F} \cdot d\vec{r} = \iint_\Sigma \text{rot} \vec{F} \cdot d\vec{S}$$

---

## 八、散度与旋度

### 8.1 散度的物理意义

散度 $\text{div} \vec{F}$ 表示向量场 $\vec{F}$ 在点 $(x,y,z)$ 处的通量密度，即单位体积内穿出闭曲面的通量。

- $\text{div} \vec{F} > 0$：该点为"源"
- $\text{div} \vec{F} < 0$：该点为"汇"
- $\text{div} \vec{F} = 0$：无源场

### 8.2 旋度的物理意义

旋度 $\text{rot} \vec{F}$ 表示向量场 $\vec{F}$ 在点 $(x,y,z)$ 处的旋转强度和方向，即单位面积上的环量最大值。

- $\text{rot} \vec{F} = \vec{0}$：无旋场（保守场）
- $\text{rot} \vec{F} \neq \vec{0}$：有旋场

---

## 九、典型例题

### 例题1：第一类曲线积分

**题目**（严选题4）：设 $L$ 为圆周 $x^2+y^2+2y=0$，则 $\int_L \sqrt{x^2+y^2} \, ds$。

**思路**：将圆周化为标准参数方程，计算弧长元素。

**解答**：
圆 $x^2+y^2+2y=0$ 化为 $x^2+(y+1)^2=1$

参数方程：$x = \cos t$，$y = -1 + \sin t$，$t \in [0, 2\pi]$

$$\sqrt{x^2+y^2} = \sqrt{\cos^2 t + (-1+\sin t)^2} = \sqrt{1 - 2\sin t + \sin^2 t + \sin^2 t}$$

$= \sqrt{1 - 2\sin t + 2\sin^2 t}$

弧长元素：$ds = \sqrt{x'^2 + y'^2} \, dt = \sqrt{(-\sin t)^2 + (\cos t)^2} \, dt = dt$

$$\int_L \sqrt{x^2+y^2} \, ds = \int_0^{2\pi} \sqrt{1 - 2\sin t + 2\sin^2 t} \, dt$$

化简后计算。

**总结**：参数方程法是计算第一类曲线积分的基本方法。

---

### 例题2：第二类曲线积分（格林公式）

**题目**（严选题2）：设 $L$ 为 $y=1-|1-x|$ 由点 $(0,0)$ 到点 $(2,0)$ 的折线段，则 $\int_L (x^2+y^2) \, dx + (x^2-y^2) \, dy$。

**思路**：补线用格林公式，或直接分段计算。

**解答**：
折线 $L$ 由两段组成：
- $L_1$：从 $(0,0)$ 到 $(1,1)$，$y = x$
- $L_2$：从 $(1,1)$ 到 $(2,0)$，$y = 2-x$

直接分段计算：

$$L_1: x=t, y=t, t:0\to1, \quad dx=dt, dy=dt$$

$$L_2: x=t, y=2-t, t:1\to2, \quad dx=dt, dy=-dt$$

代入积分计算可得结果。

**总结**：分段光滑曲线的积分需分段计算或用格林公式补线。

---

### 例题3：曲面积分（高斯公式）

**题目**（严选题12）：设 $\Sigma$ 为球面 $x^2+y^2+z^2=2Rz$（$R>0$）的外侧，则 $\iint_\Sigma xz \, dy \, dz + xy \, dz \, dx + yz \, dx \, dy$。

**思路**：直接用高斯公式。

**解答**：
由高斯公式：
$$I = \iiint_\Omega \left(\frac{\partial(xz)}{\partial x} + \frac{\partial(xy)}{\partial y} + \frac{\partial(yz)}{\partial z}\right) dv = \iiint_\Omega (z + x + y) \, dv$$

其中 $\Omega$ 为球面围成的区域 $x^2+y^2+z^2 \leq 2Rz$。

利用对称性：$\iiint_\Omega x \, dv = \iiint_\Omega y \, dv = 0$（区域关于 $y=0$ 和 $x=0$ 平面对称，$x$ 和 $y$ 为奇函数）

所以 $I = \iiint_\Omega z \, dv$。

用球面坐标：$r = 2R\cos\varphi$，$0 \leq \varphi \leq \frac{\pi}{2}$，$0 \leq \theta \leq 2\pi$

$$I = \int_0^{2\pi} d\theta \int_0^{\pi/2} \sin\varphi \cos\varphi \, d\varphi \int_0^{2R\cos\varphi} r^3 \, dr = \frac{32\pi R^4}{15}$$

**总结**：高斯公式将曲面积分化为三重积分，利用对称性可简化计算。

---

### 例题4：斯托克斯公式

**题目**（严选题10）：设 $L$ 是柱面 $x^2+y^2=1$ 与平面 $z=x+y$ 的交线，从 $z$ 轴正向往负向看去为逆时针方向，则 $\oint_L xz \, dx + x \, dy + \frac{y^2}{2} \, dz$。

**思路**：用斯托克斯公式化为曲面积分。

**解答**：
由斯托克斯公式：
$$\oint_L P \, dx + Q \, dy + R \, dz = \iint_\Sigma \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dy \, dz + \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dz \, dx + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right) dx \, dy$$

其中 $P = xz$，$Q = x$，$R = \frac{y^2}{2}$

计算偏导数：
$$\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = 1 - 0 = 1$$
$$\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z} = y - 0 = y$$
$$\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x} = x - 0 = x$$

取平面 $z = x + y$ 的上侧，投影区域为 $D: x^2+y^2 \leq 1$

$dS = \sqrt{1+z_x^2+z_y^2} \, d\sigma = \sqrt{3} \, d\sigma$

$$\oint_L = \iint_D (1 \cdot \frac{\partial(x,y)}{\partial(y,z)} + y \cdot \frac{\partial(x,y)}{\partial(z,x)} + x \cdot \frac{\partial(x,y)}{\partial(x,y)}) \sqrt{3} \, d\sigma$$

直接计算得 $\pi$。

**总结**：斯托克斯公式将空间曲线积分化为曲面积分。

---

### 例题5：曲线积分与路径无关

**题目**（严选题11）：若曲线积分 $\int_L \frac{x \, dx - ay \, dy}{x^2+y^2-1}$ 在区域 $D = \{(x,y) \mid x^2+y^2<1\}$ 内与路径无关，则 $a =$？

**思路**：利用与路径无关的条件 $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$。

**解答**：
$$P = \frac{x}{x^2+y^2-1}, \quad Q = \frac{-ay}{x^2+y^2-1}$$

在 $D$ 内（$x^2+y^2<1$），计算偏导数：

$$\frac{\partial P}{\partial y} = \frac{-2xy}{(x^2+y^2-1)^2}$$

$$\frac{\partial Q}{\partial x} = \frac{-2axy}{(x^2+y^2-1)^2}$$

由 $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$ 得 $-2xy = -2axy$，即 $a = 1$。

**总结**：与路径无关的条件是 $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$（在单连通区域内）。

---

### 例题6：散度与旋度

**题目**：求向量场 $\vec{F} = (x^2, xy, z^2)$ 的散度和旋度。

**思路**：直接用公式计算。

**解答**：
散度：
$$\text{div} \vec{F} = \frac{\partial x^2}{\partial x} + \frac{\partial (xy)}{\partial y} + \frac{\partial (z^2)}{\partial z} = 2x + x + 2z = 3x + 2z$$

旋度：
$$\text{rot} \vec{F} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ x^2 & xy & z^2 \end{vmatrix}$$

$$= \left(\frac{\partial(z^2)}{\partial y} - \frac{\partial(xy)}{\partial z}, \frac{\partial(x^2)}{\partial z} - \frac{\partial(z^2)}{\partial x}, \frac{\partial(xy)}{\partial x} - \frac{\partial(x^2)}{\partial y}\right)$$

$= (0 - 0, 0 - 0, y - 0) = (0, 0, y)$

**总结**：散度和旋度是向量场的两个基本量。

---

## 十、解题方法总结

### 10.1 曲线积分

| 类型 | 方法 |
|------|------|
| 第一类曲线积分 | 参数方程法，弧长元素 $ds$ |
| 第二类曲线积分 | 参数方程法，注意方向 |
| 格林公式 | 闭曲线，化为二重积分 |
| 与路径无关 | 检查 $\frac{\partial P}{\partial y} = \frac{\partial Q}{\partial x}$，求原函数 |

### 10.2 曲面积分

| 类型 | 方法 |
|------|------|
| 第一类曲面积分 | 投影到坐标面，$dS = \sqrt{1+z_x^2+z_y^2} \, d\sigma$ |
| 第二类曲面积分 | 投影法，注意侧的方向 |
| 高斯公式 | 闭曲面，化为三重积分 |

### 10.3 常用公式

**斯托克斯公式**：
$$\oint_L P \, dx + Q \, dy + R \, dz = \iint_\Sigma \text{rot} \vec{F} \cdot d\vec{S}$$

**高斯公式**：
$$\oint_\Sigma \vec{F} \cdot d\vec{S} = \iiint_\Omega \text{div} \vec{F} \, dv$$

---

## 十一、练习题精选

### 基础练习

1. 计算 $\int_L y \, ds$，其中 $L$ 为抛物线 $y = x^2$ 从 $(0,0)$ 到 $(1,1)$。

2. 计算 $\int_L (x+y) \, dx + (x-y) \, dy$，其中 $L$ 为从 $(0,0)$ 到 $(1,1)$ 的直线段。

3. 计算 $\iint_\Sigma z \, dS$，其中 $\Sigma$ 为锥面 $z = \sqrt{x^2+y^2}$ 被平面 $z=1$ 截下的部分。

4. 求向量场 $\vec{F} = (y, -x, z)$ 的散度。

### 提高练习

5. 用格林公式计算 $\oint_L (x^2y \, dx + xy^2 \, dy)$，其中 $L$ 为圆 $x^2+y^2=1$ 的正向。

6. 计算 $\iint_\Sigma x \, dy \, dz + y \, dz \, dx + z \, dx \, dy$，其中 $\Sigma$ 为球面 $x^2+y^2+z^2=a^2$ 的外侧。

7. 验证向量场 $\vec{F} = (2x+y, 2y+z, 2z+x)$ 是保守场，并求其势函数。

8. 计算 $\oint_L yz \, dx + zx \, dy + xy \, dz$，其中 $L$ 为螺旋线 $x=a\cos t$，$y=a\sin t$，$z=bt$ 的一圈。

---

## 参考答案提示

1. $\frac{1}{12}(5\sqrt{5}-1)$（提示：参数方程法）

2. $1$（提示：直线参数方程）

3. $\sqrt{2}\pi$（提示：极坐标计算）

4. $1$（提示：$\text{div} \vec{F} = \frac{\partial y}{\partial x} + \frac{\partial (-x)}{\partial y} + \frac{\partial z}{\partial z} = 1$）

5. $0$（提示：格林公式）

6. $4\pi a^3$（提示：高斯公式）

7. 势函数 $f = x^2 + xy + y^2 + xz + yz + z^2 + C$（提示：验证旋度为零）

8. $2\pi a^2 b$（提示：参数方程直接计算）

---

> **注**：本 Lecture 内容涵盖曲线曲面积分的基本概念、计算方法和典型例题。建议结合武忠祥《高数基础篇》及《严选题》进行练习巩固。
