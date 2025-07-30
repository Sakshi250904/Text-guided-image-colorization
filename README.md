Here is the **fully edited `README.md`** with the **image loading fixed** using proper relative paths, cleaner formatting, and verified Markdown syntax.

---

### ✅ Before You Use:

Make sure the following project structure exists:

```
text-guided-image-colorization/
├── README.md
├── images/
│   ├── framework.jpg
│   └── gradio_ui.png
```

---

### ✅ Final `README.md` (Edited):

````markdown
# Text-Guided-Image-Colorization

This project utilizes the power of **Stable Diffusion (SDXL/SDXL-Light)** and the **BLIP (Bootstrapping Language-Image Pre-training)** captioning model to provide an interactive image colorization experience. Users can influence the generated colors of objects within images, making the colorization process more personalized and creative.

![Framework](images/framework.jpg)

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Dataset Usage](#dataset-usage)
- [Training](#training)
- [Evaluation](#evaluation)
- [Results](#results)
- [License](#license)

## News  
- **(2024/11/23)** The project is now available on [Hugging Face Spaces](https://huggingface.co/spaces/fffiloni/text-guided-image-colorization) 🎉 Big thanks to @fffiloni!

---

## Features

- **Interactive Colorization**: Users can specify desired colors for different objects in the image.
- **ControlNet Approach**: Enhanced colorization capabilities through retraining with ControlNet, allowing SDXL to better adapt to the image colorization task.
- **High-Quality Outputs**: Leverage the latest advancements in diffusion models to generate vibrant and realistic colorizations.

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/nick8592/text-guided-image-colorization.git
cd text-guided-image-colorization
````

### 2. Install Dependencies

Make sure Python 3.7 or higher is installed:

```bash
pip install -r requirements.txt
```

Install PyTorch (adjust CUDA version accordingly):

```bash
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu118
```

Replace `cu118` with your CUDA version. Check [PyTorch Installation Guide](https://pytorch.org/get-started/locally/).

### 3. Download Pre-trained Models

Download from Hugging Face:

| Model                               | Link                                                                        |
| :---------------------------------- | :-------------------------------------------------------------------------- |
| SDXL-Lightning Caption              | [Download](https://huggingface.co/nickpai/sdxl_light_caption_output)        |
| SDXL-Lightning Custom (Recommended) | [Download](https://huggingface.co/nickpai/sdxl_light_custom_caption_output) |

Put the downloaded model in:

```
text-guided-image-colorization/sdxl_light_caption_output/
```

---

## Quick Start

1. Launch the interface:

```bash
python gradio_ui.py
```

2. Open the provided URL in your browser.

3. Upload a grayscale image and (optionally) provide prompts to control object colors.

4. The model will generate colorized versions of the image.

![Gradio UI](images/gradio_ui.png)

---

## Dataset Usage

For dataset instructions, visit the companion repo:
[Dataset-for-Image-Colorization](https://github.com/nick8592/Dataset-for-Image-Colorization)

---

## Training

Use the following training scripts:

* `train_controlnet.sh` – for SD v2.1
* `train_controlnet_sdxl.sh` – for SDXL
* `train_controlnet_sdxl_light.sh` – for SDXL-Lightning

> ⚠️ Due to GPU limitations, training was not fully verified. Test and tweak as needed.

---

## Evaluation

You can evaluate trained models with:

* `eval_controlnet.sh`
* `eval_controlnet_sdxl_light.sh`
* `eval_controlnet_sdxl_light_single.sh`

---

## Results

### 📌 Prompt-Guided Example

|                 Input                 |                          Green Shirt                         |                          Purple Shirt                          |                         Red Shirt                        |
| :-----------------------------------: | :----------------------------------------------------------: | :------------------------------------------------------------: | :------------------------------------------------------: |
| ![Gray](images/000000022935_gray.jpg) | ![Green](images/000000022935_green_shirt_on_right_girl.jpeg) | ![Purple](images/000000022935_purple_shirt_on_right_girl.jpeg) | ![Red](images/000000022935_red_shirt_on_right_girl.jpeg) |

### 📌 Prompt-Free Colorization

|                  Gray                 |                Colorized                |            Ground Truth           |
| :-----------------------------------: | :-------------------------------------: | :-------------------------------: |
| ![Gray](images/000000025560_gray.jpg) | ![Color](images/000000025560_color.jpg) | ![GT](images/000000025560_gt.jpg) |

---

## Related Articles

* [Image Colorization: Bringing Black and White to Life](https://medium.com/generative-ai/image-colorization-bringing-black-and-white-to-life-b14d3e0db763)
* [Understanding RGB, YCbCr, and Lab Color Spaces](https://medium.com/@weichenpai/understanding-rgb-ycbcr-and-lab-color-spaces-f9c4a5fe485a)
* [Comparison Between CLIP and BLIP Models](https://medium.com/generative-ai/comparison-between-clip-and-blip-models-42f8a6ff4b1e)
* [A Guide to Gradio for ML UI](https://medium.com/generative-ai/a-step-by-step-guide-to-interactive-machine-learning-with-gradio-3fde7541da52)
