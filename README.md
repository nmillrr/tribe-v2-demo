# 🧠 TRIBE v2 Demo: Brain Activity Visualizer

Welcome to the **TRIBE v2** (Transformers for Robust, Interpretable Brain Encoding, version 2) demo notebook! This notebook allows you to predict and visualize how a human brain would respond—in real time—to video content such as TikToks, YouTube Shorts, or any other short video clip.

TRIBE v2 is a Meta AI model trained on fMRI data from people watching thousands of hours of video. It utilizes three neural encoders (vision, language, and audio) to estimate which brain regions would light up when watching a video.

## ✨ Features

- **No Coding Required**: Simple, step-by-step execution.
- **Multimodal Analysis**: Processes what you see (vision), speech/text (language), and music/sound effects (audio).
- **2D Brain Heatmaps**: Generates color-coded flat maps of brain surfaces showing predicted BOLD signal intensity.
- **Interactive 3D Viewer**: Provides an interactive, rotatable 3D brain model highlighting activation zones.
- **Difference Maps**: Upload multiple videos to compare and see exactly which brain regions respond differently across varying types of content.

## 📋 Prerequisites

Before running the notebook, you must have the following:

1. **Google Colab Pro / Pro+**: This notebook **requires an A100 GPU** with High RAM. A standard T4 GPU does not have enough memory (~30 GB required) and will crash.
2. **HuggingFace Account**: You need a free HuggingFace account and a **Read Access Token**.
3. **LLaMA 3.2 License**: TRIBE v2 uses LLaMA 3.2 internally. You must accept Meta's license at [huggingface.co/meta-llama/Llama-3.2-3B](https://huggingface.co/meta-llama/Llama-3.2-3B).

## 🚀 Getting Started

1. Open the notebook in [Google Colab](https://colab.research.google.com).
2. Go to **Runtime → Change Runtime Type** and select **A100 GPU** and check **High RAM**.
3. Add your HuggingFace token to Colab Secrets:
   - Click the 🔑 **key icon** in the left sidebar.
   - Click **"Add new secret"** with the Name `HF_TOKEN`.
   - Paste your read token and toggle **"Notebook access"** to **ON**.
4. Run through the sections sequentially:
   - **Section 1**: Fixes the NumPy version. *⚠️ You must restart the runtime after this cell completes.*
   - **Section 2-5**: Installs dependencies, authenticates your HF token, downloads the LLaMA model (~6 GB), and loads TRIBE v2.
   - **Section 6**: Upload your `.mp4` video files (10-60 seconds recommended).
   - **Section 7-11**: Runs predictions and generates visual outputs (heatmaps, 3D viewers, difference maps) and exports the results to your local machine.

## 🧠 Understanding the Results

Your generated brain maps show predicted activation across the cortex:
- **Visual Cortex (Back)**: Responds to movement, color, faces, and scene complexity.
- **Auditory Cortex (Sides)**: Processes speech, music, and sound.
- **Default Mode Network (Center)**: Associated with social cognition and emotionally relatable content.
- **Reward Circuits (Deep/Central)**: Linked to dopamine-driven engagement and high-stimulation content.

*Note: The predictions reflect population averages derived from fMRI data and represent a statistically typical response, including a ~5-second hemodynamic delay.*

## 🛠️ Troubleshooting

- **`CUDA out of memory`**: Ensure you are using an **A100 GPU**, not a T4.
- **`401 Unauthorized` / `403 Forbidden`**: Make sure your `HF_TOKEN` is loaded correctly in Colab Secrets and that you have accepted the LLaMA 3.2 license.
- **Module errors after restart**: Make sure you re-run all cells from Section 2 onwards after the initial runtime restart in Section 1.

---
Enjoy visualizing how your brain reacts to your favorite videos!
