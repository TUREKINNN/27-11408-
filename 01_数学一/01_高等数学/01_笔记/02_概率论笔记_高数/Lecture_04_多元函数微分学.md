---
title: Lecture 04 - 多元函数微分学
subject: 高等数学
chapter: 第五章
lecture: 04
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 04: 多元函数微分学

## 一、多元函数的概念

### 1.1 二元函数的定义

<span style="background-color: #ccc1d9">**定义（二元函数）**</span> 设 $D$ 是平面上的一个非空点集，若对于每个点 $P(x,y) \in D$，按照某种法则 $f$，总有唯一确定的实数 $z$ 与之对应，则称 $f$ 为定义在 $D$ 上的**二元函数**，记作

$$z = f(x,y), \quad (x,y) \in D$$

其中 $D$ 称为**定义域**，$z$ 称为**函数值**。

### 1.2 二元函数的几何意义

二元函数 $z = f(x,y)$ 表示空间中的一张曲面。

---

## 二、二元函数的极限与连续

### 2.1 二重极限

<span style="background-color: #ccc1d9">**定义（二重极限）**</span> 设函数 $f(x,y)$ 在点 $P_0(x_0,y_0)$ 的某去心邻域内有定义，若存在常数 $A$，对于任意 $\varepsilon > 0$，总存在 $\delta > 0$，使得当 $0 < \sqrt{(x-x_0)^2+(y-y_0)^2} < \delta$ 时，恒有

$$|f(x,y) - A| < \varepsilon$$

则称 $A$ 为 $f(x,y)$ 当 $(x,y) \to (x_0,y_0)$ 时的**极限**，记作

$$\lim_{(x,y) \to (x_0,y_0)} f(x,y) = A$$

### 2.2 二次极限

<span style="background-color: #ccc1d9">**定义（二次极限）**</span>
- **先 $y$ 后 $x$**：$\lim_{x \to x_0}\lim_{y \to y_0} f(x,y)$
- **先 $x$ 后 $y$**：$\lim_{y \to y_0}\lim_{x \to x_0} f(x,y)$

**注意**：两个二次极限存在且相等，不能推出二重极限存在；二重极限存在也不能推出二次极限存在。

### 2.3 连续性

<span style="background-color: #ccc1d9">**定义（连续）**</span> 若 $\lim_{(x,y) \to (x_0,y_0)} f(x,y) = f(x_0,y_0)$，则称 $f(x,y)$ 在点 $(x_0,y_0)$ **连续**。

<span style="background-color: #8db3e2">**定理**</span> 若二元函数在有界闭区域上连续，则函数在该区域上有界，并能取得最大值和最小值。

<span style="background-color: #8db3e2">**定理（介值定理）**</span> 若二元函数在有界闭区域上连续，则它必能取得介于最大值和最小值之间的任何值。

---

## 三、偏导数的定义

### 3.1 偏导数的定义

<span style="background-color: #ccc1d9">**定义（偏导数）**</span> 设函数 $z = f(x,y)$ 在点 $(x_0,y_0)$ 的某邻域内有定义，若极限

$$\lim_{\Delta x \to 0} \frac{f(x_0+\Delta x, y_0) - f(x_0,y_0)}{\Delta x}$$

存在，则称此极限为函数 $f(x,y)$ 在点 $(x_0,y_0)$ 处对 $x$ 的**偏导数**，记作

$$f_x(x_0,y_0), \quad \frac{\partial f}{\partial x}\bigg|_{(x_0,y_0)}, \quad z_x\bigg|_{(x_0,y_0)}$$

类似地，对 $y$ 的偏导数定义为

$$f_y(x_0,y_0) = \lim_{\Delta y \to 0} \frac{f(x_0, y_0+\Delta y) - f(x_0,y_0)}{\Delta y}$$

### 3.2 偏导数的几何意义

偏导数 $f_x(x_0,y_0)$ 表示曲面 $z = f(x,y)$ 与平面 $y = y_0$ 的交线在点 $(x_0,y_0,f(x_0,y_0))$ 处的切线对 $x$ 轴的斜率。

---

## 四、偏导数的计算

### 4.1 高阶偏导数

<span style="background-color: #ccc1d9">**定义（高阶偏导数）**</span>
- 二阶偏导数：$\frac{\partial^2 f}{\partial x^2} = f_{xx}$，$\frac{\partial^2 f}{\partial y^2} = f_{yy}$
- 混合偏导数：$\frac{\partial^2 f}{\partial x \partial y} = f_{xy}$，$\frac{\partial^2 f}{\partial y \partial x} = f_{yx}$

<span style="background-color: #8db3e2">**定理**</span> 若 $f_{xy}$ 和 $f_{yx}$ 在区域 $D$ 内连续，则在该区域内 $f_{xy} = f_{yx}$。

---

## 五、全微分的定义与计算

### 5.1 全微分的定义

<span style="background-color: #ccc1d9">**定义（全微分）**</span> 若函数 $z = f(x,y)$ 在点 $(x,y)$ 的全增量

$$\Delta z = f(x+\Delta x, y+\Delta y) - f(x,y)$$

可以表示为

$$\Delta z = A\Delta x + B\Delta y + o(\rho)$$

其中 $A, B$ 与 $\Delta x, \Delta y$ 无关，$\rho = \sqrt{(\Delta x)^2 + (\Delta y)^2}$，则称 $z = f(x,y)$ 在点 $(x,y)$ **可微**，并称 $A\Delta x + B\Delta y$ 为**全微分**，记作

$$dz = df = A \, dx + B \, dy$$

### 5.2 全微分的计算

<span style="background-color: #8db3e2">**定理**</span> 若 $z = f(x,y)$ 在点 $(x,y)$ 可微，则偏导数 $f_x(x,y)$ 和 $f_y(x,y)$ 必存在，且

$$dz = \frac{\partial f}{\partial x}dx + \frac{\partial f}{\partial y}dy$$

---

## 六、全微分存在的必要条件和充分条件

### 6.1 必要条件

<span style="background-color: #8db3e2">**定理**</span> 若 $z = f(x,y)$ 在点 $(x,y)$ 可微，则偏导数 $f_x$ 和 $f_y$ 必存在，且

$$dz = f_x(x,y)dx + f_y(x,y)dy$$

### 6.2 充分条件

<span style="background-color: #8db3e2">**定理**</span> 若 $z = f(x,y)$ 在点 $(x,y)$ 的某邻域内偏导数 $f_x$ 和 $f_y$ 都存在且连续，则 $z = f(x,y)$ 在点 $(x,y)$ 可微。

---

## 七、多元复合函数的求导法则

### 7.1 链式法则

<span style="background-color: #8db3e2">**定理（链式法则）**</span> 若函数 $u = u(x,y)$，$v = v(x,y)$ 在点 $(x,y)$ 处偏导数存在，函数 $z = f(u,v)$ 在对应点 $(u,v)$ 处可微，则复合函数 $z = f(u(x,y), v(x,y))$ 在点 $(x,y)$ 处的偏导数存在，且

$$\frac{\partial z}{\partial x} = \frac{\partial z}{\partial u}\frac{\partial u}{\partial x} + \frac{\partial z}{\partial v}\frac{\partial v}{\partial x}$$

$$\frac{\partial z}{\partial y} = \frac{\partial z}{\partial u}\frac{\partial u}{\partial y} + \frac{\partial z}{\partial v}\frac{\partial v}{\partial y}$$

### 7.2 全微分形式不变性

<span style="background-color: #8db3e2">**定理**</span> 全微分形式不变性对多元复合函数同样适用：

$$dz = \frac{\partial z}{\partial u}du + \frac{\partial z}{\partial v}dv$$

无论 $u, v$ 是自变量还是中间变量，上式总成立。

---

## 八、隐函数的求导法则

### 8.1 一个方程确定的情形

<span style="background-color: #ccc1d9">**定义（隐函数）**</span> 若方程 $F(x,y) = 0$ 确定的函数关系 $y = y(x)$，则称此函数为**隐函数**。

<span style="background-color: #8db3e2">**定理**</span> 若函数 $F(x,y)$ 在点 $(x_0,y_0)$ 的某邻域内偏导数连续，且 $F(x_0,y_0) = 0$，$F_y(x_0,y_0) \neq 0$，则方程 $F(x,y) = 0$ 唯一确定一个连续可导的隐函数 $y = f(x)$，且

$$\frac{dy}{dx} = -\frac{F_x}{F_y}$$

### 8.2 多个方程确定的情形

**由两个方程确定的隐函数组**：
若 $\begin{cases}F(x,y,z) = 0 \\ G(x,y,z) = 0\end{cases}$ 确定 $y = y(x)$，$z = z(x)$，则

$$\frac{dy}{dx} = -\frac{\frac{\partial(F,G)}{\partial(F,G)}}{\frac{\partial(F,G)}{\partial(x,z)}}, \quad \frac{dz}{dx} = -\frac{\frac{\partial(F,G)}{\partial(y,x)}}{\frac{\partial(F,G)}{\partial(y,z)}}$$

---

## 九、方向导数与梯度

### 9.1 方向导数

<span style="background-color: #ccc1d9">**定义（方向导数）**</span> 设函数 $z = f(x,y)$ 在点 $P(x,y)$ 的某邻域内有定义，$l$ 是从 $P$ 出发的射线，$P'$ 为 $l$ 上另一点，若极限

$$\lim_{P' \to P} \frac{f(P') - f(P)}{|PP'|}$$

存在，则称此极限为 $f(x,y)$ 在点 $P$ 沿方向 $l$ 的**方向导数**，记作

$$\frac{\partial f}{\partial l} = \lim_{\rho \to 0^+} \frac{f(x+\Delta x, y+\Delta y) - f(x,y)}{\rho}$$

<span style="background-color: #8db3e2">**定理**</span> 若 $z = f(x,y)$ 在点 $(x,y)$ 可微，则沿任一方向 $l$ 的方向导数存在，且

$$\frac{\partial f}{\partial l} = f_x \cos \alpha + f_y \cos \beta$$

其中 $\cos \alpha, \cos \beta$ 为方向 $l$ 的方向余弦。

### 9.2 梯度

<span style="background-color: #ccc1d9">**定义（梯度）**</span> 设 $z = f(x,y)$ 在区域 $D$ 内有一阶连续偏导数，则称向量

$$\nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}\right)$$

为函数 $f(x,y)$ 的**梯度**，记作 $\text{grad} \, f$。

<span style="background-color: #8db3e2">**定理**</span> 方向导数 $\frac{\partial f}{\partial l}$ 等于梯度 $\nabla f$ 与方向 $l$ 的方向余弦的数积：

$$\frac{\partial f}{\partial l} = \nabla f \cdot \vec{l} = |\nabla f| \cos(\nabla f, \vec{l})$$

---

## 十、空间曲线的切线和法平面

### 10.1 参数方程形式

设空间曲线 $\Gamma$ 的参数方程为 $x = x(t)$，$y = y(t)$，$z = z(t)$，则在点 $t = t_0$ 处的切向量为

$$\vec{T} = (x'(t_0), y'(t_0), z'(t_0))$$

**切线方程**：
$$\frac{x-x_0}{x'(t_0)} = \frac{y-y_0}{y'(t_0)} = \frac{z-z_0}{z'(t_0)}$$

**法平面方程**：
$$x'(t_0)(x-x_0) + y'(t_0)(y-y_0) + z'(t_0)(z-z_0) = 0$$

### 10.2 一般方程形式

设空间曲线 $\Gamma$ 的一般方程为 $\begin{cases}F(x,y,z) = 0 \\ G(x,y,z) = 0\end{cases}$，则在点 $P_0(x_0,y_0,z_0)$ 处的切向量为

$$\vec{T} = \begin{vmatrix} \vec{i} & \vec{j} & \vec{k} \\ F_x & F_y & F_z \\ G_x & G_y & G_z \end{vmatrix}$$

---

## 十一、曲面的切平面和法线

### 11.1 曲面方程 $z = f(x,y)$

<span style="background-color: #ccc1d9">**定义（法向量）**</span> 曲面 $z = f(x,y)$ 在点 $(x_0,y_0,f(x_0,y_0))$ 处的法向量为

$$\vec{n} = (f_x(x_0,y_0), f_y(x_0,y_0), -1)$$

**切平面方程**：
$$f_x(x_0,y_0)(x-x_0) + f_y(x_0,y_0)(y-y_0) - (z-z_0) = 0$$

**法线方程**：
$$\frac{x-x_0}{f_x(x_0,y_0)} = \frac{y-y_0}{f_y(x_0,y_0)} = \frac{z-z_0}{-1}$$

### 11.2 曲面方程 $F(x,y,z) = 0$

<span style="background-color: #8db3e2">**定理**</span> 曲面 $F(x,y,z) = 0$ 在点 $(x_0,y_0,z_0)$ 处的法向量为

$$\vec{n} = (F_x(x_0,y_0,z_0), F_y(x_0,y_0,z_0), F_z(x_0,y_0,z_0))$$

---

## 十二、多元函数的极值

### 12.1 无条件极值

<span style="background-color: #ccc1d9">**定义（极值）**</span> 设函数 $z = f(x,y)$ 在点 $(x_0,y_0)$ 的某邻域内有定义，若对该邻域内任一点 $(x,y)$，都有

$$f(x,y) \leq f(x_0,y_0) \quad (\text{或 } f(x,y) \geq f(x_0,y_0))$$

则称 $(x_0,y_0)$ 为**极大值点**（或**极小值点**），$f(x_0,y_0)$ 为**极大值**（或**极小值**）。

<span style="background-color: #8db3e2">**定理（极值的必要条件）**</span> 若 $f(x,y)$ 在点 $(x_0,y_0)$ 处有极值且偏导数存在，则

$$f_x(x_0,y_0) = 0, \quad f_y(x_0,y_0) = 0$$

### 12.2 极值的充分条件

<span style="background-color: #8db3e2">**定理（极值的充分条件）**</span> 设函数 $f(x,y)$ 在点 $(x_0,y_0)$ 的某邻域内有一阶及二阶连续偏导数，且 $f_x(x_0,y_0) = f_y(x_0,y_0) = 0$。记

$$A = f_{xx}(x_0,y_0), \quad B = f_{xy}(x_0,y_0), \quad C = f_{yy}(x_0,y_0)$$

则：
1. 若 $AC - B^2 > 0$，则 $(x_0,y_0)$ 是**极值点**：
   - $A < 0$ 时为**极大值点**
   - $A > 0$ 时为**极小值点**
2. 若 $AC - B^2 < 0$，则 $(x_0,y_0)$ 不是极值点（**鞍点**）
3. 若 $AC - B^2 = 0$，需进一步讨论

---

## 十三、条件极值与拉格朗日乘数法

### 13.1 拉格朗日乘数法

<span style="background-color: #ccc1d9">**定义（条件极值）**</span> 求函数 $z = f(x,y)$ 在约束条件 $\varphi(x,y) = 0$ 下的极值。

<span style="background-color: #8db3e2">**定理（拉格朗日乘数法）**</span> 作拉格朗日函数

$$L(x,y,\lambda) = f(x,y) + \lambda \varphi(x,y)$$

解方程组
$$\begin{cases} \frac{\partial L}{\partial x} = f_x + \lambda \varphi_x = 0 \\ \frac{\partial L}{\partial y} = f_y + \lambda \varphi_y = 0 \\ \varphi(x,y) = 0 \end{cases}$$

得到的解 $(x_0,y_0)$ 就是可能的极值点。

### 13.2 多个约束条件的情形

对于 $n$ 元函数在 $m$ 个约束条件下的极值，需引入 $m$ 个拉格朗日乘数。

---

## 十四、多元函数的最大值与最小值

### 14.1 求最值的步骤

1. 求 $f(x,y)$ 在区域 $D$ 内部的极值（无条件极值）
2. 求 $f(x,y)$ 在区域 $D$ 边界上的极值（条件极值）
3. 比较所有候选点的函数值，最大者为最大值，最小者为最小值

### 14.2 应用问题

**步骤**：
1. 建立目标函数
2. 确定约束条件
3. 用拉格朗日乘数法求解
4. 验证为最大值还是最小值

---

## 十五、典型例题

### 例题1：偏导数计算

**题目**（660题94）：设 $f(x,y) = \int_0^{xy} e^{-t^2} \, dt$，求 $\frac{x}{y}\frac{\partial^2 f}{\partial x^2} - 2\frac{\partial^2 f}{\partial x \partial y} + \frac{y}{x}\frac{\partial^2 f}{\partial y^2}$。

**思路**：先求一阶偏导数，再求二阶偏导数，代入表达式。

**解答**：
$$\frac{\partial f}{\partial x} = ye^{-x^2y^2}, \quad \frac{\partial f}{\partial y} = xe^{-x^2y^2}$$

$$\frac{\partial^2 f}{\partial x^2} = -2y^3xe^{-x^2y^2}, \quad \frac{\partial^2 f}{\partial y^2} = -2x^3ye^{-x^2y^2}$$

$$\frac{\partial^2 f}{\partial x \partial y} = e^{-x^2y^2} - 2x^2y^2e^{-x^2y^2} = e^{-x^2y^2}(1-2x^2y^2)$$

代入得：
$$\frac{x}{y} \cdot (-2y^3xe^{-x^2y^2}) - 2 \cdot e^{-x^2y^2}(1-2x^2y^2) + \frac{y}{x} \cdot (-2x^3ye^{-x^2y^2})$$

$$= -2x^2y^2e^{-x^2y^2} - 2e^{-x^2y^2} + 4x^2y^2e^{-x^2y^2} - 2x^2y^2e^{-x^2y^2} = -2e^{-x^2y^2}$$

**总结**：复合函数偏导数计算需注意对中间变量的求导。

---

### 例题2：全微分

**题目**（660题96）：若函数 $z = z(x,y)$ 由方程 $e^{x+2y+3z} + xyz = 1$ 确定，求 $dz$。

**思路**：方程两边求全微分。

**解答**：
方程两边微分：
$$e^{x+2y+3z}(dx + 2dy + 3dz) + yz \, dx + xz \, dy + xy \, dz = 0$$

整理含 $dz$ 的项：
$$(3e^{x+2y+3z} + xy) \, dz = -(e^{x+2y+3z} + yz)dx - (2e^{x+2y+3z} + xz)dy$$

$$dz = -\frac{e^{x+2y+3z} + yz}{3e^{x+2y+3z} + xy}dx - \frac{2e^{x+2y+3z} + xz}{3e^{x+2y+3z} + xy}dy$$

**总结**：隐函数的全微分通过对方程两边求全微分来计算。

---

### 例题3：多元函数极值

**题目**（660题97）：二元函数 $f(x,y) = x^2(2+y^2) + y\ln y$ 的极小值为。

**思路**：求偏导数，解方程组，判断极值点类型。

**解答**：
$$f_x = 2x(2+y^2), \quad f_y = 2x^2y + \ln y + 1$$

令 $f_x = 0$，$f_y = 0$：

由 $f_x = 0$ 得 $x = 0$。

代入 $f_y = 0$ 得 $\ln y + 1 = 0$，即 $y = e^{-1}$。

所以极值点为 $(0, e^{-1})$。

$$f_{xx} = 2(2+y^2), \quad f_{yy} = 2x^2 + \frac{1}{y}, \quad f_{xy} = 4xy$$

在 $(0, e^{-1})$ 处：
$$A = 2(2+e^{-2}) > 0, \quad B = 0, \quad C = e, \quad AC-B^2 = 2e(2+e^{-2}) > 0$$

因为 $A > 0$，所以 $(0, e^{-1})$ 为极小值点。

$$f_{min} = f(0, e^{-1}) = 0 + e^{-1} \ln(e^{-1}) = -\frac{1}{e}$$

**总结**：多元函数极值需解偏导数方程组并用充分条件判断。

---

### 例题4：方向导数与梯度

**题目**：求 $f(x,y) = x^2 + y^2$ 在点 $(1,1)$ 沿方向 $\vec{l} = (1,-1)$ 的方向导数。

**思路**：先求梯度，再求方向余弦。

**解答**：
梯度 $\nabla f = (2x, 2y)$，在 $(1,1)$ 处为 $(2,2)$。

方向 $\vec{l}$ 的单位向量：$\vec{l}^0 = \frac{1}{\sqrt{2}}(1,-1)$

方向导数：
$$\frac{\partial f}{\partial l} = \nabla f \cdot \vec{l}^0 = (2,2) \cdot \frac{1}{\sqrt{2}}(1,-1) = \frac{2}{\sqrt{2}} - \frac{2}{\sqrt{2}} = 0$$

**总结**：方向导数等于梯度在该方向上的投影。

---

### 例题5：条件极值

**题目**（660题99）：设 $F(u,v)$ 可微，且 $F\left(x+\frac{z}{y}, y+\frac{z}{x}\right) = 0$ 确定隐函数 $z = z(x,y)$，求 $z - x\frac{\partial z}{\partial x} - y\frac{\partial z}{\partial y}$。

**思路**：利用隐函数求导公式计算偏导数。

**解答**：
令 $u = x + \frac{z}{y}$，$v = y + \frac{z}{x}$，则 $F(u,v) = 0$。

对 $x$ 求偏导：
$$F_u \cdot \left(1 + \frac{z_x}{y}\right) + F_v \cdot \frac{z_x}{x} = 0$$

对 $y$ 求偏导：
$$F_u \cdot \frac{z_y}{y} + F_v \cdot \left(1 + \frac{z_y}{x}\right) = 0$$

解得：
$$z_x = -\frac{yF_u}{xF_v + yF_u}, \quad z_y = -\frac{xF_v}{xF_v + yF_u}$$

代入 $z - xz_x - yz_y$ 化简可得结果为 $0$。

**总结**：条件极值问题需明确变量关系，灵活运用隐函数求导。

---

## 十六、解题方法总结

### 16.1 偏导数计算

| 类型 | 方法 |
|------|------|
| 复合函数 | 链式法则 |
| 隐函数 | 方程两边求偏导 |
| 高阶偏导数 | 逐次求导 |

### 16.2 全微分计算

1. 分别求 $\frac{\partial f}{\partial x}$ 和 $\frac{\partial f}{\partial y}$
2. 写成 $dz = f_x dx + f_y dy$

### 16.3 极值判断

1. **无条件极值**：解方程组，用充分条件判断
2. **条件极值**：拉格朗日乘数法

---

## 十七、练习题精选

### 基础练习

1. 设 $z = e^{xy} \sin(x+y)$，求 $z_x, z_y$。

2. 设 $z = f(x^2 - y^2, e^{xy})$，求 $z_x, z_y$。

3. 求 $f(x,y) = x^3 + y^3 - 3xy$ 的极值。

4. 求函数 $f(x,y) = xy$ 在条件 $x+y=2$ 下的极值。

### 提高练习

5. 设 $z = f(x,y)$，证明：若 $z_x = z_y$，则 $z = g(x+y)$。

6. 求曲面 $z = x^2 + y^2$ 在点 $(1,1,2)$ 处的切平面方程。

7. 求 $f(x,y) = x^2 + y^2 - 2x - 4y$ 在区域 $D: x^2 + y^2 \leq 9$ 上的最大值和最小值。

8. 求 $u = xyz$ 在条件 $x^2 + y^2 + z^2 = 1$ 下的最大值。

---

## 参考答案提示

1. $z_x = ye^{xy}\sin(x+y) + e^{xy}\cos(x+y)$，$z_y = xe^{xy}\sin(x+y) + e^{xy}\cos(x+y)$

2. $z_x = 2xf_1 + ye^{xy}f_2$，$z_y = -2yf_1 + xe^{xy}f_2$

3. 极小值 $f(-1,-1) = -1$，$(0,0)$ 为鞍点

4. 极大值 $f(1,1) = 1$

5. 提示：令 $u = x+y$，$v = x-y$，证明 $f_v = 0$

6. $2(x-1) + 2(y-1) - (z-2) = 0$

7. 最大值 $f(-3,-4) = 37$，最小值 $f(1,2) = -7$

8. 最大值 $\frac{1}{3\sqrt{3}}$，当 $x=y=z=\frac{1}{\sqrt{3}}$ 时取得

---

> **注**：本 Lecture 内容涵盖多元函数微分学的基本概念、计算方法和典型例题。建议结合《基础过关660题》第94-103题进行练习巩固。
