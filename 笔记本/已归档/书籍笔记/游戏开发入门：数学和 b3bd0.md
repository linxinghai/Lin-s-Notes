# 游戏开发入门：数学和物理

Created: April 13, 2022 10:32 PM

# 笛卡尔坐标系和极坐标系

2D笛卡尔数学 从2D到3D processing及其坐标系 极坐标系

# 向量

向量与标量

 向量的定义

 向量的表达

 向量与点

 向量运算

 点乘->夹角 叉乘->垂直 

pVector

```cpp
class Vector{
	public:
		x,
		y,
		z,
}

public PVector(float x,float y)
{
	this.x = x;
	this.y = y;
	this.z = 0;
}
```

add函数

```cpp
static public PVector add(PVector v1,PVector v2,PVector target)
{
	if(target == null){
		target = new PVector(v1.x+v2.x,v1.y+v2.y,v1.z+v2.z);
	}else{
		target.set()
	}
return target;
}
```

sub函数

normalize函数

mult函数

dot函数

cross函数

# 矩阵运算

矩阵的数学定义 向量和矩阵 矩阵的几何意义 PMatrix

# 矩阵和仿射变换

变换物体和变换坐标系 齐次坐标和齐次矩阵 平移 缩放 旋转 组合变换

# 几何图元

直线,线段和射线 圆和球 平面 三角形 多边形 矩形边界框

# 几何检测

直线上的最近点 圆或球上的最近点 平面上的最近点 直线的两两相交 直线与圆或球的相交 直线与平面的相交 圆或球的两两相交 球与平面的相交

# 线性运动

速度 加速度 运动方程 抛体运动

# 牛顿力学

牛顿三大定律 力

# 动量和碰撞

与静止物体的碰撞 动量定理 线性碰撞建模

# 旋转运动

角运动 旋转力学

# 粒子系统基础

粒子系统的组成 功能模块 更新循环阶段 单个粒子的模拟 粒子系统的模拟 定义粒子系统 与力的整合 复杂粒子