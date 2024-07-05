---
title: How to make your Qt/CPP Applications Scriptable with Python
create_date: 2024-06-13::00:00
author: Faisal Shahzad
status: draft
categories: intermediate, tutorials
banner: incomplete
feature_image: fatureimage.png
description: How to make your Qt/CPP Applications Scriptable with Python
---

This guide is for PySide6 using the latest version of 6.7.1. 

### Install QT6

install 7zip

### Installation PySide6

- PySide6
- Shiboken6
- Shiboken6_generator


#### Create Virtual environment

```bash
user@pybodensee:~/src/embed_pyside$ python -m venv .venv
user@pybodensee:~/src/embed_pyside$ source .venv/bin/activate
```

#### Setup PySide Directory

```bash
QTVERSION=6.7.1
git clone https://code.qt.io/pyside/pyside-setup
cd pyside-setup
pip install -r requirements.txt
$USERgit checkout $QTVERSION # if a specific version is needed
export PATH=/home/$USER/Qt/$QTVERSION/gcc_64/bin:$PATH
```

## Setup CLANG
If you havnet already setup CLANG on your machine, then get a copy form [Qt website](https://download.qt.io/development_releases/prebuilt/libclang/). Extract it at a suitable location (e.g. in pyside-setup) forlder and then export its path in `LLVM_INSTALL_DIR` path.


```bash
wget https://download.qt.io/development_releases/prebuilt/libclang/libclang-release_17.0.1-based-linux-Ubuntu22.04-gcc11.4-x86_64.7z
7z x libclang-release_17.0.1-based-linux-Ubuntu22.04-gcc11.4-x86_64.7z
export LLVM_INSTALL_DIR=$PWD/libclang
```

When downloading CLANG, make sure it matches your compiler version. For example, I am running Ubuntu 22.04 with GCC11.4, so I downloaded `ibclang-release_17.0.1-based-linux-Ubuntu22.04-gcc11.4-x86_64.7z` file. 


# Build and Install PySide with all bindings


```bash
python setup.py install --qt-target-path=/home/$USER/Qt/$QTVERSION/ --qtpaths=/home/$USER/Qt/$QTVERSION/gcc_64/bin/qtpaths6
```

### Compile Example

```bash
mkdir build
cd build
cmake ..
make
```

### Run
```bash
./scriptableapplication
```

## Prepare Your Linux System

Python 3.10
All python dependences are in requirements.txt file

### Missing Dependencies
Depending upon your current Linux distro, you might get missing dependencies error e.g. `libxcb`. Your erro might look like `XCB:XCB` missing.

```bash
sudo apt install libfontconfig1-dev libfreetype6-dev \
libx11-dev libx11-xcb-dev libxext-dev libxfixes-dev \
libxi-dev libxrender-dev libxcb1-dev libxcb-glx0-dev \
libxcb-keysyms1-dev libxcb-image0-dev libxcb-shm0-dev \
libxcb-icccm4-dev libxcb-sync-dev libxcb-xfixes0-dev \
libxcb-shape0-dev libxcb-randr0-dev libxcb-render-util0-dev \
libxcb-util-dev libxcb-xinerama0-dev libxcb-xkb-dev \
libxkbcommon-dev libxkbcommon-x11-dev libatspi2.0-dev \
libopengl0 -y
```

If you are using Qt Multimedia modules, then you have to install install gstreamer aswell.

```bash
sudo apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev \
libgstreamer-plugins-bad1.0-dev gstreamer1.0-plugins-base \
gstreamer1.0-plugins-good gstreamer1.0-plugins-bad \
gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-doc \
gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl \
gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio
```