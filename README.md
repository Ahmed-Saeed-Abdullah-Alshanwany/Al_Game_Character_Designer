# 🎮 AI Game Character Designer

An interactive, AI-powered toolkit for generating and fine-tuning high-quality game characters using **Stable Diffusion 1.5** and **Gradio**. 

This repository demonstrates two distinct approaches to AI image generation, fully optimized to run efficiently on the free **Google Colab (T4 GPU)** tier.

## 📂 Repository Structure

### 1. Base Model Generator (`AI_Game_Character_Designer_Gradio_Colab.ipynb`)
A lightweight, memory-optimized text-to-image pipeline using the pre-trained Stable Diffusion 1.5 model.
* **Core Technologies:** `diffusers`, `transformers`, `gradio`.
* **Features:** Memory slicing for T4 GPUs (VAE & Attention slicing), interactive Gradio UI, and dynamic control over guidance scale, inference steps, and seeds.
* **Best for:** General game character design concepts (e.g., Cyberpunk warriors, Sci-Fi soldiers, Fantasy knights).

### 2. Fine-Tuning Edition - LoRA (`Anime_Game_Character_LoRA.ipynb`)
An advanced, end-to-end pipeline demonstrating Parameter-Efficient Fine-Tuning (PEFT) using **LoRA (Low-Rank Adaptation)**.
* **Core Technologies:** `peft`, `accelerate`, `datasets`, custom PyTorch `Dataset` class.
* **Features:** * Downloads and streams the `huggan/anime-faces` dataset from HuggingFace.
  * Freezes the VAE and Text Encoder to train only the UNet's attention layers.
  * Utilizes Mixed Precision (`fp16`) and Gradient Accumulation for optimal VRAM usage.
  * Merges the trained LoRA weights with the base UNet for seamless Gradio deployment.
* **Trigger Word:** `anime character, sks style`
* **Best for:** Specialized, consistent anime-style character generation.

## 🚀 Key Features
* **Hardware Optimized:** Both pipelines run seamlessly on a 15GB VRAM environment without Out-Of-Memory (OOM) errors.
* **Interactive UI:** Built-in Gradio web interfaces allow users to test prompts and parameters in real-time.
* **Extensible:** The LoRA notebook acts as a template; you can swap the dataset and trigger words to train the model on any custom art style.

## 🖼️ Gallery
*(Examples of characters generated using this toolkit)*

<div style="display: flex; justify-content: space-between;">
  <img src="image (1).webp" width="48%" alt="Base Model: Cyberpunk Warrior">
  <img src="image (3).jpeg" width="48%" alt="LoRA Fine-Tuned: Anime Mage Face">
</div>

## 💻 How to Use
1. Open either notebook in Google Colab.
2. Run the setup cells to install the required dependencies.
3. **(For LoRA)** Execute the training loop to generate your custom weights.
4. Run the final cell to launch the Gradio interface and click the generated public link to start designing!

## 👨‍💻 About the Author
**Ahmed Saeed Abdullah Alshanwany**
AI & Computer Science Student (Menoufia University & University of the People). Passionate about Generative AI, Computer Vision, NLP, and building practical, end-to-end AI pipelines.
