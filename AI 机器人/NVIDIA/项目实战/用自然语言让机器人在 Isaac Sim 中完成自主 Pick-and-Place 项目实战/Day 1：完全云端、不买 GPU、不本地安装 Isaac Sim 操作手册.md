先纠正一个版本问题：NVIDIA 当前 Physical AI 学习平台已经提供 Isaac Launchable，可以在 Brev 上直接运行 Isaac Lab + Isaac Sim；目前官方学习资料也已经包含 GR00T + Unitree G1 的完整课程。

Day 1 总目标

今天不要碰真实机器人，也不要急着训练 GR00T。

今天只完成 5 件事：

① 注册 NVIDIA / Brev
        ↓
② 创建 Isaac Launchable
        ↓
③ 云端进入 Ubuntu
        ↓
④ 打开 Isaac Sim
        ↓
⑤ 跑第一个机器人仿真

最终你应该看到：

一个机器人在 NVIDIA Isaac Sim 云端环境中运行。

一、今天需要准备什么

你的 Windows 电脑只需要：

Windows 10/11
Chrome 或 Edge↳
GitHub 账号
NVIDIA Developer 账号
稳定网络
建议至少 16GB 本地 RAM
不需要 NVIDIA GPU

Isaac Sim 官方支持远程/headless运行，并可以通过 WebRTC Streaming Client 从没有强大 GPU 的本地电脑查看。

二、注册 NVIDIA Developer

进入 NVIDIA Developer：
↳

NVIDIA Developer

注册/登录。

建议使用你长期使用的邮箱，因为以后：

NVIDIA Developer
      ↓
Brev
      ↓
Isaac
      ↓
GR00T
      ↓
Hugging Face

会经常使用。

三、进入 Brev

进入：

NVIDIA Brev

登录。

NVIDIA 当前官方 Physical AI 学习平台已经明确把 Brev 作为没有本地 GPU 用户的云端入口，并提供 Isaac Launchable。

四、创建你的第一个云端机器人环境

进入 Brev Console 后：

Brev
 ↓
Launchables

搜索：

Isaac Lab

优先选择：

NVIDIA 官方 Isaac Lab Launchable

不要随便选择第三方环境。

NVIDIA 当前文档明确推荐初学者使用 Isaac Lab Launchable。

五、GPU 怎么选？

如果界面出现 GPU 选择：

Day 1 我建议：

1 × NVIDIA L40S

不要：

❌ H100
❌ H200
❌ B200

你今天只是学习 Isaac Sim。

NVIDIA 官方 Brev Isaac Sim 部署文档本身就是以 1× NVIDIA L40S作为示例。

六、磁盘怎么选？

如果让你选择 Storage：

150–250 GB

Day 1 不需要 500GB。

因为今天主要是：

Isaac Sim
Isaac Lab
ROS 2
Python
Git

以后开始下载 GR00T 数据集，再扩容。

七、实例名称

建议直接命名：

peng-isaac-lab-day1

以后你会有：

peng-isaac-lab-day1
peng-isaac-lab-day2
peng-groot
peng-vla
peng-humanoid

不要使用一堆：

test1
test2
abc
robot
new

后面会非常乱。

八、启动实例

点击：

Deploy

等待云端 VM 创建。

第一次可能需要一些时间。

你最终应该看到：

Status: Running
九、进入云端 Terminal

如果 Launchable 提供：

Open Notebook

或者：

Terminal

直接进入。

NVIDIA 的 Brev Isaac Sim 文档也提供从 Jupyter Notebook Terminal 进入云端实例的方法。

你应该看到类似：

ubuntu@xxxxx:~$

这意味着：

你现在已经进入云端 Ubuntu。

你的 Windows 电脑只是客户端。

十、第一条命令：检查 GPU

输入：

nvidia-smi

你应该看到类似：

NVIDIA L40S
CUDA Version
Driver Version
Memory

重点看：

GPU: NVIDIA L40S
VRAM: 48 GB

如果能看到 GPU：

Day 1 的第一个检查点通过。

十一、第二条命令：检查 Docker

输入：

docker --version

然后：

docker info

如果返回 Docker 信息：

Docker 正常。

十二、第三条命令：检查 Python

输入：

python3 --version

然后：

python3 -m pip --version
十三、第四条命令：检查 ROS 2

输入：

printenv ROS_DISTRO

如果已经配置 ROS 2，应该看到类似：

jazzy

然后：

ros2 --version

如果 Launchable 当前环境没有 ROS 2，也不要今天自己乱装。

因为你现在最重要的是先确认：

Isaac Sim 能运行。

ROS 2 可以在后面的 Day 2/3 接进去。

十四、现在启动 Isaac Sim

如果 Launchable 已经提供 Isaac Sim 启动脚本，使用它提供的启动方式。

如果你看到类似：

Isaac Sim
Start Isaac Sim
Launch Isaac Sim

直接点击。

如果需要 Terminal 启动远程流：

./isaac-sim.streaming.sh

Isaac Sim 官方当前文档明确说明，远程/headless 环境可以使用 isaac-sim.streaming.sh，然后连接 WebRTC Streaming Client。

十五、Windows 上显示 Isaac Sim

这里有两种方式。

方法 A：Web Viewer

如果你的 Launchable 提供：

Open Web Viewer

直接用。

Isaac Sim 6.0 已经增加了基于 WebRTC 的 web-based livestreaming，可以通过 Docker Compose 部署，不需要本地安装客户端。

这是：

最适合你的方式。

因为：

Windows
 ↓
Chrome
 ↓
WebRTC
 ↓
Cloud Isaac Sim
方法 B：WebRTC Streaming Client

如果 Brev 环境要求客户端：

下载 NVIDIA 官方：

Isaac Sim WebRTC Streaming Client

Windows 电脑安装 Client。

然后连接你的云实例。

NVIDIA 当前文档明确把 WebRTC Streaming Client 定义为在没有强大本地 GPU 的桌面/工作站上远程查看 Isaac Sim 的推荐方式。

十六、第一次看到 Isaac Sim 后，不要急着操作

你先认识这个界面。

主要看：

┌───────────────────────────────────┐
│ Menu                              │
├────────────┬──────────────────────┤
│            │                      │
│ Stage      │       3D View        │
│            │                      │
│ Scene      │       Robot          │
│            │                      │
├────────────┴──────────────────────┤
│ Properties / Console               │
└───────────────────────────────────┘

重点认识 4 个东西：

Stage

机器人和世界里的对象。

World
 ├── Robot
 ├── Camera
 ├── Light
 └── Ground
Viewport

你看到的 3D 世界。

Properties

修改机器人参数。

Physics

控制：

gravity
collision
rigid body
joints
十七、今天第一个机器人：不要直接 GR00T

今天先用一个最简单的机器人。

如果 Launchable 有：

Isaac Lab
Examples
Cartpole

直接打开。

Cartpole：

       Pole
        │
        │
        │
   ─────┴─────
      Cart

它看起来很简单。

但是它会让你第一次理解：

Robot
 ↓
Environment
 ↓
Observation
 ↓
Action
 ↓
Reward
 ↓
Policy

这正是后面：

GR00T / VLA / RL

的基础。

NVIDIA 当前 Isaac Lab 学习课程就是围绕 GPU 加速机器人学习、RL 和并行训练建立的。

十八、第一次运行 Cartpole

如果 Launchable已经提供课程环境，进入：

Isaac Lab
 ↓
Tutorial
 ↓
Cartpole

运行。

你应该看到：

Cart
 ↓
Pole
 ↓
Simulation

然后点击：

Play
十九、今天第一次理解“机器人 AI”

假设：

Observation:
pole angle = 10°

机器人执行：

Action:
move left

环境返回：

Reward:
+1

下一步：

Observation
      ↓
Policy
      ↓
Action
      ↓
Environment
      ↓
Reward
      ↓
Policy update

这就是：

Reinforcement Learning

二十、Day 1 不要训练 GR00T

这是我特别建议你的地方。

今天不要做：

❌ Fine-tune GR00T
❌ 下载几十 GB 数据
❌ Humanoid
❌ VLA
❌ Jetson
❌ Unitree
❌ Sim-to-Real

今天只建立：

Cloud GPU
   ↓
Isaac Sim
   ↓
Isaac Lab
   ↓
Robot Simulation
二十一、最后做一个 Python 检查

在云端 Terminal：

python3 - <<'PY'
print("================================")
print(" AI ROBOTICS DAY 1")
print("================================")
print("Cloud GPU : OK")
print("Python    : OK")
print("Isaac Lab : OK")
print("Robot Sim : OK")
print("================================")
PY

如果全部正常：

Day 1 完成。

二十二、把你的代码放进 GitHub

建立一个仓库：

ai-robotics-lab

目录：

ai-robotics-lab/
│
├── day01/
│   ├── README.md
│   └── notes.md
│
├── day02/
│
├── day03/
│
├── isaac_lab/
│
├── ros2/
│
├── groot/
│
└── projects/

Day 1 的 README.md 写：

# AI Robotics Lab

## Day 1

Environment:
- NVIDIA Brev
- NVIDIA Isaac Lab
- NVIDIA Isaac Sim
- Cloud GPU: NVIDIA L40S

Completed:
- Cloud GPU created
- Isaac Lab launched
- Isaac Sim launched
- First robot simulation completed

Next:
- ROS 2
- Isaac Sim Python
- Isaac Lab
- GR00T
二十三、今天一定要做一个动作：关掉 GPU

这个非常重要。

你使用云 GPU 是：

按时间/资源产生费用。

所以学习结束以后：

Brev
 ↓
Instances
 ↓
peng-isaac-lab-day1
 ↓
Stop / Suspend

不要直接关闭浏览器就走。

浏览器关闭 ≠ 云服务器停止。

二十四、Day 1 最终检查表

完成以后你应该全部打勾：

☐ NVIDIA Developer 注册
☐ Brev 注册
☐ Isaac Lab Launchable
☐ Cloud GPU L40S
☐ Ubuntu Terminal
☐ nvidia-smi
☐ Docker
☐ Python
☐ Isaac Sim
☐ WebRTC/Web Viewer
☐ 第一个机器人
☐ Cartpole
☐ GitHub repository
☐ 停止 Cloud GPU
二十五、你的完整学习路线，我建议这样改

你之前准备从：

ROS 2 → Isaac Sim → Isaac Lab → GR00T

现在我建议改成：

              AI ROBOTICS
                   │
          ┌────────┴────────┐
          ↓                 ↓
       Robotics             AI
          │                 │
       ROS 2              PyTorch
       C++                Transformer
       URDF               VLM
       TF2                VLA
          │                 │
          └────────┬────────┘
                   ↓
              Isaac Sim
                   ↓
              Isaac Lab
                   ↓
                 GR00T
                   ↓
              VLA Policy
                   ↓
              Sim-to-Real
                   ↓
            Jetson / Robot

而且 NVIDIA 现在已经提供一门**“How to Develop and Deploy Humanoid Robots End-to-End with NVIDIA Isaac GR00T and Unitree G1”**课程，覆盖 GR00T、Isaac Lab、teleoperation、Isaac ROS、Jetson Thor 和 Unitree G1。这个可以作为你后面从仿真进入人形机器人的主线。

你今天真正要达到的目标

不是“学会 Isaac Sim”。

而是建立这个概念：

Cloud GPU → Simulation → Robot → Data → Policy → AI → Real Robot

这就是你以后学习 GR00T / Figure / Optimus / Gemini Robotics 时反复使用的基本框架。
