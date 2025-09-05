# simulate
## 启动
* build/bin $ ./simulate 将模型拖入
* 后面加上文件路径来加载模型

## 操作
* ctrl+左键：调整姿态
* ctrl+右键：给一个力

* +和-控制仿真世界时间流逝速度
* ctrl+A：相机视角回正

## 快捷键
| key    | function        |
|--------|-----------------|
| F1     | help            |
| F2     | info            |
| F3     | profiler(监视器)   |
| F4     | Sensor Data     |
| F5     | 全屏              |
| F6     | 切换可视化坐标         |
| F7     | 实体名字坐标          |
| TAB    | 隐藏左侧工具栏         |
| Delete | 重置世界            |
| `      | geom最小外界矩形和碰撞状态 |
| Q      | Camera可视化       |
| W      | 世界网格化           |
| E      | Equality        |
| R      | 开关光线反射          |
| T      | 几何体透明化          |
| Y      | 测距可视化           |
| U      | 驱动器方向可视化        |
| I      | 转动惯量可视化         |
| O      | 调整物体姿态可视化       |
| P      | Contact可视化      |
| [ / ]  | 切换相机视角          |
| \      | Mesh Tree       |
| A      | auto connect    |
| D      | 只显示body         |
| S      | 画面亮度调整          |
| F      | 接触力大小及方向可视化     |
| G      | 迷雾              |
| J      | 关节方向可视化         |
| H      | 凸包可视化           |
| J      | 关节选装可视化         |
| K      | 关闭天空盒           |
| ；      | Skin可视化         |
| ‘      | 缩放转动惯量          |
| Z      | 灯光              |
| X      | Texture关闭       |
| C      | 接触点可视化          |
| V      | 肌腱可视化           |
| B      | 扰动力大小及方向可视化     |
| M      | 质心可视化           |
| ，      | Activation      |
| /      | haze地平线         |

# 仿真世界
## 世界根节点
```xml
<mujoco model="模型文件">
</mujoco>
```
## 仿真计算配置
### compiler节点
```xml
<compiler angle="radian/degree" autolimits="true"/>
```
compiler 节点中定义的包括angle(角度单位)，autolimits(受力限制)等，
一般按照上面写就行，规定角度单位是弧度制，受力限制开启。弧度制是机器人开发的常用单位制。
### option节点
```xml
<option timestep="0.002" gravity="0 0 -9.81" integrator="implicitfast"
density="1.225" viscosity="1.8e-5"/>
```
* timestep:计算机无法直接模拟“连续时间”，只能将时间拆分成离散的“小步”（timestep）
* gravity:官方推荐默认，不推荐修改
* integrator(数值积分器)：可选：Euler(欧拉法)，RK4（四阶龙格-库塔法）,implicit（快速隐式法），implicitfast(快速隐式法)，默认值：Euler