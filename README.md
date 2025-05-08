# 🧠 NervTestGenV8: AI-Driven Zero-Latency Cloud Gaming with Predictive Rendering

**NervTestGenV8** is an advanced 3D cloud gaming system that utilizes real-time **image prediction** to virtually eliminate the latency experienced in traditional remote gaming. By combining deep learning with geometry-aware rendering, NervTestGenV8 delivers smooth and instantaneous game frames before the server finishes rendering them.

---

## 🚀 Key Highlights

* 🎮 **Zero-latency 3D gameplay** via intelligent prediction
* 🔍 Dual-core: Foreground movement prediction + Background scene reconstruction
* 🧠 Built on deep temporal modeling and depth-aware interpolation
* ⚡ Lightweight demo-ready setup with pre-trained models and sample data

---

## 🧠 System Components

### 1. Foreground Prediction

Predicts player and object movement using temporal deep learning models.

### 2. Background Prediction

Reconstructs static scene elements through image-based rendering (DIBR), optionally using cached data.

---

## 📁 Foreground Module

### 🔧 Setup

```bash
git clone https://github.com/Kenxpx/NervTestGenV8.git
cd NervTestGenV8/foreground
conda env create -f environment.yml
conda activate nervfg
```

### 📅 Download Models

* [Pre-trained Foreground Models (Google Drive)](https://drive.google.com/drive/folders/129ftjmfHjoehxGyi6HLQszVRgVN_WBGV?usp=sharing)
* Save models in the `/checkpoints` directory.

### 🤪 Run a Prediction Demo

```bash
python run.py
```

* Sample inputs located in `/sample`
* Output predictions saved in `/results`

**Note:** Default resolution is `256x256`. For `1024x1024` predictions (requires ≥ 41GB GPU memory), update `--img_width` and `--pretrained_model` in `run.py`.

---

## 🌄 Background Module

### 🔧 Build Requirements

* OS: Linux / macOS / Windows
* C++ compiler
* OpenCV 4.5.5 or later

### 🔨 Setup

```bash
cd NervTestGenV8/background
# Use your preferred build system (e.g., CMake) to compile the C++ project
```

### 📅 Sample Data

* [Download Sample Background Dataset](https://drive.google.com/file/d/19gWhURb2LU7ysBNeMSUeIe1Il6VLXjO7/view?usp=drive_link)
* Extract and place folders (`2020-06-03-20-28-01`, etc.) into `/data`

### 🤪 Run Background Reconstruction

* Execute the compiled binary.
* Outputs:

  * Predicted frames → `/results`
  * PSNR log → `results/log.txt`

---

## 🔗 External Dependencies

Built upon and inspired by the following open-source projects:

* [PredRNN (PyTorch)](https://github.com/thuml/predrnn-pytorch)
* [MASA-SR (Multi-Scale SR)](https://github.com/dvlab-research/MASA-SR)
* [GTA-IM Dataset](https://github.com/ZheC/GTA-IM-Dataset)

---

## 📬 Contact & Contributions

We welcome contributions and feedback!

* 📧 Email: [sachinbinduc@gmail.com](mailto:sachinbinduc@gmail.com)
* 🛠️ Issues & Pull Requests: [GitHub Issues](https://github.com/Kenxpx/NervTestGenV8/issues)

---

> NervTestGenV8 – Redefining the boundaries of real-time cloud gaming.
