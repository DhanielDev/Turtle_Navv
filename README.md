# 🚀 TurtleBot4 Setup & Run Guide

This guide explains how to set up your workspace, build the project, and run TurtleBot4 with navigation, localization, RViz visualization, and custom packages.

---

## 📦 1. Setup Workspace & Build Project

1️⃣ Buat workspace :

```bash
mkdir -p ~/turtlebot4_delivery/src
cd ~/turtlebot4_delivery/src
```

2️⃣ Clone repository :

```bash
git clone https://github.com/MarcellinoAcel/pose_nav_turtle.git
```

3️⃣ Build workspace dengan colcon :

```bash
cd ~/turtlebot4_delivery
colcon build
```

4️⃣ Source workspace :

```bash
source install/setup.bash
```

---

## 🖥️ 2. Visualization (RViz)

### 🔹Option A: Run RViz remotely via SSH (recommended only if needed)

Connect with X forwarding:

```bash
ssh -X ubuntu@192.168.185.3
```

Launch the navigation RViz view:

```bash
ros2 launch turtlebot4_viz view_navigation.launch.py
```

### 🔹Option B: Run RViz locally (better performance)

If RViz is installed on your laptop, **no need for SSH -X**.
Simply run:

```bash
ros2 launch turtlebot4_viz view_robot.launch.py
```

---

## 📍 3. Localization
*(Open a **new terminal**)*
Connect to the robot:

```bash
ssh ubuntu@192.168.185.3
```

Source workspace:

```bash
cd ~/turtlebot4_delivery
source install/setup.bash
```

Run localization with your map:

```bash
ros2 launch pose_nav_turtle localization.launch.py map:=src/pose_nav_turtle/maps/map_uts_kel1.yaml
```

In RViz:

* Use **2D Pose Estimate** to set the initial pose.

---

## 🤖 4. Run Your Navigation Package
*(Open a **new terminal**)*
Connect again:

```bash
ssh ubuntu@192.168.185.3
```

Enter your workspace:

```bash
cd ~/turtlebot4_delivery
source install/setup.bash
```

Launch your navigation node:

```bash
ros2 launch pose_nav_turtle run_nav.launch.py
```

➡️Then test navigation using **Nav2 Goal** in RViz.

---

## ⚙️ 5. Run Additional Nodes
*(Open a **new terminal**)*
Connect once more:

```bash
ssh ubuntu@192.168.185.3
```

Source workspace:

```bash
cd ~/turtlebot4_delivery
source install/setup.bash
```

Run your node:

```bash
ros2 run pose_nav_turtle pose_nav_turtle
```

---

## You’re Ready!

You now have:

* RViz visualization running (remote or local)
* Localization active
* Your navigation package launched
* Additional custom nodes for robot target pose and task

<h1 align="center">Video UTS Lokalisasi </h1>

<p align="center">
  <a href="https://youtu.be/6zgk-CazAtY" target="_blank">
    <img src="https://img.shields.io/badge/Tonton_Edukasi-YouTube-red?style=for-the-badge&logo=youtube" alt="Tonton di YouTube"/>
  </a>
</p>

📺 Klik tombol di atas untuk melihat video YouTube UTS saya!
