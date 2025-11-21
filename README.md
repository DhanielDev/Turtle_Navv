🚀 TurtleBot4 Setup & Run Guide

Panduan lengkap untuk menyiapkan workspace, build project, menjalankan navigasi, lokalisasi, RViz, dan paket custom pada TurtleBot4.

📦 1. Setup Workspace & Build Project
1️⃣ Buat workspace
mkdir -p ~/turtlebot4_delivery/src
cd ~/turtlebot4_delivery/src

2️⃣ Clone repository
git clone https://github.com/MarcellinoAcel/pose_nav_turtle.git

3️⃣ Build workspace dengan colcon
cd ~/turtlebot4_delivery
colcon build

4️⃣ Source workspace
source install/setup.bash

🖥️ 2. Visualization (RViz)
🔹 Opsi A — Jalankan RViz lewat SSH (jika benar-benar diperlukan)

Koneksi dengan X-Forwarding:

ssh -X ubuntu@192.168.185.3


Lalu jalankan tampilan navigasi:

ros2 launch turtlebot4_viz view_navigation.launch.py

🔹 Opsi B — Jalankan RViz lokal (direkomendasikan — lebih cepat)

Tanpa SSH:

ros2 launch turtlebot4_viz view_robot.launch.py

📍 3. Localization

Buka terminal baru, lalu konek ke robot:

ssh ubuntu@192.168.185.3


Source workspace:

cd ~/turtlebot4_delivery
source install/setup.bash


Jalankan localization dengan map Anda:

ros2 launch pose_nav_turtle localization.launch.py map:=src/pose_nav_turtle/maps/map_uts_kel1.yaml


Di RViz:
➡️ Gunakan 2D Pose Estimate untuk set posisi awal robot.

🤖 4. Jalankan Navigation Package

Buka terminal baru dan konek ulang:

ssh ubuntu@192.168.185.3


Source workspace:

cd ~/turtlebot4_delivery
source install/setup.bash


Jalankan navigation node:

ros2 launch pose_nav_turtle run_nav.launch.py


Di RViz:
➡️ Gunakan Nav2 Goal untuk memberi tujuan navigasi.

⚙️ 5. Menjalankan Node Tambahan

Buka terminal baru, konek ulang:

ssh ubuntu@192.168.185.3


Source workspace:

cd ~/turtlebot4_delivery
source install/setup.bash


Jalankan node custom:

ros2 run pose_nav_turtle pose_nav_turtle

🎉 Selesai!

Anda sekarang sudah menjalankan:

✅ RViz Visualization
✅ Localization
✅ Navigation Package
✅ Custom Node untuk pengaturan target pose & task

Selamat mencoba dan bereksperimen dengan TurtleBot4! 🤖✨

▶️ Video Demonstrasi

Klik di sini untuk menonton video demonstrasinya:
👉 Tonton di YouTube

(Ganti # dengan link video YouTube Anda)
