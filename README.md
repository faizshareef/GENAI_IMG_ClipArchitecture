# 🎨 Text-to-Image & Video Generation using CLIP + VQGAN

A Generative AI project that generates **high-resolution images and interpolated videos from text prompts** using multimodal contrastive learning and transformer-based generative modeling.

This project combines:

- 🔗 CLIP by OpenAI  
- 🎨 VQGAN (Taming Transformers) by CompVis  

---

## 🚀 Project Overview

This project demonstrates how natural language prompts can be transformed into visually coherent images and smooth video transitions using multimodal AI architectures.

Instead of training from scratch, we:

1. Encode text prompts using CLIP  
2. Initialize random latent vectors  
3. Optimize latent vectors using cosine similarity loss  
4. Decode optimized latents into images using VQGAN  
5. Interpolate between latent vectors to generate video sequences  

This showcases practical implementation of advanced **Multimodal Generative AI systems**.

---

## 🧠 Architecture Explanation

### 1️⃣ CLIP (Contrastive Language–Image Pretraining)

CLIP learns a shared embedding space between text and images.

- Text Encoder → Converts prompt into embedding vector  
- Image Encoder → Converts image into embedding vector  
- Similarity Function → Aligns image features with text features  

The objective is to maximize cosine similarity between the prompt embedding and generated image embedding.

---

### 2️⃣ VQGAN (Vector Quantized Generative Adversarial Network)

VQGAN is responsible for image synthesis.

- Operates in discrete latent space  
- Uses vector quantization  
- Combines transformer blocks with GAN-based training  
- Generates high-resolution visual outputs  

Optimized latent vectors are decoded into final images.

---

## 🏗 Generation Pipeline

```
Text Prompt
     ↓
CLIP Text Encoder
     ↓
Random Latent Initialization
     ↓
Latent Optimization (Gradient Descent)
     ↓
VQGAN Decoder
     ↓
Generated Image
     ↓
Latent Interpolation
     ↓
Generated Video
```

---

## 🛠 Tech Stack

- Python  
- PyTorch  
- Torchvision  
- CLIP  
- VQGAN  
- Google Colab (GPU Recommended)  

---

## ⚙️ Setup Instructions (Google Colab Recommended)

### 1️⃣ Enable GPU
Runtime → Change Runtime Type → GPU  

---

### 2️⃣ Clone Required Repositories

```bash
!git clone https://github.com/openai/CLIP
!git clone https://github.com/CompVis/taming-transformers
```

---

### 3️⃣ Install Dependencies

```bash
pip install torch torchvision ftfy regex tqdm
pip install omegaconf pytorch-lightning
```

---

### 4️⃣ Download Pretrained VQGAN Model

```bash
!wget <checkpoint_url> -O models/vqgan_imagenet_f16_16384/checkpoints/last.ckpt
!wget <config_url> -O models/vqgan_imagenet_f16_16384/configs/model.yaml
```

---

## 🧩 Core Functional Components

### ✅ Helper Functions
- Tensor to image conversion  
- Pixel normalization and clipping  
- Axis transposition for visualization  

### ✅ Prompt Encoding
- Tokenization via CLIP  
- Text embedding extraction  
- Include / Exclude / Extra prompt logic  

### ✅ Data Augmentation
- Random horizontal flip  
- Random affine transforms  
- Multi-crop strategy  
- Noise injection  

### ✅ Optimization Strategy
- Cosine similarity loss  
- Weight decay regularization  
- Learning rate scheduling  
- Gradient-based latent updates  

---

## 🎬 Video Generation via Latent Interpolation

To generate videos:

1. Select two prompts  
2. Generate corresponding latent vectors  
3. Perform linear interpolation in latent space  
4. Decode intermediate vectors  
5. Combine frames into a video sequence  

This produces smooth visual transitions between concepts.

---

## 🖼 Example Prompts

- “A futuristic cyberpunk city at night”  
- “Elephants dancing in a neon forest”  
- “A surreal blue tree in the desert”  
- “A glass dragon flying through space”  

---

## 📊 Concepts Demonstrated

- Multimodal contrastive learning  
- Transformer-based generative modeling  
- Vector quantization  
- GAN-based synthesis  
- Latent space manipulation  
- Prompt engineering  
- Hyperparameter optimization  
- Data augmentation techniques  

---

## 🎯 Applications

- AI-generated artwork  
- Creative design systems  
- Generative animation pipelines  
- Prompt-driven visual storytelling  
- Research in multimodal AI  

---

## 🔮 Future Enhancements

- Add Streamlit Web UI  
- Deploy on cloud GPU  
- Compare with Stable Diffusion  
- Add style-conditioning controls  
- Extend to text-to-3D or motion models  

---

## OUTPUT IMAGES

<img width="742" height="705" alt="output1" src="https://github.com/user-attachments/assets/8218d272-640c-4a34-a666-01e226e306e2" />

<img width="733" height="667" alt="output2" src="https://github.com/user-attachments/assets/9d179fe2-43d3-454c-91af-5baf8590a2e0" />

<img width="718" height="557" alt="output3" src="https://github.com/user-attachments/assets/e930f477-75e8-4d09-beb3-c50e8b32da84" />


## 🎥 Demo Preview






