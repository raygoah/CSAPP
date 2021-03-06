$$ B2U_{w}(\vec x) = \sum_{i=0}^{w-1}x_{i}2^{i} \\ 	B2T_{w}(\vec x) = \sum_{i=0}^{w-2}x_{i}2^{i} - x_{w-1}2^{w-1} \\ 
	B2U_{w}(\vec x) - B2T_{w}(\vec x) = 2^{w}x_{w-1} \\
	B2U_{w}(\vec x) =   B2T_{w}(\vec x) + 2^{w}x_{w-1}
$$ 

现在理解将补码表示的数转换为无符号数，则 $$ \vec x =  T2B_{w}(x) $$

有 $$  T2U_{w}(x) = B2U_{w}(T2B_{w}(x)) = x +  2^{w}x_{w-1} $$

分情况，x为负数时最高bit=1，否则为0

$$ T2U_{w}(x) = \{ \begin{aligned} x + 2^{w}, x > 0 \\ x , x <= 0  \end{aligned} $$

抽象理解：之前负数x的最高bit=1，代表的是$$-2^{w-1}$$ 现在解释为无符号数时代表$$2^{w-1}$$，所以增加了$$2^{w}$$。

---

$$ B2T_{w+1}([x_{w-1}, x_{w-1},x_{w-2}, ... , x_0])   \\	= -x_{w-1}2^{w} + \sum_{i=0}^{w-1}x_i2^{i}  \\
	= -x_{w-1}2^{w} + x_{w-1}2^{w-1}  + \sum_{i=0}^{w-2}x_i2^{i}  \\
	= -x_{w-1}2^{w-1} + \sum_{i=0}^{w-2}x_i2^{i}  \\
	= B2T_w([x_{w-1},x_{w-2}, ... , x_0])
$$

注意关键点：$$  2^w - 2^{w-1} = 2^{w-1} $$

---

$$	-2^{w-1} <= x < 2^{w-1}	$$中的每个数字x都有对应的加法逆元 $$+_w^tx$$
$$ +^t_wx=\{ \begin{aligned} -x, x > -2^{w-1}  \\ -2^{w-1}, x=-2^{w-1}       \end{aligned}  $$ 

我的理解：就是用 $$2^w-x$$ 按bit级别运算就是的了。如字长为4，分别求3和-8的逆元，这里-8就是TMin。

$$  3的逆元=\frac{10000}{-0011} = 1101 = -3   \\
-8的逆元 = \frac{10000}{-10000} = 10000 = -8 不变
$$

















