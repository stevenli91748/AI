* [一份 AI Robotics 第一个月逐日学习计划（Day 1–30）和 Ubuntu/ROS 2 安装命令及第一个 ROS 2 机器人项目完整代码结构](https://github.com/stevenli91748/AI/blob/master/AI%20%E6%9C%BA%E5%99%A8%E4%BA%BA/AI%20Robotics%20%E7%AC%AC%E4%B8%80%E4%B8%AA%E6%9C%88%E9%80%90%E6%97%A5%E5%AD%A6%E4%B9%A0%E8%AE%A1%E5%88%92%EF%BC%88Day%201%E2%80%9330%EF%BC%89.md)





如果从美国机器人公司的实际开发视角来看，现在做机器人已经不是“学一个机器人编程语言”这么简单，而是一个完整技术栈：

C++/Python + ROS 2 + Robot Control + Perception + Planning + AI + Simulation + Hardware

其中我认为你最应该先理解的是：

ROS 2 是机器人软件的骨架，C++/Python 是开发语言，Isaac Sim/Gazebo/MuJoCo 是模拟环境，AI/ML/RL 是智能层。

一、2026 年美国机器人开发的主流架构

可以先把机器人想象成下面这个系统：

                 ┌───────────────────────┐
                 │       AI / LLM        │
                 │ Vision / VLM / Agent  │
                 └───────────┬───────────┘
                             ↓
                 ┌───────────────────────┐
                 │   Task / Behavior     │
                 │ Planning / Decision   │
                 └───────────┬───────────┘
                             ↓
                 ┌───────────────────────┐
                 │      ROS 2            │
                 │ Nodes / Topics /      │
                 │ Services / Actions     │
                 └───────────┬───────────┘
                             ↓
        ┌────────────────────┼────────────────────┐
        ↓                    ↓                    ↓
   Perception            Navigation            Control
        ↓                    ↓                    ↓
 Camera/LiDAR          SLAM / Nav2          PID / MPC
        ↓                    ↓                    ↓
        └────────────────────┼────────────────────┘
                             ↓
                    Robot Hardware
                             ↓
             Motors / Sensors / Actuators

这就是你应该建立的机器人软件架构思维。

二、第一核心：ROS 2

如果你想进入美国机器人开发，我建议把 ROS 2 放在第一优先级。

ROS 2 不是一种编程语言。

它更像：

机器人操作系统级的软件通信框架。

官方文档：

ROS 2 Documentation

例如一个机器人有：

Camera
   ↓
Camera Node
   ↓
/camera/image
   ↓
Vision Node
   ↓
/object_detection
   ↓
Planner
   ↓
/cmd_vel
   ↓
Motor Controller

每一个功能都可以是一个 Node。

三、ROS 2 最重要的几个概念

你学习 ROS 2，先不要一上来学几百个 API。

先掌握这 6 个：

1. Node

一个机器人程序模块。

例如：

camera_node
lidar_node
navigation_node
motor_node
vision_node
2. Topic

机器人模块之间传递实时数据。

例如：

/camera/image
/lidar/scan
/robot/odom
/cmd_vel

可以理解成：

Publisher
    ↓
   Topic
    ↓
Subscriber
3. Service

适合一次性的请求/响应。

Client
  ↓
Service
  ↓
Server

例如：

“打开机械臂夹爪。”

4. Action

适合长时间运行的任务。

例如：

“让机器人移动到厨房。”

可以：

Goal
 ↓
Navigation
 ↓
Feedback
 ↓
Result
5. TF2

这个非常重要。

机器人需要知道：

World
 ↓
Map
 ↓
Odom
 ↓
Base
 ↓
Camera
 ↓
Robot Arm
 ↓
Gripper

这就是机器人不同坐标系之间的关系。

6. Package

机器人项目通常组织成：

robot_project/
├── package.xml
├── setup.py
├── src/
├── launch/
├── config/
├── urdf/
└── meshes/
四、机器人到底用什么语言？

这是一个非常重要的问题。

第一名：C++

机器人底层控制非常重要。

例如：

Motor
Sensor
Controller
Planner
ROS 2

大量高性能机器人软件使用 C++。

原因：

性能高
实时性好
内存控制
硬件接口成熟
ROS 2 支持非常好
五、第二语言：Python

现在机器人开发非常需要 Python。

尤其是：

AI
Computer Vision
Machine Learning
Deep Learning
Reinforcement Learning
Data Processing
Simulation

例如：

camera_data
    ↓
Python
    ↓
PyTorch
    ↓
Object Detection
    ↓
ROS 2
    ↓
Robot

所以我给你的建议是：

C++ + Python 两个都学。

不是二选一。

六、第三类：机器人描述语言

这里很多初学者容易搞混。

机器人不是只写 Python/C++。

还需要描述：

“机器人长什么样、关节在哪里、质量是多少、碰撞模型是什么。”

常见：

URDF
robot.urdf

描述：

Link
Joint
Sensor
Inertia
Collision
Visual

例如：

Base
 ↓
Joint1
 ↓
Arm1
 ↓
Joint2
 ↓
Arm2
 ↓
Gripper
七、机器人开发还有一个非常重要的语言：USD

如果你进入 NVIDIA Isaac 生态，USD 会越来越重要。

USD 是：

Universal Scene Description

Isaac Sim 使用 USD 作为核心场景/资产描述格式。Isaac Sim 可以导入包括 URDF、MJCF 等机器人模型，并通过 USD 组织场景。

所以未来你会看到：

URDF
   ↓
Isaac Sim
   ↓
USD
   ↓
Simulation
八、机器人真正的“智能”在哪里？

可以分成 5 层：

Level 5   AI / LLM / VLM
              ↑
Level 4   Task Planning
              ↑
Level 3   Motion Planning
              ↑
Level 2   Control
              ↑
Level 1   Hardware
九、Level 1：Hardware

机器人最底层：

Motor
Servo
Encoder
IMU
Camera
LiDAR
Force Sensor
GPS

例如机械臂：

CPU
 ↓
Motor Controller
 ↓
Servo
 ↓
Joint
 ↓
Arm
十、Level 2：Control

机器人控制非常核心。

例如：

PID
Target Position
       ↓
     Error
       ↓
      PID
       ↓
Motor Command

你至少应该理解：

PID
Forward Kinematics
Inverse Kinematics
Dynamics
Trajectory
Joint Control

再进一步：

MPC
Whole Body Control
Torque Control
十一、Level 3：Motion Planning

例如机械臂：

目标：

把杯子从桌子左边
移动到桌子右边

不是简单：

move(x,y,z)

而是：

Target Pose
     ↓
Inverse Kinematics
     ↓
Collision Checking
     ↓
Motion Planning
     ↓
Trajectory
     ↓
Controller
     ↓
Motor

常见技术：

MoveIt 2

十二、移动机器人则是另一套体系

比如：

Robot
 ↓
LiDAR
 ↓
SLAM
 ↓
Map
 ↓
Localization
 ↓
Path Planning
 ↓
Nav2
 ↓
Motor

ROS 2 生态中：

Nav2

是非常重要的移动机器人导航框架。

十三、Level 4：Computer Vision

机器人需要“看”。

例如：

Camera
 ↓
Image
 ↓
Computer Vision
 ↓
Object Detection
 ↓
Object Tracking
 ↓
3D Position
 ↓
Robot

现在常见：

OpenCV
PyTorch
YOLO
Depth Camera
LiDAR
Point Cloud
十四、Level 5：AI / VLM / LLM

这是最近机器人领域变化最大的部分。

传统机器人：

if obstacle:
    stop

AI Robot：

Camera
 ↓
Vision Model
 ↓
VLM
 ↓
Understand Scene
 ↓
LLM / Agent
 ↓
Task Planning
 ↓
ROS 2
 ↓
Robot

例如你告诉机器人：

“把桌子上的红色杯子拿给我。”

机器人可能执行：

语音
 ↓
LLM
 ↓
理解任务
 ↓
VLM
 ↓
识别红色杯子
 ↓
3D Position
 ↓
Motion Planning
 ↓
MoveIt
 ↓
机械臂
 ↓
Grasp
 ↓
拿起杯子

这就是现在所谓的：

Embodied AI / Physical AI

十五、现在机器人模拟环境非常重要

真实机器人很贵。

所以开发流程通常：

Simulation
     ↓
Test
     ↓
Train
     ↓
Validate
     ↓
Real Robot

而不是：

直接买机器人
     ↓
直接测试
     ↓
机器人撞墙
     ↓
$$$$
十六、三大模拟环境

我建议你重点认识：

Simulator	最适合
NVIDIA Isaac Sim	AI机器人、工业机器人、数字孪生、GPU仿真
Gazebo	ROS 2机器人开发
MuJoCo	Robotics Research / RL / 控制
十七、Isaac Sim

如果你以后想做：

AI + Robot

我非常推荐你重点学习 NVIDIA Isaac Sim。

NVIDIA Isaac Sim Documentation

它提供物理仿真、机器人、摄像头、LiDAR、接触传感器等能力，并支持 ROS 2 桥接。

架构：

Isaac Sim
│
├── Physics
├── Robot
├── Camera
├── LiDAR
├── Environment
├── Sensors
├── ROS 2
└── Python

而且现在的 Isaac Sim 可以直接用 Python 控制机器人。官方教程就提供了用 Python 添加和控制移动机器人的流程。

十八、Isaac Lab

如果你想进一步做：

机器人 + AI + Reinforcement Learning

那么：

Isaac Sim → Isaac Lab

是非常值得学习的路线。

Isaac Lab 是 NVIDIA 面向机器人学习的框架，支持 reinforcement learning、imitation learning，并支持 sim-to-real 等工作流。

结构：

Isaac Sim
    ↓
Isaac Lab
    ↓
RL / Imitation Learning
    ↓
Robot Policy
    ↓
Real Robot
十九、Gazebo

Gazebo 是 ROS 生态非常经典的机器人仿真环境。

官方：

Gazebo

典型：

ROS 2
 ↓
Gazebo
 ↓
Robot
 ↓
Sensor
 ↓
ROS 2

如果你的目标是：

ROS 2机器人软件工程师

Gazebo 非常值得学习。

注意：现在不要去重点学已经 EOL 的 Gazebo Classic；官方资料也明确提示 Classic 已被新的 Gazebo 取代。

二十、MuJoCo

MuJoCo 特别适合：

Robot Control
RL
Simulation
Research
Biomechanics

它是一个高性能物理引擎，重点处理多关节系统和接触动力学。

官方：

MuJoCo Documentation

架构：

Python
 ↓
MuJoCo
 ↓
Physics
 ↓
Robot
 ↓
RL
二十一、我给你推荐的现代机器人技术栈

如果你是从软件开发背景转机器人，我会这样安排：

                    Robotics
                       │
          ┌────────────┴────────────┐
          ↓                         ↓
      Software                    AI
          │                         │
       ROS 2                     PyTorch
          │                         │
      C++ / Python             Vision / VLM
          │                         │
       Control                    LLM
          │                         │
       Planning                  Agent
          │                         │
          └────────────┬────────────┘
                       ↓
                  Simulation
                       │
             ┌─────────┼─────────┐
             ↓         ↓         ↓
          Isaac Sim  Gazebo    MuJoCo
             │
          Isaac Lab
             │
             ↓
         Real Robot
二十二、如果让我给你排学习优先级

考虑到你已经在学习 Python、FastAPI、LLM、RAG、Agent、MCP、PostgreSQL、Docker、AWS，我不会让你从机械工程重新学起。

我建议：

第一阶段

Python

↓

Linux

↓

C++基础

↓

ROS 2

第二阶段
ROS 2
 ↓
Node
 ↓
Topic
 ↓
Service
 ↓
Action
 ↓
TF2
 ↓
URDF
 ↓
RViz
第三阶段
Robot Control
 ↓
Kinematics
 ↓
PID
 ↓
Motion Planning
 ↓
MoveIt 2
 ↓
Nav2
第四阶段
Isaac Sim
 ↓
USD
 ↓
Robot Simulation
 ↓
Sensors
 ↓
ROS 2 Bridge
第五阶段
PyTorch
 ↓
Computer Vision
 ↓
Object Detection
 ↓
Depth
 ↓
3D / Point Cloud
第六阶段
VLM
 ↓
LLM
 ↓
Agent
 ↓
MCP
 ↓
Task Planning
 ↓
Robot
第七阶段
Isaac Lab
 ↓
Reinforcement Learning
 ↓
Imitation Learning
 ↓
Sim-to-Real
二十三、最终形成的“美国机器人 AI Engineer”架构

这是我最建议你记住的一张图：

                 HUMAN
                   │
             Voice / Text
                   ↓
             ┌───────────┐
             │ LLM / VLM │
             └─────┬─────┘
                   ↓
             ┌───────────┐
             │ AI Agent  │
             └─────┬─────┘
                   ↓
             Task Planning
                   ↓
             ┌───────────┐
             │   ROS 2   │
             └─────┬─────┘
                   │
        ┌──────────┼──────────┐
        ↓          ↓          ↓
    Vision      Planning    Control
        ↓          ↓          ↓
    Camera      MoveIt      PID/MPC
    LiDAR       Nav2
        │          │          │
        └──────────┼──────────┘
                   ↓
              Robot Hardware
                   │
          ┌────────┼────────┐
          ↓        ↓        ↓
        Motor    Sensor   Actuator

如果你的目标是“机器人 + AI”，我认为最值得你重点押注的是：

Python + C++ → ROS 2 → Isaac Sim → PyTorch → Computer Vision → VLM/LLM → Agent → Isaac Lab → Sim-to-Real

而不是同时去学十几个机器人框架。

你尤其应该注意

ROS 2 ≠ AI。
Isaac Sim ≠ ROS 2。
LLM ≠ Robot Controller。

真正的现代机器人系统是把它们组合起来：

AI负责“理解/决策” → ROS 2负责“机器人软件通信” → Planner负责“怎么走” → Controller负责“怎么动” → Hardware负责“真正执行”。

这也是你从 AI 软件开发转向机器人开发时，最需要建立的架构思维。

如果你的目标是开发 AI 机器人，而不是单纯学习机器人编程，我建议不要一开始买工业机器人。最适合的是 ROS 2 + NVIDIA Jetson + 深度相机 + 四轮/履带底盘，然后逐步升级到机械臂和人形机器人。

我建议的开发路线
阶段	推荐机器人	主要开发内容	难度
① 入门	四轮移动机器人	ROS 2、SLAM、导航、避障、AI Vision	⭐⭐
② AI	Jetson + RGB-D机器人	YOLO、VLM、目标识别、跟踪	⭐⭐⭐
③ 操作	机械臂	视觉抓取、运动规划、Manipulation	⭐⭐⭐⭐
④ 高级	轮式机械臂	Navigation + Vision + Manipulation	⭐⭐⭐⭐⭐
⑤ 前沿	人形机器人	VLA、全身控制、双臂操作	⭐⭐⭐⭐⭐
如果让我给你选一台

我会优先选择：

1. AgileX / ROS 2 移动机器人底盘
适合学习真实机器人开发：

ROS 2
Python / C++
LiDAR
SLAM
Nav2
Docker
Jetson
OpenCV
YOLO
AI Agent
5

2. Unitree Go2

如果你的目标是进一步做四足 AI Robot，Go2 很值得考虑：

ROS 2
Jetson
深度相机
LiDAR
SLAM
Vision AI
LLM/VLM
Autonomous Navigation↳
6

3. SO-ARM100 / SO-ARM101

如果重点是AI 机械臂 / Vision-Language-Action（VLA），这个方向非常适合个人开发：

ROS 2
Python
PyTorch
OpenCV
Camera
Object Detection↳
Robot Learning↳
Imitation Learning↳
VLA
5
如果你的最终目标是 AI Agent + Robot

我反而建议你不要直接买人形机器人。

可以按照这个架构开发：

                LLM / VLM
                   │
              AI Agent
                   │
        ┌──────────┴──────────┐
        │                     │
   Task Planner          Robot Skills
        │                     │
        └──────────┬──────────┘
                   │
              ROS 2
                   │
       ┌───────────┼───────────┐
       │           │           │
     Nav2       MoveIt 2    Perception
       │           │           │
    LiDAR       Robot Arm   Camera
       │           │           │
       └───────────┼───────────┘
                   │
             Jetson Orin
                   │
                Robot

你的第一台开发机器人，我推荐：

Jetson Orin + ROS 2 + LiDAR + RGB-D Camera + 四轮移动底盘

这是目前非常适合作为AI Robot 开发测试平台的组合。

然后第二台再增加：

SO-ARM101 机械臂

最终形成：

移动底盘 + 机械臂 + 摄像头 + LiDAR + Jetson + ROS 2 + VLM/LLM + Agent

这套平台实际上已经可以做真正的 AI Robotics 项目，而不仅仅是 Arduino 式机器人。

如果你准备认真进入 AI Robot 开发，
我可以下一步直接给你整理一份 「2026 美国 AI Robotics 开发完整技术栈 + 推荐机器人硬件（$500 / $1,500 / $3,000 / $10,000 四档）」，包括 ROS 2、Python/C++、Jetson、Gazebo/Isaac Sim、MoveIt 2、OpenCV、YOLO、VLM、VLA、Agent，以及每个阶段该买什么。


可以。按 2026 年美国 AI Robotics 的实际开发方向，如果你准备自己搭建开发平台，我建议不要把重点放在“买一台昂贵机器人”，而是建立一套 Simulation → ROS 2 → Edge AI → Real Robot → VLA/Agent 的完整体系。

目前 NVIDIA 的机器人路线已经把 ROS 2 + Isaac Sim + Isaac ROS + Jetson + HIL（Hardware-in-the-Loop） 串起来；Isaac Sim 目前推荐 Ubuntu 24.04 + ROS 2 Jazzy。

一、2026 AI Robotics 完整技术栈
                    ┌─────────────────────────────┐
                    │       LLM / VLM / VLA       │
                    │ GPT / Gemini / Claude       │
                    │ Vision-Language-Action      │
                    └──────────────┬──────────────┘
                                   │
                            AI Robot Agent
                                   │
                    ┌──────────────┴──────────────┐
                    │                             │
              Task Planning                  Robot Skills
                    │                             │
                    └──────────────┬──────────────┘
                                   │
                            ROS 2 Middleware
                                   │
          ┌────────────────────────┼──────────────────────┐
          │                        │                      │
       Perception              Navigation            Manipulation
          │                        │                      │
     Camera / LiDAR              Nav2                 MoveIt 2
     YOLO / VLM                  SLAM                  IK / Motion
          │                        │                      │
          └────────────────────────┼──────────────────────┘
                                   │
                         NVIDIA Isaac ROS
                                   │
                           Jetson Edge AI
                                   │
                         Real Robot Hardware
二、最核心的 10 层
层	技术	优先级
1	Python	⭐⭐⭐⭐⭐
2	C++	⭐⭐⭐⭐⭐
3	Linux / Ubuntu	⭐⭐⭐⭐⭐
4	ROS 2	⭐⭐⭐⭐⭐
5	Docker	⭐⭐⭐⭐⭐
6	OpenCV / PyTorch	⭐⭐⭐⭐⭐
7	Nav2 / SLAM	⭐⭐⭐⭐⭐
8	MoveIt 2	⭐⭐⭐⭐
9	Isaac Sim / Isaac ROS	⭐⭐⭐⭐⭐
10	VLM / VLA / Agent	⭐⭐⭐⭐⭐

如果你只问我“最重要的是什么”：

Python + C++ + Linux + ROS 2 + Docker + PyTorch + OpenCV + Nav2 + MoveIt 2 + Isaac Sim + Jetson

三、操作系统
首选：Ubuntu 24.04

2026 年我建议直接：

Ubuntu 24.04 LTS + ROS 2 Jazzy

NVIDIA 当前 Isaac Sim 文档明确推荐 Ubuntu 24.04 + ROS 2 Jazzy。

不要从 ROS 1 开始。

不要为了学习 AI Robotics 而把主要环境放在 Windows。

你的开发电脑：

Ubuntu 24.04
       │
       ├── ROS 2 Jazzy
       ├── Docker
       ├── NVIDIA Driver
       ├── CUDA
       ├── PyTorch
       ├── Isaac Sim
       ├── Isaac ROS
       ├── Gazebo
       └── VS Code
四、编程语言
第一：Python

AI Robotics 中 Python 非常重要。

主要用于：

AI
Computer Vision↳
VLM
VLA
Agent
ROS 2 Python↳
数据处理
模型训练
推理
自动化测试

重点：

Python
 ├── NumPy
 ├── OpenCV
 ├── PyTorch
 ├── Transformers
 ├── ROS 2 rclpy
 ├── FastAPI
 └── AI Agent
第二：C++

机器人底层控制仍然离不开 C++。

重点：

C++
 ├── ROS 2 rclcpp
 ├── sensor drivers
 ├── controller
 ├── motion planning
 ├── real-time
 ├── perception
 └── hardware interface

所以你的学习比例可以：

Python 60% + C++ 40%

五、ROS 2——整个系统的核心

ROS 2 不应该理解成一个“机器人操作系统”。

更准确地说：

ROS 2 = Robotics Middleware + Communication + Tools + Ecosystem

它负责：

Camera
   ↓
ROS Topic
   ↓
Perception
   ↓
ROS Topic
   ↓
Planner
   ↓
ROS Action
   ↓
Controller
   ↓
Motor

重点学习：

ROS 2
Nodes
Topics
Services
Actions
Parameters
TF2
Launch
URDF
Xacro
rosbag
QoS
DDS
Lifecycle Nodes↳
Composition


六、机器人导航

如果你第一台机器人是移动机器人，重点学习：

Nav2
Camera / LiDAR
       ↓
      SLAM
       ↓
    Map / TF
       ↓
      Nav2
       ↓
Global Planner
       ↓
Local Planner
       ↓
Controller
       ↓
Motor

核心技术：

SLAM
Localization
Mapping
Path Planning↳
Obstacle Avoidance
AMCL
Costmap
Behavior Tree
七、机械臂

如果以后做机器人抓东西：

MoveIt 2
Camera
   ↓
Object Detection
   ↓
3D Position
   ↓
MoveIt 2
   ↓
IK
   ↓
Motion Planning
   ↓
Collision Checking
   ↓
Robot Arm

重点：

Forward Kinematics
Inverse Kinematics
Collision Detection
Motion Planning
Trajectory
Grasping
Servo
八、Computer Vision

这一层是 AI Robot 的眼睛。

推荐：

OpenCV
   +
PyTorch
   +
YOLO
   +
Depth Camera
   +
3D Vision

学习顺序：

Level 1
OpenCV
Image Processing↳
Camera Calibration
Level 2
Object Detection
YOLO
Segmentation
Tracking
Level 3
Depth
Point Cloud
3D Object Detection
Level 4
VLM

例如：

Camera
   ↓
Image
   ↓
VLM
   ↓
"What objects are on the table?"
   ↓
Objects + semantic understanding
九、3D / Point Cloud

你之前问过三维点云，这个方向非常值得学。

推荐：

Open3D
PCL
Depth Camera↳
LiDAR
Point Cloud
3D Reconstruction
ICP
SLAM

尤其是：

Open3D + ROS 2 + RGB-D Camera

非常适合个人 AI Robotics 项目。

十、NVIDIA Robotics 技术栈

这是我认为你在 2026 年应该重点关注的一条路线。

                 NVIDIA
                    │
        ┌───────────┼───────────┐
        │           │           │
    Jetson       Isaac ROS    Isaac Sim
        │           │           │
     Edge AI    ROS acceleration Simulation
        │           │           │
        └───────────┼───────────┘
                    │
                  ROS 2

NVIDIA 的 Isaac ROS 是一组面向自主机器人的高性能、低延迟 ROS 2 包，并针对 Jetson 等 NVIDIA 平台进行了加速。

十一、Isaac Sim

我建议：

Gazebo 要学，但 Isaac Sim 要重点学。

Isaac Sim 可以做：

Robot Simulation↳
Physics
Camera
LiDAR
Synthetic Data↳
Navigation
Manipulation
Reinforcement Learning
ROS 2 Integration
HIL

而且 NVIDIA 当前文档直接支持：

ROS 2 + Nav2 + MoveIt 2 + Reinforcement Learning。

十二、Gazebo 还要不要学？

要。

但是：

Gazebo       → ROS 2 基础
Isaac Sim    → 高级 AI Robotics

我的建议：

Gazebo 学到能够建立机器人、传感器、SLAM、Nav2 就够了。

然后把主要精力转向：

Isaac Sim

十三、AI / VLM / VLA

这是 2026 年和传统机器人开发最大的区别。

传统机器人：

if obstacle:
    turn_left()

AI Robot：

Camera
   ↓
VLM
   ↓
理解环境
   ↓
LLM / Agent
   ↓
Task Planning
   ↓
Robot Skills
   ↓
ROS 2
   ↓
Robot
十四、VLA 是重点

VLA：

Vision + Language + Action

例如：

用户：

“把桌上的红色杯子拿给我。”

机器人：

Camera
 ↓
Vision
 ↓
VLM
 ↓
识别红色杯子
 ↓
3D Position
 ↓
Task Planning
 ↓
Motion Planning
 ↓
Arm
 ↓
Grasp
 ↓
Deliver

这才是真正意义上的：

AI Robot

十五、Agent 在机器人里面怎么用？

我建议你不要让 LLM 直接控制电机。

错误架构：

LLM
 ↓
Motor

正确架构：

LLM / VLM
     ↓
Robot Agent
     ↓
Task Planner
     ↓
Robot Skills
     ↓
ROS 2
     ↓
Controller
     ↓
Motor

例如 Robot Skills：

navigate_to()
find_object()
pick_object()
place_object()
open_door()
follow_person()
dock()

Agent 只负责：

决定调用哪个 Skill

而不是直接控制：

PWM / Motor / Joint Torque
↳

十六、推荐 AI Robotics 硬件

这里我给你分成 4 个预算。

$500 左右：学习平台

核心：

小型移动底盘
+
Jetson Orin Nano Super
+
RGB-D Camera
+
2D LiDAR

Jetson Orin Nano Super 是很合适的入门 Edge AI 平台，目前零售结果大约在 $500–600 档，但不同供应商价格差异较大。

NVIDIA Jetson Orin Nano Super Developer Kit
$499.99
•
AAAWave

配合 RPLIDAR：

SLAMTEC RPLIDAR A1M8
$158.99 · newegg.com

适合：

ROS 2
SLAM
Nav2
OpenCV
YOLO
Object Tracking↳
Edge AI
十七、$1,500 左右：我最推荐

这是我最建议你的预算。

                    $1,500
                       │
       ┌───────────────┼───────────────┐
       │               │               │
   Mobile Base       Jetson        Camera/LiDAR
       │               │               │
    ROS 2          Isaac ROS       Perception
       │               │               │
       └───────────────┼───────────────┘
                       │
                   AI Robot

可以考虑：

Unitree Go2

Unitree 官方目前将 Go2 定位为 AI + Robot 平台，官方页面显示起价约 $1,600，并提供 4D LiDAR 等能力。

5

而且 Unitree 官方提供：

unitree_sdk2
unitree_ros2

其中 unitree_ros2 用于 Go2/B2 等机器人的 ROS 2 开发。

所以如果你想直接进入“四足机器人 + AI”，Go2 是很好的测试平台。

十八、机械臂平台

如果重点是：

AI + Robot Arm

我建议：

SO-ARM101

它比直接买工业机械臂更适合个人学习：

Camera
 ↓
VLM
 ↓
Object Detection
 ↓
3D Position
 ↓
Robot Policy
 ↓
SO-ARM101

重点研究：

Imitation Learning↳
Robot Learning
Vision-based Manipulation
VLA
Teleoperation
十九、$3,000–5,000：专业个人实验室

如果你认真做 AI Robotics，我会这样搭：

                 Developer PC
              NVIDIA GPU Workstation
                       │
                  Isaac Sim
                       │
                 ROS 2 Jazzy
                       │
              ┌────────┴────────┐
              │                 │
         Mobile Robot       Robot Arm
              │                 │
           Jetson            Jetson
              │                 │
          Camera/LiDAR      RGB-D Camera
              │                 │
              └────────┬────────┘
                       │
                 AI Robot Agent

PC 端负责：

Isaac Sim
Training
VLA
LLM
Simulation↳

Jetson 负责：

Real-time inference
Perception
ROS 2
Control
Edge AI
二十、$10,000+：完整 AI Robotics Lab

如果以后做专业研发：

                 AI Robotics Lab
                        │
        ┌───────────────┼────────────────┐
        │               │                │
     Simulation      Mobile           Manipulation
        │             Robot               │
   Isaac Sim        Go2/UGV           Robot Arm
        │               │                │
        └───────────────┼────────────────┘
                        │
                   Jetson Cluster
                        │
                 ROS 2 / Isaac ROS
                        │
              VLM / VLA / Agent
                        │
                 Data Collection
                        │
                Robot Learning
二十一、我最推荐你的硬件组合

如果是你现在开始学，我不会让你一次买很多东西。

第一阶段

PC + Jetson + 小型移动机器人

PC
 │
 ├── Ubuntu 24.04
 ├── ROS 2 Jazzy
 ├── Docker
 ├── Isaac Sim
 └── PyTorch
       │
       ↓
Jetson Orin Nano Super
       │
       ├── ROS 2
       ├── Isaac ROS
       ├── OpenCV
       ├── YOLO
       └── VLM
       │
       ↓
Mobile Robot

二十二、第二阶段

增加：

SO-ARM101

变成：

                AI Agent
                   │
                 VLM
                   │
             Task Planning
                   │
             ┌─────┴─────┐
             │           │
           Nav2       MoveIt 2
             │           │
         Mobile Base   Arm
             │           │
             └─────┬─────┘
                   │
                ROS 2

这时候你已经可以做真正的：

Mobile Manipulation

二十三、第三阶段

再进入：

Unitree Go2

这样你同时拥有：

移动机器人
    +
机械臂
    +
四足机器人
    +
AI Vision
    +
VLM
    +
VLA
    +
Agent

这已经是一个相当完整的个人 AI Robotics 实验室。

二十四、你的学习顺序

如果按照就业价值和实际项目价值，我建议：

Phase 1 — 机器人基础
Linux
 ↓
Python
 ↓
C++
 ↓
Git
 ↓
Docker
Phase 2 — ROS 2
ROS 2
 ↓
TF2
 ↓
URDF
 ↓
Launch
 ↓
Topics
 ↓
Services
 ↓
Actions
 ↓
rosbag
Phase 3 — Mobile Robot
Sensors
 ↓
LiDAR
 ↓
Camera
 ↓
SLAM
 ↓
Nav2
 ↓
Autonomous Navigation
Phase 4 — AI
PyTorch
 ↓
OpenCV
 ↓
YOLO
 ↓
Depth
 ↓
3D Vision
 ↓
VLM
Phase 5 — Simulation
Gazebo
 ↓
Isaac Sim
 ↓
Synthetic Data
 ↓
RL
 ↓
Sim-to-Real
Phase 6 — Manipulation
MoveIt 2
 ↓
IK
 ↓
Motion Planning
 ↓
Grasping
 ↓
Robot Arm
Phase 7 — Embodied AI
VLM
 ↓
VLA
 ↓
Robot Policy
 ↓
Imitation Learning
 ↓
Reinforcement Learning
 ↓
Agent
二十五、2026 最值得你重点掌握的技术

我会把它分成三个等级。

🔴 必须掌握
Python
C++
Linux
Git
Docker
ROS 2
OpenCV
PyTorch
TF2
URDF
Nav2
SLAM
Isaac Sim
🟠 强烈建议
MoveIt 2
Point Cloud
Open3D
YOLO
Depth Camera
LiDAR
CUDA
Isaac ROS
Jetson
Simulation
HIL
🟢 AI Robotics 前沿
VLM
VLA
Robot Foundation Models
Imitation Learning
Reinforcement Learning
Diffusion Policy
Behavior Cloning
Embodied AI
Robot Agent
Sim-to-Real
二十六、最关键的一点

不要把 AI Robotics 学成“ROS 工程师”。

2026 年更有价值的组合是：

Robotics Engineering + AI Engineering

也就是：

传统 Robotics
       +
Computer Vision
       +
Deep Learning
       +
LLM/VLM
       +
VLA
       +
Agent

最终目标：

                Human
                  │
           "帮我把杯子拿来"
                  │
                  ↓
              AI Agent
                  │
             VLM / LLM
                  │
             Task Planner
                  │
        ┌─────────┴─────────┐
        ↓                   ↓
    Navigation          Manipulation
        ↓                   ↓
      Nav2              MoveIt 2
        ↓                   ↓
     Mobile             Robot Arm
        └─────────┬─────────┘
                  ↓
                ROS 2
                  ↓
              Jetson
                  ↓
                Robot

这就是我建议你在 2026 年学习的 AI Robotics 主线。

另外，NVIDIA 已经提供从 Isaac Sim → ROS 2 → Jetson → 真实机器人部署的 HIL 学习路线，这正好对应上面这套架构。

我给你的最终硬件选择
预算	我建议
$500	小型移动底盘 + Jetson Orin Nano Super + LiDAR
$1,500	Unitree Go2 + PC
$2,000	移动机器人 + Jetson + RGB-D + LiDAR
$3,000–5,000	移动机器人 + SO-ARM101 + Jetson + AI PC
$10,000+	Go2 + Mobile Manipulator + GPU Workstation + Jetson
最终目标	Mobile Manipulator + VLM/VLA + Agent + ROS 2 + Isaac Sim

如果只让我替你选一套，我会选：

Ubuntu 24.04 AI 工作站 + NVIDIA GPU + Jetson Orin Nano Super + ROS 2 Jazzy + Isaac Sim + RGB-D Camera + LiDAR + 移动底盘 + SO-ARM101。

这套比单独买一台昂贵的人形机器人更适合你真正学习和开发 AI Robotics。

如果你的目标是以后进入美国 AI Robotics / Physical AI Engineer 岗位，我下一步建议直接做成一份 「6个月实战路线图」：每个月学什么、装什么软件、买什么硬件、做什么项目，以及最终做出 3个可以放 GitHub/简历的 AI Robot 项目。

可以。下面我直接给你一份面向美国 AI Robotics / Physical AI Engineer 岗位的 6 个月实战路线图。目标不是“学会 ROS”，而是 6 个月做出 3 个能放 GitHub、简历、面试展示的机器人项目。

我把路线设计成：

ROS 2 → Simulation → Vision → Navigation → Manipulation → VLM/VLA → Robot Agent

目前 NVIDIA Isaac Sim 官方推荐 Ubuntu 24.04 + ROS 2 Jazzy；ROS 2 Jazzy 官方也支持 Ubuntu 24.04 x86_64 和 ARM64。ROS 1 已进入弃用路线，所以不要再从 ROS 1 开始。

一、先确定你的最终目标

6 个月后，你应该能够做出：

项目 1：AI Autonomous Mobile Robot

“机器人自己建图、定位、导航、避障，并通过摄像头识别物体。”

项目 2：AI Vision Robot Arm

“机器人看到目标后，自动判断目标位置并抓取。”

项目 3：VLM + Robot Agent

用户说：

“找到桌上的红色杯子，把它拿到厨房。”

机器人：

语音 / Text
      ↓
LLM
      ↓
Robot Agent
      ↓
Task Planner
      ↓
VLM
      ↓
Object Detection
      ↓
Navigation
      ↓
Manipulation
      ↓
ROS 2
      ↓
Robot

这三个项目完成后，你就不再只是：

ROS Developer

而是可以开始往：

AI Robotics Engineer / Robotics Software Engineer / Physical AI Engineer / Embodied AI Engineer

方向走。

二、先买什么？

我建议你不要一开始买 Go2 + 机械臂 + 一堆传感器。

先建立开发环境。

第一批硬件
① AI 开发 PC

建议：

Ubuntu 24.04
NVIDIA GPU
32–64 GB RAM
1–2 TB NVMe

如果你准备认真跑 Isaac Sim：

RTX 4070 Ti Super / 4080 Super / 5080 / 5090 级别

越强越舒服。

② Jetson Orin Nano Super

这是我现在最推荐你的 Edge AI 开发板。

NVIDIA 官方目前给出的 Orin Nano Super：

67 INT8 TOPS
8 GB LPDDR5
102 GB/s memory bandwidth
7–25W
支持 Vision Transformer、LLM、VLM、Robotics

官方当前价格为 $249。

NVIDIA Jetson Orin Nano Super 官方页面

注意：

不要把 Jetson 当你的主开发电脑。

正确架构：

        AI Workstation
       RTX GPU / 64GB
             │
       Isaac Sim / AI
             │
             │ Ethernet
             ↓
      Jetson Orin Nano
             │
      ROS 2 / Edge AI
             │
        ┌────┴────┐
        ↓         ↓
     Camera     LiDAR
        │         │
        └────┬────┘
             ↓
           Robot
三、6个月路线图
Month 1 — Linux + Python/C++ + ROS 2
目标

建立机器人软件开发环境。

学习：

Ubuntu 24.04
Python
C++
Git
Docker
ROS 2 Jazzy

ROS 2 Jazzy 是这条路线的核心版本。官方 Ubuntu 安装文档支持 Ubuntu 24.04 Noble。

ROS 2 必学

不要一开始把所有 ROS 2 API 都学完。

先掌握：

Node
Topic
Service
Action
Parameter
Launch
TF2
URDF
rosbag
QoS

重点理解：

Node
 │
 ├── Publisher
 │
 ├── Subscriber
 │
 ├── Service
 │
 └── Action
第一个项目
Project 0：ROS 2 Robot Simulator

创建：

robot_ws/
├── src/
│   ├── robot_description/
│   ├── robot_bringup/
│   ├── robot_controller/
│   └── robot_navigation/
├── build/
├── install/
└── log/

实现：

Keyboard
   ↓
ROS 2
   ↓
cmd_vel
   ↓
Robot

机器人能够：

前进
后退
左转
右转
停止

Month 2 — Simulation + Sensors

这一个月非常重要。

学习：

Gazebo

先掌握：

URDF
Robot model↳
Camera
LiDAR
IMU
Wheel
Differential drive

然后进入：

Isaac Sim

Isaac Sim 官方 ROS 2 bridge 支持 ROS 2 Jazzy/Humble，并且官方推荐 Ubuntu 24.04 + Jazzy。

Isaac Sim 本身还提供：

ROS 2 Navigation
MoveIt 2
Joint Control
Reinforcement Learning
Synthetic Data

Month 2 项目
Project 1：Virtual Autonomous Robot

建立：

Isaac Sim
    ↓
Robot
    ↓
LiDAR
    ↓
Camera
    ↓
ROS 2
    ↓
Python

机器人能够：

在虚拟环境中移动 + 发布 Camera/LiDAR 数据。

Month 3 — Computer Vision + SLAM + Nav2

这是你正式进入 AI Robotics 的月份。

Vision

学习：

OpenCV
 ↓
PyTorch
 ↓
YOLO
 ↓
Object Detection
 ↓
Tracking

例如：

Camera
 ↓
YOLO
 ↓
person
car
chair
cup
SLAM

学习：

LiDAR
 ↓
SLAM
 ↓
Map
 ↓
Localization

理解：

Robot 如何知道自己在哪里？

Nav2

然后：

Map
 ↓
Localization
 ↓
Nav2
 ↓
Path Planning
 ↓
Obstacle Avoidance
 ↓
cmd_vel
 ↓
Robot
Month 3 项目
Project 1：Autonomous AI Mobile Robot

这是你的第一个真正可以放 GitHub 的项目。

功能：

Camera
   +
LiDAR
   ↓
ROS 2
   ↓
SLAM
   ↓
Nav2
   ↓
Object Detection
   ↓
Autonomous Navigation

Demo：

“机器人从 A 点自动走到 B 点，同时避开障碍物。”

第二个 Demo：

“机器人导航到指定位置并寻找红色杯子。”

Month 4 — Robot Arm + MoveIt 2

现在开始机械臂。

推荐：

SO-ARM101

原因不是它性能最强。

而是：

非常适合学习 Robot Learning / Manipulation。

你需要学习：

Forward Kinematics
Inverse Kinematics
Trajectory
Motion Planning
Collision
Grasping
MoveIt 2

架构：

Camera
 ↓
Object Detection
 ↓
3D Position
 ↓
MoveIt 2
 ↓
IK
 ↓
Motion Planning
 ↓
Trajectory
 ↓
Robot Arm
Month 4 项目
Project 2：AI Vision Pick & Place

目标：

摄像头看到一个物体 → 判断物体位置 → 机械臂抓取。

例如：

Camera
   ↓
YOLO
   ↓
Cup
   ↓
Depth Camera
   ↓
3D XYZ
   ↓
MoveIt 2
   ↓
Arm
   ↓
Grasp

这已经是一个很不错的 Robotics Engineer Portfolio 项目。

Month 5 — VLM + VLA

这是最重要的升级。

传统机器人：

Camera
 ↓
YOLO
 ↓
Cup

AI Robot：

Camera
 ↓
VLM
 ↓
理解场景
 ↓
LLM
 ↓
Task Planning
VLM

学习：

Vision-Language Models↳
Multimodal LLM
Image understanding
Visual grounding

让机器人能够理解：

“桌上有什么？”

而不是仅仅：

“YOLO 检测到了一个 cup。”

VLA

VLA：

Vision-Language-Action

核心：

Vision
   +
Language
   +
Action

最终：

"把杯子拿给我"
       ↓
     VLM
       ↓
  Task Planning
       ↓
   Robot Policy
       ↓
   Navigation
       ↓
 Manipulation
Month 5 项目
Project 3：VLM Robot

机器人看到：

桌子
├── 红色杯子
├── 蓝色瓶子
├── 手机
└── 键盘

用户说：

“找到红色杯子。”

Robot：

VLM
 ↓
red cup
 ↓
3D position
 ↓
Robot

第二阶段：

“把红色杯子拿起来。”
Month 6 — Robot Agent

这一个月把前面全部连接起来。

你的架构：

                     User
                       │
                       ↓
                LLM / VLM
                       │
                       ↓
                 Robot Agent
                       │
                 Task Planner
                       │
          ┌────────────┼────────────┐
          ↓            ↓            ↓
      Navigation    Vision      Manipulation
          ↓            ↓            ↓
         Nav2         VLM       MoveIt 2
          │            │            │
          └────────────┼────────────┘
                       ↓
                     ROS 2
                       ↓
                    Jetson
                       ↓
                     Robot
四、Robot Agent 怎么设计？

不要：

LLM
 ↓
Motor

应该：

LLM
 ↓
Agent
 ↓
Tools / Skills

例如：

navigate_to(location)

find_object(object)

pick_object(object)

place_object(location)

follow_person()

dock_robot()

take_picture()

LLM 决定：

navigate_to("kitchen")
find_object("red cup")
pick_object("red cup")
navigate_to("living room")
place_object("table")

ROS 2 负责真正执行。

五、6个月后的完整系统

你最终应该做出：

                    Human
                      │
             "拿红色杯子给我"
                      │
                      ↓
                Robot Agent
                      │
                 LLM / VLM
                      │
               Task Planner
                      │
          ┌───────────┴───────────┐
          │                       │
     Navigation              Manipulation
          │                       │
        Nav2                    MoveIt 2
          │                       │
       Mobile                  Robot Arm
          │                       │
          └───────────┬───────────┘
                      │
                    ROS 2
                      │
                Jetson Orin
                      │
            Camera + LiDAR
                      │
                    Robot
六、每个月具体学习时间

如果你每周投入 10–15 小时：

月份	学习	项目
Month 1	Linux/Python/C++/ROS 2	ROS 2 Mobile Robot
Month 2	Gazebo/Isaac Sim/URDF/Sensors	Simulation Robot
Month 3	OpenCV/YOLO/SLAM/Nav2	Autonomous Robot
Month 4	MoveIt 2/IK/Grasping	AI Robot Arm
Month 5	VLM/VLA/3D Vision	Vision Robot
Month 6	Agent/LLM/ROS 2 Integration	AI Robot Agent
七、GitHub 应该做成这样

不要把 GitHub 做成：

ros2_test
ros2_test2
robot_demo
test_robot

而应该做成三个完整项目。

Repo 1
ai-autonomous-mobile-robot

README：

ROS 2
Nav2
SLAM
LiDAR
YOLO
Isaac Sim
Jetson
Repo 2
vision-based-robot-manipulation

README：

ROS 2
MoveIt 2
RGB-D
YOLO
Open3D
IK
Grasping
Repo 3
vlm-robot-agent

README：

LLM
VLM
VLA
Robot Agent
ROS 2
Nav2
MoveIt 2
Jetson

第三个项目最重要。

八、硬件购买顺序

我建议你按照这个顺序花钱：

第一阶段

$250–500

Jetson Orin Nano Super
+
RGB-D Camera
+
LiDAR

Jetson Orin Nano Super 官方目前标价 $249，并提供 67 TOPS；它的定位就是 Edge AI、Vision AI 和 Robotics。

第二阶段

$500–1,000

增加：

四轮 Mobile Robot

先不要买四足机器人。

第三阶段

$500–1,000

增加：

SO-ARM101
+
RGB-D Camera
第四阶段

如果你想深入四足机器人：

Unitree Go2

这时再买。

九、我特别建议你学习一个东西
Open3D

你之前问过：

三维点云技术是否适合我学？

现在答案非常明确：

适合，而且应该加入这条 AI Robotics 路线。

你的 Vision Stack：

OpenCV
 ↓
YOLO
 ↓
Depth
 ↓
Open3D
 ↓
Point Cloud
 ↓
3D Object
 ↓
Robot

这样你就不是只会：

2D Object Detection
↳

而是：

3D Perception

这是 Robotics 非常重要的能力。

十、你的最终技术栈

我建议你最终形成这一套：

                  AI / Cloud
                      │
             ┌────────┼────────┐
             │        │        │
            LLM      VLM      VLA
             │        │        │
             └────────┼────────┘
                      │
                  AI Agent
                      │
                 Task Planner
                      │
             Robot Skills / Tools
                      │
                     ROS 2
                      │
       ┌──────────────┼──────────────┐
       │              │              │
      Nav2         MoveIt 2       Perception
       │              │              │
      SLAM          IK/Motion     OpenCV/YOLO
       │              │              │
       │              │           Open3D
       │              │              │
       └──────────────┼──────────────┘
                      │
                  Isaac ROS
                      │
                  Jetson
                      │
             Camera / LiDAR / IMU
                      │
                    Robot
十一、最终开发环境

我建议你把自己的开发机固定成：

PC：

Ubuntu 24.04
ROS 2 Jazzy
Docker
NVIDIA Driver
CUDA
PyTorch
OpenCV
Open3D
Isaac Sim
VS Code
Git/GitHub

Robot：

Jetson Orin Nano Super
ROS 2 Jazzy
Isaac ROS
Camera
LiDAR
IMU
Motor Controller

Jetson Orin Nano Super 的官方硬件还提供 4 个 USB 3.2、Gigabit Ethernet、M.2、双 MIPI CSI 摄像头接口等，非常适合作为这种机器人边缘计算节点。

十二、我给你的优先级

如果你时间有限，按照这个顺序：

S级——必须学

1. Python
2. ROS 2
3. Linux
4. C++
5. Docker
6. OpenCV
7. PyTorch
8. Nav2
9. Isaac Sim
10. VLM / VLA

A级——第二优先

11. SLAM
12. TF2
13. URDF
14. MoveIt 2
15. Open3D
16. YOLO
17. Jetson
18. Isaac ROS

B级——后面再深入

19. Reinforcement Learning
20. Imitation Learning
21. Diffusion Policy
22. Robot Foundation Models
23. Sim-to-Real
24. Whole-Body Control
最后给你一个非常明确的结论

如果你准备从现在开始正式进入 AI Robotics，我建议不要同时学 20 个框架。

你的主线锁死为：

Ubuntu 24.04 → Python/C++ → ROS 2 Jazzy → Gazebo → Isaac Sim → OpenCV/YOLO → SLAM/Nav2 → Open3D → MoveIt 2 → Jetson → VLM → VLA → Robot Agent

硬件：

AI GPU PC → Jetson Orin Nano Super → Mobile Robot → RGB-D/LiDAR → SO-ARM101 → 最后再上 Unitree Go2。

其中 Isaac Sim + ROS 2 + Jetson 是非常值得重点押注的组合；NVIDIA 当前的 Isaac Sim 文档也把 ROS 2、Nav2、MoveIt 2、强化学习等直接纳入其机器人开发工作流。

下一步最有价值的是直接进入 Month 1。 我可以给你做成一份 
「AI Robotics 第一个月逐日学习计划（Day 1–30）+ Ubuntu/ROS 2 安装命令 + 第一个 ROS 2 机器人项目完整代码结构」
