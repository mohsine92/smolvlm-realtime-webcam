# LlamaLens - SmolVLM Real-time Webcam

Vision-Language Model (VLM) for real-time video analysis via webcam.

<img width="2964" height="1866" alt="LocalEye Screenshot" src="https://github.com/user-attachments/assets/2ad3bdcb-db90-4b15-8ca4-193990d988b8" />

---

## 🔍 Objective

LlamaLens allows you to:  
- Capture images from your webcam  
- Send them to a **SmolVLM** model via `llama-server`  
- Receive real-time analysis (text, detected objects, etc.)

---

## 🛠 Prerequisites

- **OS**: Linux, macOS, or Windows (via WSL)  
- **Browsers**: Chrome, Firefox, Safari  
- **Webcam**: built-in or external  
- **GPU (optional)**: NVIDIA, AMD, or Metal (Mac) for faster processing  
- **Python 3** to run the web server

---

## ⚡ Installation

### 1. Install `llama.cpp`

```bash
git clone https://github.com/ggml-org/llama.cpp
cd llama.cpp
mkdir build && cd build
cmake .. -DGGML_METAL=ON  # or -DGGML_CUDA=ON
make -j$(nproc)
```

### 2. Install LlamaLens
```bash
git clone https://github.com/mohsine92/smolvlm-realtime-webcam.git
cd smolvlm-realtime-webcam
```

## Utilisation

### 1. Start the AI server
```bash
cd llama.cpp/build
./bin/llama-server -hf ggml-org/SmolVLM-500M-Instruct-GGUF --host 0.0.0.0 --port 8080 -ngl 99
```

### 2. Launch the web application
```bash
python3 -m http.server 3000
```

### 3. Open http://localhost:3000

## Notes & Troubleshooting

**Camera error:** Use localhost and allow camera access in system preferences.

**Browser cache:** Refresh with Cmd+Shift+R (Mac) or Ctrl+Shift+R (Windows/Linux) if the interface doesn’t update.

**API:** Check that the llama.cpp server is running on port 8080

## Useful Links

- [Original SmolVLM Realtime Webcam](https://github.com/ngxson/smolvlm-realtime-webcam) – Original repository
- [Your Fork: smolvlm-realtime-webcam](https://github.com/mohsine92/smolvlm-realtime-webcam) – My updated version
- [llama.cpp GitHub](https://github.com/ggml-org/llama.cpp) – Official repository for llama.cpp
- [Hugging Face Models](https://huggingface.co/models) – Browse and download machine learning models
- [SmolVLM 500M Model on Hugging Face](https://huggingface.co/ggml-org/SmolVLM-500M-Instruct-GGUF) – Pre-trained SmolVLM 500M model
