# MySign: Real-Time Malaysian Sign Language (MSL) Translator 🇲🇾

MySign is an end-to-end AI-powered translation system designed to bridge the communication gap for the Deaf community in Malaysia. Unlike traditional image-based models, MySign uses **3D skeletal landmarks** and **Temporal Convolutional Networks (TCN)** to recognize dynamic gestures in real-time.

---

## 🚀 Key Features

- **High Accuracy:** Achieved **94.14% test accuracy** across 52 distinct MSL signs (glosses).
- **Privacy-First:** Uses MediaPipe to extract mathematical wireframes, ensuring no raw video/facial data is ever stored or sent to a server.
- **Client-Side Inference:** Powered by **ONNX Runtime Web**, performing all AI calculations on the user's device for zero-latency and offline potential.
- **Accessibility Optimized:** Includes Text-to-Speech (TTS), dark mode, and adjustable text sizes for inclusive use.

---

## 📊 Technical Benchmarking

We compared four deep learning architectures to find the optimal balance between speed and accuracy for sequential sign data:

| Architecture       | Test Accuracy | Note                                                |
| :----------------- | :------------ | :-------------------------------------------------- |
| **TCN (Proposed)** | **94.14%**    | **Superior temporal perception & efficiency**       |
| 1D-CNN             | 93.00%        | Strong local feature detection                      |
| Transformer        | 85.86%        | High complexity, required more data                 |
| LSTM               | 77.57%        | Suffered from vanishing gradients on long sequences |

---

## 🛠️ Tech Stack

- **Deep Learning:** PyTorch, MediaPipe (3D Landmarks), ONNX.
- **Frontend:** Next.js, Tailwind CSS v4, Lucide React.
- **Deployment:** Cloudflare Pages (Serverless).
- **Optimization:** AdamW Optimizer, Learning Rate Scheduling (ReduceLROnPlateau).

---

## 🏗️ Methodology

1. **Data Acquisition:** Recorded 5,200+ video samples using a green-screen environment.
2. **Feature Engineering:** Extracted 3D coordinates (x, y, z) for hands and pose. Implemented **Center Normalization** based on shoulder midpoints to ensure position invariance.
3. **Augmentation:** Applied real-time jittering and random rotation during training to prevent overfitting.
4. **Model Export:** Converted the PyTorch `.pth` model to **ONNX** format for cross-platform interoperability.

---
