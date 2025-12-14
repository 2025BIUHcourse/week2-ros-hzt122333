Week2 实验报告
#一 实验目标
##1.掌握 Linux 基本命令，理解终端操作逻辑与常用操作方式。
##2.完成 Python 和 C++ 开发环境搭建，能够独立运行简单程序并进行调试。
##3.成功安装 ROS1 Noetic 版本，理解 ROS 基础结构与核心概念。
##4.学会创建 ROS 工作空间与功能包，熟悉基本通信机制的原理。
##5.实现 turtlesim 小乌龟的运行与控制，通过话题完成简单自动控制功能。
##6.初步掌握 launch 文件编写、命名空间使用及话题 remap 映射的基础应用。

#二、实验环境
操作系统:Ubuntu 20.04 LTS
开发工具:VSCode(含 Python/C++ 插件)
核心软件:Python3、GCC/G++、ROS1 Noetic
辅助工具:rqt_graph、rqt_plo

#三、实验内容与步骤
##（一）Linux 基础命令练习
执行命令:ps(查看进程)、kill [进程ID]（终止进程）
操作截图:c:\Users\lenovo\Desktop\微信图片_20251211100606_256_147.png
##（二）Python 与 C++ 编程练习
##1.Python HelloWorld 程序
运行截图:c:\Users\lenovo\Desktop\微信图片_20251211100607_257_147.png
##2.C++ 求和程序
编译命令:g++ [源码文件名].cpp -o [可执行文件名]
编译截图:c:\Users\lenovo\Desktop\微信图片_20251211100608_258_147.png
运行截图:c:\Users\lenovo\Desktop\微信图片_20251211100608_258_147.png
##（三）ROS1 安装验证
###1.环境搭建
核心步骤：按参考教程完成 ROS1 Noetic 安装、rosdep 初始化、环境变量配置
###2.功能验证
启动命令:roscore
roscore 启动截图:c:\Users\lenovo\Desktop\微信图片_20251211100610_260_147.png
节点列表命令:rosnode list
节点列表截图:c:\Users\lenovo\Desktop\微信图片_20251211100605_255_147.png
###3.环境变量检查
执行命令:echo $ROS_PACKAGE_PATH
环境变量截图:c:\Users\lenovo\Desktop\微信图片_20251211100605_255_147.png
##（四）CATKIN 工作空间与功能包创建
###1.工作空间搭建
执行命令:mkdir -p catkin_ws/src → cd catkin_ws → catkin_make
编译截图:c:\Users\lenovo\Desktop\微信图片_20251211100609_259_147.png
###2.功能包创建
执行命令:cd src → catkin_create_pkg beginner_tutorials roscpp rospy std_msgs
功能包截图：[c:\Users\lenovo\Desktop\微信图片_20251211100609_259_147.png
###3.HelloWorld 节点运行
运行命:catkin_make → source devel/setup.bash → rosrun beginner_tutorials [节点名]
运行截图:c:\Users\lenovo\Desktop\微信图片_20251211100610_260_147.png
##（五）Turtlesim 小乌龟基础控制
###1.键盘控制
启动命令:roscore → rosrun turtlesim turtlesim_node → rosrun turtlesim turtle_teleop_key
仿真窗口截图:c:\Users\lenovo\Desktop\微信图片_20251211100603_252_147.png
控制截图:c:\Users\lenovo\Desktop\微信图片_20251211100601_251_147.png
c:\Users\lenovo\Desktop\微信图片_20251211100604_253_147.png
###2.rostopic 控制
控制命令:rostopic pub /cmd_vel geometry_msgs/Twist "linear: {x: 0.5, y: 0.0, z: 0.0} angular: {x: 0.0, y: 0.0, z: 0.5}"
命令执行截图:c:\Users\lenovo\Desktop\微信图片_20251211100611_261_147.png
运动轨迹截图:c:\Users\lenovo\Desktop\微信图片_20251211100611_261_147.png
##（六）多乌龟 launch 配置与通信可视化
###1.launch 文件编写
文件名：[填写 launch 文件名，如 multi_turtles.launch]
###2.分别控制
启动命令:roslaunch [功能包名] [launch 文件名]
启动截图:c:\Users\lenovo\Desktop\微信图片_20251211100613_264_147.png
控制截图:c:\Users\lenovo\Desktop\微信图片_20251211100613_264_147.png
###3.通信可视化c:\Usc:\Users\lenovo\Desktop\微信图片_20251211100613_264_147.png
ers\lenovo\Desktop\微信图片_20251211100613_264_147.png
rqt_graph 命令:rqt_graph
通信关系截图：[此处预留截图位置，粘贴 rqt_graph 显示的通信关系图截图]
rqt_plot 命令:rqt_plot
速度曲线截图:c:\Users\lenovo\Desktop\微信图片_20251210204318_248_147.png
#四、实验结果与分析
##1.Linux 命令操作：所有文件管理、软件安装、进程控制命令均执行成功，截图清晰记录关键步骤，验证了对 Linux 终端基本操作的掌握。
##2.开发环境搭建：Python 与 C++ 环境配置完成，程序运行与 VSCode 调试功能正常，g++ 编译无报错，满足开发基础需求。
##3.ROS 安装与工作空间：ROS1 Noetic 启动正常，工作空间编译成功，功能包与 HelloWorld 节点运行稳定，ROS 基础环境搭建完成。
##4.小乌龟控制：键盘控制、rostopic 指令控制及程序自动画圆均实现预期效果，多乌龟 launch 文件运行正常，不同命名空间下的乌龟可独立控制。
##5.通信可视化：rqt_graph 清晰展示了多乌龟与节点间的通信关系，rqt_plot 准确绘制速度变化曲线，验证了命名空间与话题映射的有效性。
#五、实验总结与体会
本次实验系统学习了 Linux 基础操作、开发环境搭建及 ROS1 核心基础内容，从环境配置到实际功能实现，逐步掌握了 ROS 开发的基本流程。通过小乌龟控制与多实例配置，深入理解了 ROS 的话题通信机制、launch 文件用法及命名空间的作用。实验过程中，也遇到了 rosdep 初始化失败、工作空间编译报错等问题，通过查阅参考资料与调试排查，最终成功解决，提升了问题解决能力。后续将进一步巩固 ROS 通信机制，为更复杂的机器人开发打下基础。