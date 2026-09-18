# ROS2SendImage_src

<p>
  <img src="https://img.shields.io/badge/ROS%202-22314E?style=for-the-badge&logo=ros&logoColor=white" alt="ROS 2" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
</p>

## 🇬🇧 Overview

A ROS 2 Python package (`send_img`) with two nodes: a publisher that reads an image file and publishes it as `sensor_msgs/Image` on `image_topic` every second, and a subscriber that converts the message back to OpenCV with `cv_bridge` and saves it.

**Quick start:** `ros2 run send_img publisher_member`

## 🇹🇷 Proje hakkında

İki düğümden oluşan bir ROS 2 Python paketi (`send_img`). Yayıncı düğüm bir görsel dosyasını okuyup saniyede bir `image_topic` konusuna `sensor_msgs/Image` olarak yayınlar. Abone düğüm mesajı `cv_bridge` ile OpenCV görüntüsüne çevirip kaydeder.

## ✨ Özellikler

- `publisher_member`: 1 Hz görüntü yayını
- `subscriber_member`: görüntüyü alıp `received_image.jpg` olarak kaydetme
- `ament_flake8` / `ament_pep257` testleri

## ⚙️ Kurulum ve çalıştırma

Paketi bir ROS 2 çalışma alanının `src/` klasörüne kopyalayın:

```bash
cd ~/ros2_ws
rosdep install --from-paths src -y --ignore-src
colcon build --packages-select send_img
source install/setup.bash

ros2 run send_img publisher_member     # 1. terminal
ros2 run send_img subscriber_member    # 2. terminal
```

## 📁 Dosya yapısı

```text
ROS2SendImage_src/
├── resource/
│   ├── img.png
│   └── send_img
├── send_img/
│   ├── __init__.py
│   ├── img.png
│   ├── publisher_member.py
│   ├── received_image.jpg
│   └── subscriber_member.py
├── test/
│   ├── test_copyright.py
│   ├── test_flake8.py
│   └── test_pep257.py
├── package.xml
├── setup.cfg
└── setup.py
```

## 📝 Notlar

- `publisher_member.py` içindeki `image_path` mutlak bir yol içerir; kendi sisteminizdeki görsel yoluyla değiştirin.
