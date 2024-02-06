import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# 生成一个原始向量
v = np.array([1, 0, 0])

# 定义旋转矩阵（这里使用一个绕z轴的旋转）
theta = np.pi / 4  # 旋转角度
rotation_matrix = np.array([[np.cos(theta), -np.sin(theta), 0],
                            [np.sin(theta), np.cos(theta), 0],
                            [0, 0, 1]])

# 将原始向量应用旋转矩阵
rotated_v = np.dot(rotation_matrix, v)

# 创建一个三维坐标系
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# 绘制原始向量
ax.quiver(0, 0, 0, v[0], v[1], v[2], color='r', label='Original Vector')

# 绘制旋转后的向量
ax.quiver(0, 0, 0, rotated_v[0], rotated_v[1], rotated_v[2], color='b', label='Rotated Vector')

# 设置坐标轴范围
ax.set_xlim([-1, 1])
ax.set_ylim([-1, 1])
ax.set_zlim([-1, 1])

# 设置坐标轴标签
ax.set_xlabel('X')
ax.set_ylabel('Y')
ax.set_zlabel('Z')

# 显示图例
ax.legend()

# 显示图形
plt.show()
