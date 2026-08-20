如果你说的是“在线打开浏览器就能模拟无人机”，和“真正用于无人机/AI开发的专业仿真器”要分开看。

1. 真正适合无人机开发
模拟器	是否浏览器在线	PX4	ArduPilot	ROS 2	AI/视觉	推荐
Gazebo	❌本地/云	✅	✅	✅	⭐⭐⭐⭐⭐	★★★★★
NVIDIA Isaac Sim	❌本地/云GPU	✅	可接	✅	⭐⭐⭐⭐⭐	★★★★★
Microsoft AirSim	❌本地	✅	✅/社区方案	✅	⭐⭐⭐⭐⭐	★★★★☆
Webots	❌本地	✅/可接	可接	✅	⭐⭐⭐⭐	★★★★☆
CoppeliaSim	❌本地	可接	可接	✅	⭐⭐⭐⭐	★★★★☆
PX4 SITL + Gazebo	❌本地/云	✅	—	✅	⭐⭐⭐⭐⭐	★★★★★
DroneSimLab	✅浏览器	—	—	—	⭐⭐	★★★☆☆
Altnautica Mission Control	✅浏览器	✅	✅	—	⭐⭐⭐	★★★★☆

PX4 官方目前推荐 Gazebo 做完整 3D 仿真，尤其适合传感器、避障、计算机视觉、多无人机和 ROS 开发。

2. 如果你现在就想“打开网页玩无人机”

DroneSimLab 是比较直接的选择：

DroneSimLab 在线无人机模拟器

它直接在浏览器运行，不需要安装软件，也可以用手机作为控制器。

另外还有 Altnautica Mission Control，它是浏览器版地面站，同时提供 3D simulator，支持 PX4、ArduPilot 和 MAVLink。

Altnautica Mission Control

3. 如果你的目标是“开发 AI 无人机”

结合你之前准备学习的 AI Robotics + ROS 2 + 无人机开发，我不建议把主要时间放在 DroneSimLab 这种网页飞行模拟器上。

我建议直接走：

Ubuntu → ROS 2 → PX4 → Gazebo → QGroundControl → Python/MAVSDK → AI/Computer Vision

架构是：

Python / C++
      ↓
ROS 2
      ↓
MAVSDK / MAVROS
      ↓
PX4 Flight Controller
      ↓
Gazebo
      ↓
虚拟无人机
 ↓    ↓    ↓
Camera LiDAR IMU GPS
      ↓
AI / Computer Vision

PX4 官方支持 SITL，也就是不用真实飞控和无人机，就可以让 PX4 飞控代码控制虚拟无人机。

4. 我最推荐你的组合

如果你的最终目标是在美国做 AI Drone / Autonomous Drone Engineer：

第一阶段：

DroneSimLab → 先理解飞行控制

第二阶段：

PX4 SITL + Gazebo → 学真正的无人机开发

第三阶段：

ROS 2 + PX4 + Gazebo → 自主导航

第四阶段：

Isaac Sim → AI视觉、LiDAR、3D、强化学习

第五阶段：

真机 PX4/ArduPilot → SITL → HITL → 实机

AirSim 仍然可以用于视觉和无人机研究，但 PX4 当前文档明确把它列为 community supported，因此我不会把它作为你2026年的第一主力平台。

如果你愿意，我可以直接
给你搭一套“完全在线的无人机 AI 开发环境”——不用买电脑，AWS 云端 Ubuntu + ROS 2 + PX4 + Gazebo + QGroundControl + Python，从注册 AWS 到让第一架虚拟无人机自动起飞。

给我搭一套完全在线的无人机 AI 开发环境

可以。按照你前面想走的 AI Robotics / 无人机自主飞行 / ROS 2 / PX4 路线，我建议直接搭一套完全云端环境：你的电脑只负责浏览器和远程桌面，真正的 Ubuntu、GPU、Gazebo、PX4、ROS 2 都跑在 AWS。

一、最终架构
你的电脑 / Mac / iPad
        │
        │ 浏览器
        ▼
 AWS EC2 GPU
 Ubuntu 24.04
        │
        ├── VS Code Server / Code-Server
        │
        ├── ROS 2
        │
        ├── PX4 Autopilot
        │
        ├── Gazebo
        │
        ├── MAVSDK
        │
        ├── OpenCV
        │
        ├── PyTorch
        │
        └── AI Drone
              │
              ├── Camera
              ├── IMU
              ├── GPS
              └── LiDAR

AWS 的 G6 GPU 实例目前采用 NVIDIA L4，单 GPU 有 24 GB GPU memory，并且专门适合图形渲染和机器学习，所以非常适合 Gazebo + AI 视觉这类组合。

二、我建议你的 AWS 配置
开发阶段

先用：

EC2 g6.2xlarge

配置：

8 vCPU
32 GiB RAM
NVIDIA L4
24 GB GPU memory

AWS 官方规格也列出了这个配置。

这个级别比较适合：

PX4 SITL
Gazebo
ROS 2
RViz
OpenCV
YOLO
Python
MAVSDK

如果以后跑 Isaac Sim + 大型视觉模型，再升级 GPU。

不建议一开始就开：

g6.12xlarge

它是 4 × L4 GPU / 96 GB GPU memory，对你目前学习阶段明显过剩。

三、操作系统

我建议：

Ubuntu 24.04 LTS

原因是你以后要学习：

ROS 2
PX4
Gazebo
CUDA
PyTorch
OpenCV
MAVSDK
Isaac Sim

Ubuntu 会比 Windows 更适合这套机器人开发环境。

四、云端开发工具

我建议安装：

Ubuntu 24.04
│
├── Git
├── Docker
├── Python 3
├── VS Code Server
│
├── ROS 2
│
├── PX4
├── Gazebo
│
├── MAVSDK
├── MAVROS
│
├── OpenCV
├── PyTorch
├── YOLO
│
└── QGroundControl

QGroundControl 是 PX4 非常重要的地面站，可以用来观察飞行状态、设置参数和执行任务；官方目前支持 Windows、macOS、Ubuntu 和 Android。

五、整个无人机 AI 开发链

你以后真正开发的时候，就是：

                 AI
                 │
        ┌────────┴────────┐
        │                 │
 Computer Vision      AI Agent
        │                 │
      Python             LLM
        │
      ROS 2
        │
     MAVSDK
        │
       PX4
        │
      Gazebo
        │
    Virtual Drone

例如：

项目 1

让无人机自动起飞：

Python
 ↓
MAVSDK
 ↓
PX4
 ↓
Gazebo
 ↓
Takeoff
项目 2

让无人机自动飞到目标：

Camera
 ↓
OpenCV
 ↓
Object Detection
 ↓
ROS 2
 ↓
PX4
 ↓
Drone Navigation
项目 3

AI 无人机：

Camera
 ↓
YOLO
 ↓
Object Detection
 ↓
ROS 2
 ↓
AI Decision
 ↓
MAVSDK
 ↓
PX4
 ↓
Drone
六、第一阶段不要碰 Isaac Sim

这一点我特别建议你注意。

先不要：

AWS
↓
Isaac Sim
↓
GR00T
↓
复杂 AI

这样很容易把时间全部花在环境配置上。

先：

AWS
 ↓
Ubuntu
 ↓
ROS 2
 ↓
PX4
 ↓
Gazebo
 ↓
第一架虚拟无人机起飞

第一目标只有一个：

在 AWS 上让一架 PX4 虚拟无人机在 Gazebo 中成功自动起飞、悬停、降落。

完成以后再增加 AI。

七、最终学习路线

我建议你按照这个顺序：

Phase 1 — Linux
Ubuntu
SSH
Git
Docker
Python
Bash

↓

Phase 2 — Drone
PX4
SITL
Gazebo
QGroundControl
MAVLink

↓

Phase 3 — Robotics
ROS 2
Node
Topic
Service
Action
TF
RViz

↓

Phase 4 — Drone Programming
MAVSDK
MAVROS
Python
C++

↓

Phase 5 — Computer Vision
OpenCV
YOLO
Camera
Object Detection
Tracking

↓

Phase 6 — Autonomous Drone
GPS
IMU
LiDAR
SLAM
Path Planning
Obstacle Avoidance

↓

Phase 7 — AI
PyTorch
Deep Learning
Vision Transformer
LLM
AI Agent
VLM

↓

Phase 8 —高级仿真
Isaac Sim
NVIDIA Isaac
GR00T
Reinforcement Learning
Sim-to-Real
八、我建议直接给你做成这个项目

最终目录：

ai-drone/
│
├── px4/
│
├── ros2_ws/
│   └── src/
│       ├── drone_control/
│       ├── drone_navigation/
│       ├── drone_vision/
│       └── drone_ai/
│
├── simulation/
│   ├── worlds/
│   ├── models/
│   └── configs/
│
├── ai/
│   ├── detection/
│   ├── tracking/
│   └── decision/
│
├── scripts/
│
├── docker/
│
└── README.md

最终你会拥有一套真正接近美国无人机/机器人公司的开发环境，而不是单纯的“飞行游戏模拟器”。

九、下一步我建议直接实操

我们可以从 AWS 第一步开始，一步一步搭，不跳步骤：

Day 1：

AWS
 ↓
EC2
 ↓
g6.2xlarge
 ↓
Ubuntu 24.04
 ↓
NVIDIA Driver
 ↓
CUDA
 ↓
Docker
 ↓
VS Code Server

然后 Day 2：

ROS 2
 ↓
Gazebo

Day 3：

PX4 SITL
 ↓
Gazebo
 ↓
Virtual Drone

Day 4：

Python
 ↓
MAVSDK
 ↓
自动 Takeoff

Day 5：

Camera
 ↓
OpenCV
 ↓
YOLO
 ↓
目标识别

这样 5天以后你就能在云端拥有第一套可以真正运行 AI 无人机程序的开发环境。
