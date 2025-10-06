线性代数的本质

课程大纲：

- 第1章：向量是什么？
- 第2章：向量的线性组合、张成的空间与基
- 第3章：线性变换与矩阵
- 第4章：线性变换复合与矩阵乘法
- 第5章：行列式
- 第6章：逆矩阵、列空间与零空间
- 第7章：点积与叉积
- 第8章：基变换
- 第9章：特征向量与特征值
- 第10章：抽象向量空间 

<br>

---

# 【1】向量究竟是什么？

1）向量定义1：指空间中的箭头，以原点为起点，有自己的方向与长度；

2）线性代数：围绕两种基本运算，包括向量加法与向量数乘；

2）向量定义2：指有序的数字列表（计算机视角）；

- 向量：看做是一种特定运动；
- 向量加法：把对应项目加起来；
- 向量数乘：向量与标量相乘指向量每个分量都乘以标量；

<br>

---

# 【2】向量的线性组合、张成的空间与基

1）通过改变所选择的标量，基向量与标量相乘，可以得到所有的二维向量； 

2）线性代数中的线性定义？以及线性与直线的区别？

- <font color=red>线性定义：在二维空间中，若固定一个向量的标量，而让另一个向量的标量自由变化，两个向量组合所产生向量的终点会描出一条直线</font>；
- 如果让两个基的标量同时变化：有3种情况；
  - 情况1：所产生的向量能够到达二维空间中的每一个点；
  - 情况2：当两个向量共线时（方向相同），则所产生向量的终点被限制在一条过原点的直线上；
  - 情况3：当两个向量都是零向量，则所产生向量的终点只能是原点或零点；

3）给定向量张成的空间定义：所有可以表示为给定向量线性组合的向量的集合；

【例】张成的空间：$\vec{v}$与$\vec{w}$  全部线性组合构成的向量集合称为张成的空间（<font color=red>张成可以理解为构成或组成</font>）
$$
a\vec{v}+b\vec{w}
$$
<br>

---

## 【2.1】向量与点

1）使用向量的终点表示该向量，因为起点全部是原点；

- 当考虑一个向量时，把该向量看做箭头；
- 当考虑多个向量时，把它们都看做点；

<br>

---

## 【2.2】三维空间中向量的张成（组合）

1）三维空间中两个向量张成的空间就是它们所有可能的线性组合；

2）<font color=red>三维空间中两个向量的张成定义：</font>改变线性组合中的两个标量，把缩放后的向量相加，然后跟着最终向量的终点走，这个终点会画出三维空间中某个过原点的平面；

- 确切的说，所有终点落在这个平面上的向量的集合是这两个向量张成的空间；

3）如果把两个向量增加到三个向量，那么这3个向量张成的空间是什么？

4）3个向量的线性组合：选择3个标量，对3个向量分别进行缩放，然后把结果相加，构成这3个向量张成的空间；

- 有两种情况：
  - 情况1：第3个向量恰好落在前面2个向量所张成的平面上，那么这3个向量张成的空间与前2个向量张成的空间相同； 
  - 情况2：第3个向量不落在前面2个向量所张成的平面上，那么这3个向量的组合能够表示三维空间中的任何一个向量；
    - <font color=red>当我们缩放第3个向量时，它会将前2个向量组成的平面沿它的方向来回移动，从而扫过整个三维空间</font>；

5）特殊情况

- 第3个向量落在前面2个向量张成的空间中，或2个向量恰好共线的情况，即一组向量中至少有一个向量是多余的，没有对张成空间做出任何贡献；

<br>

---

## 【2.3】线性相关

1）线性相关定义：有n个向量，移除其中一个而不减少其他n-1个向量张成的空间，则称n-1个向量是线性相关；

- 另一种定义是：其中一个向量是其他n-1个向量的线性组合，因为这个向量已经落在其他n-1个向量张成的空间中；

<br>

---

## 【2.5】线性无关

1）线性无关定义：n个向量给张成空间都添加了新的维度，则称这n个向量是线性无关的；

- 或者说，n个向量张成的空间的维度是n，则称这n个向量是线性无关的； 

![](./img/ch02_01_linear_independent.png)

<br>

---

## 【2.6】基的严格定义 

1）基的严格定义： 向量空间的一组基是张成该空间的一个线性无关向量集；

<br>

---

# 【3】矩阵与线性变换

## 【3.1】线性变换

1）线性变换解释：

- 变换：本质上是函数的花哨说法；
  - 使用变换这个术语：是在暗示以特定方式来可视化这一输入-输出关系；
  - 一种理解向量的函数的方法：使用运动；
- 理解变换：一个输入向量移动到输出向量的位置； 
  - 以二维空间为例，向量都用箭头表示会非常拥挤，一个技巧是把向量表示为向量终点，而不是一个箭头；用这种方法考虑所有输入向量都移动到输出向量的位置时，我们只用看空间中的所有点移动到其他点的位置；

2）线性变换定义（<font color=red>严格意义上说，线性变换是将向量作为输入与输出的一类函数；线性变换也可以看做是对空间的挤压伸展，它保持网格线平行且等距分布，并且保持原点不变；关键点在于，线性变换由它对空间的基向量的作用完全决定；在二维空间中，基向量就是</font> $\hat{i},\hat{j} $）：

- 各种各样对空间的变换是非常复杂多样的；如挤压或变形空间；但线性代数限制在一种特殊类型的变换上；这种变换更容易理解，称为线性变换；
- <font color=red>线性变换定义：若一个变换具有如下2个性质，则称该变换是线性变换；</font>
  - 性质1：直线在变换后仍然是直线，不能弯曲；
  - 性质2：原点必须保持固定；
- 总结：线性变换指保持网格线平行且等距分布的变换；

3）向量的线性变换过程：

![](./img/ch03_01_linear_transformer_process.png)

【图解】上述线性变换的公式如下：

【补充】

- 通过上述线性变换公式，给定任何一个输入向量，我们都知道线性变换后的位置； 

4）一个二维线性变换，仅由4个数字可以完全确定，即变换后$\hat{i}$的2个坐标与变换后$\hat{j}$的2个坐标；

- 通常：我们把这4个坐标值包装在一个2*2的格子中，称为为2\*2的矩阵。

$$
\begin{bmatrix}
3 & 2 \\ 
-2 & 1
\end{bmatrix}
$$

![](./img/ch03_02_2m2_matrix.png)

<br>

---

## 【3.2】线性变换矩阵（示例）

1）如果你有一个描述线性变换的2*2矩阵，以及一个给定向量。你想了解线性变换矩阵对这个给定向量的变换效果，则只需要取出给定向量的坐标，将它们与矩阵的特定列相乘，然后把结果相加即可，如下图所示。

![](./img/ch03_03_matrix_transform.png)

<br>

---

### 【3.2.1】线性变换过程（非常重要）

1）考虑变换后的第1个基向量坐标为(a,c)，变换后的第2个基向量坐标为(b,d)，我们让这个变换作用于输入向量$v=(x,y)$，则变换的计算过程如下：

变换后的2个基向量组成线性变换矩阵，如下：
$$
M=\begin{bmatrix}
a & b \\
c & d 
\end{bmatrix}
$$
输入向量v=$\begin{bmatrix}x \\ y\end{bmatrix}$

则线性变换矩阵M对向量v执行线性变换过程，如下：
$$
x\begin{bmatrix} a \\ c \end{bmatrix} + y\begin{bmatrix} b \\ d \end{bmatrix}=\begin{bmatrix} ax+by \\ cx+dy \end{bmatrix}
$$
2）上述过程也可以看做是<font color=red>矩阵向量乘法</font>，如下（矩阵放在向量左边，类似与一个函数）。
$$
\begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} =x\begin{bmatrix} a \\ c \end{bmatrix} + y\begin{bmatrix} b \\ d \end{bmatrix}=\begin{bmatrix} ax+by \\ cx+dy \end{bmatrix}
$$

3）矩阵列看做变换后的基向量；

4）矩阵向量乘法：看做是矩阵列的线性组合，其中组合系数是向量元素；

![](./img/ch03_04_matrix_column_vec.png)

<br>

---

### 【3.2.2】练习：用矩阵描述线性变换

1）例1：把坐标轴逆时针旋转90度；

- 旋转前的基向量：$\hat{i}=(1,0), \hat{j}=(0,1)$
- 旋转后的基向量：$\hat{i}=(0,1), \hat{j}=(-1,0)$
- 则变换后的基向量$\hat{i},\hat{j} $组成的线性变换矩阵$M=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}$

如果想计算任意向量$v=\begin{bmatrix}x \\ y\end{bmatrix}$在逆时针旋转90度后的位置，你只需要把该向量v与矩阵M相乘即可。
$$
\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}=x\begin{bmatrix}0 \\ 1 \end{bmatrix} + y\begin{bmatrix} -1 \\ 0 \end{bmatrix}=\begin{bmatrix}0*x-y \\ 1*x + 0*y \end{bmatrix}=\begin{bmatrix}-y \\ x \end{bmatrix}
$$
2）例2：剪切变换：

- $\hat{i}不变，坐标还是为(1,0)； \hat{j}移动到坐标(1,1)$；线性变换矩阵$M=\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}$
- 为计算任意向量$v=\begin{bmatrix}x \\ y\end{bmatrix}$在剪切变换后的位置，你只需要把该向量v与矩阵M相乘即可
- $\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}=x\begin{bmatrix}1 \\ 0\end{bmatrix}+y\begin{bmatrix} 1 \\ 1 \end{bmatrix}=\begin{bmatrix}x+y \\ y\end{bmatrix}$

<br>

---

3）例3：给定两个向量$v1=\begin{bmatrix}1 \\ 2\end{bmatrix}, v2=\begin{bmatrix} 3 \\ 1 \end{bmatrix}$，则这2个向量组成的线性变换矩阵$M=\begin{bmatrix} 1 & 3 \\ 2 & 1 \end{bmatrix}$ 表示的线性变换是怎样的？

- 把基向量$\hat{i}移动到(1,2)，\hat{j}移动到(3,1)$，且空间其他部分随着$\hat{i}与\hat{j} $一起移动，以保持网格线平行且等距分布；
  - 若变换（移动后）后的$\hat{i},\hat{j} $是线性相关的（列线性相关），则其中一个向量是另一个向量的倍数； 那么这个线性变换将整个二维空间挤压到一条直线上（也就是这2个线性相关向量所张成的一维空间）； 

<br>

---

## 【3.3】总结（矩阵就是空间的一种特定变换形式）

1）线性变换：是操作空间的一种手段； 它保持网格线平行且等距分布，并且保持原点不动；

- 线性变换：通过几个数字（即变换后基向量坐标）就可以描述清楚； 
  - 以这些坐标为列构成的线性变换矩阵为我们提供一种描述线性变换的语言； 
  - 而矩阵向量乘法就是计算线性变换作用于给定向量的一种途径；

2）<font color=red>矩阵：每当看到一个矩阵时，都可以把它解读为空间的一种特定变换（非常精辟）</font>；

- 当你把矩阵看做空间变换后，此后几乎所有主题，从矩阵乘法到行列式，基变换，特征值等都会更加容易理解；

<br>

---

# 【4】矩阵乘法与线性变换复合的联系 

## 【4.1】复合变换

1）复合变换：指多次线性变换；如逆时针旋转90度，再执行剪切变换；

- 旋转+剪切前的基向量：$\hat{i}=(1,0), \hat{j}=(0,1)$
- 旋转+剪切后的基向量：$\hat{i}=(1,1), \hat{j}=(-1,0)$
- 旋转+剪切后的复合变换矩阵$M=\begin{bmatrix}1 & -1 \\ 1 & 0 \end{bmatrix}$，复合线性变换矩阵M描述了先旋转再剪切的复合变换效应；

2）对于旋转+剪切复合线性变换，可以先左乘旋转矩阵，然后再左成剪切矩阵，如下。（<font color=red>两次线性变换结果，应该与一次复合矩阵变换的效果相同</font>）
$$
\begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix} \begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}\begin{bmatrix} x \\ y \end{bmatrix}=\begin{bmatrix}1 & -1 \\ 1 & 0\end{bmatrix}\begin{bmatrix} x \\ y \end{bmatrix}
$$


![](./img/ch04_01_composite_matrix.png)

<br>

3）复合线性变换矩阵：应该是旋转线性变换矩阵左乘剪切线性变换矩阵；

- <font color=red>两个矩阵相乘的几何意义（如旋转矩阵左乘剪切矩阵）：指两个线性变换的相继作用</font>；

 ![](./img/ch04_02_composite_matrix.png)

<br>

---

## 【4.2】矩阵乘法（基于矩阵向量乘法）

1）给定向量M1，M2，则M1左乘M2计算过程如下：
$$
M_1=\begin{bmatrix} 1 & -2 \\ 1 & 0 \end{bmatrix} , 
M_2=\begin{bmatrix} 0 & 2 \\ 1 & 0 \end{bmatrix}
$$
则M1左乘M2计算过程如下：
$$
M_2M_1=\begin{bmatrix} 0 & 2 \\ 1 & 0 \end{bmatrix}\begin{bmatrix} 1 & -2 \\ 1 & 0 \end{bmatrix} \\
$$
计算步骤如下：
第1步：$M_1$第1列$\begin{bmatrix} 1 \\ 1\end{bmatrix}$使用$M_2$表示的线性变换后得到如下结果。
$$
\begin{bmatrix} 0 & 2 \\ 1 & 0 \end{bmatrix}\begin{bmatrix} 1  \\ 1  \end{bmatrix} =1\begin{bmatrix} 0 \\ 1 \end{bmatrix}+1\begin{bmatrix} 2 \\ 0 \end{bmatrix}=\begin{bmatrix} 2 \\ 1 \end{bmatrix}
$$
第2步：$M_1$第2列$\begin{bmatrix} -2 \\ 0 \end{bmatrix}$使用$M_2$表示的线性变换后得到如下结果。

$$
\begin{bmatrix} 0 & 2 \\ 1 & 0 \end{bmatrix}\begin{bmatrix} -2  \\ 0  \end{bmatrix} =(-2)\begin{bmatrix} 0 \\ 1 \end{bmatrix}+0\begin{bmatrix} 2 \\ 0 \end{bmatrix}=\begin{bmatrix} 0 \\ -2 \end{bmatrix}
$$
综上：等式9的结果如下。
$$
M_2M_1=\begin{bmatrix} 0 & 2 \\ 1 & 0 \end{bmatrix}\begin{bmatrix} 1 & -2 \\ 1 & 0 \end{bmatrix} =\begin{bmatrix}2 & 0 \\ 1 & -2\end{bmatrix}
$$
<br>

---

### 【4.2.1】矩阵乘法的普适性

1）把上述矩阵$M_1$替换为符号$\begin{bmatrix} e & f \\ g & h\end{bmatrix}$，把$M_2$替换为$\begin{bmatrix}a & b \\ c & d\end{bmatrix}$。则$M_1$左乘$M_2$的计算过程如下：

第1步：$M_1$第1列左乘$M_2$如下：
$$
\begin{bmatrix}a & b \\ c & d\end{bmatrix}\begin{bmatrix}e \\ g\end{bmatrix}=e\begin{bmatrix}a \\ c\end{bmatrix}+g\begin{bmatrix}b \\ d\end{bmatrix}=\begin{bmatrix} ac+bg \\ ce+dg \end{bmatrix}
$$


第2步：$M_1$第2列左乘$M_2$如下：
$$
\begin{bmatrix} a & b \\ c & d \end{bmatrix}\begin{bmatrix} f \\ h \end{bmatrix}=f\begin{bmatrix}a \\ c\end{bmatrix}+h\begin{bmatrix} b \\ d\end{bmatrix}=\begin{bmatrix} af+bh \\ cf+dh \end{bmatrix}
$$
综上：$M_1$左乘$M_2$的乘积结果如下：
$$
M_2M_1=\begin{bmatrix}e & f \\ g & h\end{bmatrix}\begin{bmatrix}a & b \\ c & d\end{bmatrix}=\begin{bmatrix} ac+bg & af+bh \\ ce+dg & cf+dh \end{bmatrix}
$$


<br>

---

### 【4.2.2】矩阵乘法的意义

1）矩阵乘法的意义：指两个线性变换的相继作用；

- 如$M_2M_1 \not= M_1M_2$，就可以通过线性变换来解释；如先旋转再剪切与先剪切再旋转的线性变换效果明显不同，所以矩阵乘法的矩阵顺序不能交换；
- 证明矩阵乘法的基结合律，即$(AB)C=A(BC)$

<br>

---

## 【4.3】三维空间的线性变换

1）考虑如下图的三维空间的线性变换：

![](./img/ch04_05_3dim_transform.png)

【图解】$L(\vec{v})$是三维空间中的线性变换矩阵（或线性变化函数，对的，简单理解，矩阵就是函数）

2）三维空间中的线性变换：

- $L(\vec{v})$描述的线性变换（函数）移动三维空间中的所有点，保持网格平行且等距分布，并保持原点不动；
- 与二维空间相同：
  - 我们看到三维空间中的每一个点，实际上是用来代表以它为终点的向量； 而线性变换矩阵（函数）做的只是将输入向量input移动到对应输出向量output的位置；
  - 三维线性变换由基向量的去向完全决定；
- 我们有3个通用的标准基向量：x轴的单位向量是$\hat{i}$，y轴的单位向量是$\hat{j}$，z轴的单位向量是$\hat{k}$；

<br>

---

### 【4.3.1】跟踪基向量易于观察线性变换

1）三维空间的基向量：

变换前：
$$
\hat{i}=\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \hat{j}=\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \hat{k}=\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
$$


变换后：
$$
\hat{i}=\begin{bmatrix} 1 \\ 0 \\ -1 \end{bmatrix}, \hat{j}=\begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}, \hat{k}=\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}
$$
变换后的基向量组合到线性变换矩阵M（<font color=red>仅仅使用9个数字，这个矩阵就能够完全描述一个线性变换</font>）：
$$
M=\begin{bmatrix} 1 & 1 & 1 \\ 0 & 1 & 0 \\ -1 & 0 & 1\end{bmatrix}
$$
<br>

2）举例：三维空间的线性变换-沿着y轴旋转90度的线性变换（y轴基向量$\hat{j}$不变） 

变换后的基向量：
$$
\hat{i}=\begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}, \hat{j}=\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \hat{k}=\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}
$$
变换后的基向量组成的线性变换矩阵M：
$$
M=\begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ -1 & 0 & 0 \end{bmatrix}
$$


<br>

---

### 【4.3.2】三维空间向量变换后的位置推导

1）对于向量$\hat{v}=\begin{bmatrix} x \\y \\z\end{bmatrix}$，其经过M矩阵表示的线性变换后的位置是怎样的？推理过程与二维向量几乎相同；

- 向量$\hat{v}=\begin{bmatrix} x \\y \\z\end{bmatrix}$的<font color=red>每个坐标都可以看做是对相应基向量的缩放；把基向量缩放后的向量相加得到变换后的结果</font>。

2）综上，要找到向量v变换后的位置，则需要把向量v的每个坐标与变换矩阵对应列相乘再相加即可，如下。
$$
\begin{bmatrix} 0 &1 &2 \\ 3 & 4 &5 \\ 6 &7 &8\end{bmatrix}\begin{bmatrix} x \\ y \\z\end{bmatrix}=x\begin{bmatrix}0\\3\\6\end{bmatrix} + y\begin{bmatrix}1\\4\\7\end{bmatrix} + z\begin{bmatrix}2\\5\\8\end{bmatrix} =\begin{bmatrix}0x+y+2z \\3x+4y+5z \\6x + 7y + 8z\end{bmatrix}
$$
![](./img/ch04_06_3dim_in_out.png)

<br>

---

### 【4.3.3】三维空间矩阵乘法

1）三维空间矩阵乘法：先应用右侧矩阵变换，再应用左侧矩阵变换；

2）例：2个三维矩阵相乘；
$$
\begin{bmatrix}0 &-1 &2 \\ 5 &1 &5 \\ 1 &4 &-1\end{bmatrix}\begin{bmatrix}0 &1 &2 \\ 3 &4 &5 \\ 6 &7 &8\end{bmatrix}
$$
分为如下3个模块，分别计算向量$\begin{bmatrix}0\\3\\6\end{bmatrix}$,$\begin{bmatrix}1\\4\\7\end{bmatrix}$,$\begin{bmatrix}2\\5\\8\end{bmatrix}$经过线性变换矩阵作用后的结果。
$$
\begin{bmatrix}0 &-1 &2 \\ 5 &1 &5 \\ 1 &4 &-1\end{bmatrix}\begin{bmatrix}0 \\3\\6\end{bmatrix}=0\begin{bmatrix}0\\5\\1\end{bmatrix}+3\begin{bmatrix}-1\\1\\4\end{bmatrix}+6\begin{bmatrix}2\\5\\-1\end{bmatrix}=\begin{bmatrix}0-3+12 \\0+3+30 \\ 0+12-6 \end{bmatrix}=\begin{bmatrix}9 \\33 \\ 06 \end{bmatrix}
$$
<br>

---

# 【5】行列式































