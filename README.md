# ComfyUI-LTXVideo

ComfyUI-LTXVideo is a collection of custom nodes for ComfyUI, designed to provide useful tools for working with the LTXV model.
The model itself is supported in the core ComfyUI [code](https://github.com/comfyanonymous/ComfyUI/tree/master/comfy/ldm/lightricks).
The main LTXVideo repository can be found [here](https://github.com/Lightricks/LTX-Video).

# ⭐ 14.05.2025 – LTXVideo 13B 0.9.7 Distilled Release ⭐

### 🚀 What's New in LTXVideo 13B 0.9.7 Distilled
1. **LTXV 13B Distilled 🥳 0.9.7**<br>
   Delivers cinematic-quality videos at fraction of steps needed to run full model. Only 4 or 8 steps needed for single generation.<br>
   👉 [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-13b-0.9.7-distilled.safetensors)

2. **LTXV 13B Distilled Quantized 0.9.7**<br>
   Offers reduced memory requirements and even faster inference speeds.
   Ideal for consumer-grade GPUs (e.g., NVIDIA 4090, 5090).<br>
   ***Important:*** In order to get the best performance with the quantized version please install [q8_kernels](https://github.com/Lightricks/LTXVideo-Q8-Kernels) package and use dedicated flow below. <br>
   👉 [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-13b-0.9.7-distilled-fp8.safetensors)<br>
   🧩 Example ComfyUI flow available in the [Example Workflows](#example-workflows) section.

3. **Updated LTV 13B Quantized version**<br>
From now on all our 8bit quantized models are running natively in ComfyUI, still with our Q8 patcher node you will get the best inference speed.<br>
👉 [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-13b-0.9.7-dev-fp8.safetensors)<br>
# ⭐ 06.05.2025 – LTXVideo 13B 0.9.7 Release ⭐

### 🚀 What's New in LTXVideo 13B 0.9.7

1. **LTXV 13B 0.9.7**
   Delivers cinematic-quality videos at unprecedented speed.<br>
   👉 [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-13b-0.9.7-dev.safetensors)

2. **LTXV 13B Quantized 0.9.7**
   Offers reduced memory requirements and even faster inference speeds.
   Ideal for consumer-grade GPUs (e.g., NVIDIA 4090, 5090).
   Delivers outstanding quality with improved performance.<br>
   ***Important:*** In order to run the quantized version please install [LTXVideo-Q8-Kernels](https://github.com/Lightricks/LTXVideo-Q8-Kernels) package and use dedicated flow below. Loading the model in Comfy with LoadCheckpoint node won't work. <br>
   👉 [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-13b-0.9.7-dev-fp8.safetensors)<br>
   🧩 Example ComfyUI flow available in the [Example Workflows](#example-workflows) section.

3. **Latent Upscaling Models**
   Enables inference across multiple scales by upscaling latent tensors without decoding/encoding.
   Multiscale inference delivers high-quality results in a fraction of the time compared to similar models.<br>
   ***Important:*** Make sure you put the models below in **models/upscale_models** folder.<br>
   👉 Spatial upscaling: [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-spatial-upscaler-0.9.7.safetensors).<br>
   👉 Temporal upscaling: [Download here](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltxv-temporal-upscaler-0.9.7.safetensors).<br>
   🧩 Example ComfyUI flow available in the [Example Workflows](#example-workflows) section.


### Technical Updates

1. ***New simplified flows and nodes***<br>
1.1. Simplified image to video: [Download here](example_workflows/ltxv-13b-i2v-base.json).<br>
1.2. Simplified image to video with extension: [Download here](example_workflows/ltxv-13b-i2v-extend.json).<br>
1.3. Simplified image to video with keyframes: [Download here](example_workflows/ltxv-13b-i2v-keyframes.json).<br>

# 17.04.2025 ⭐ LTXVideo 0.9.6 Release ⭐

### LTXVideo 0.9.6 introduces:

1. LTXV 0.9.6 – higher quality, faster, great for final output. Download from [here](https://huggingface.co/Lightricks/LTX-Video/resolve/main/ltxv-2b-0.9.6-dev-04-25.safetensors).
2. LTXV 0.9.6 Distilled – our fastest model yet (only 8 steps for generation), lighter, great for rapid iteration. Download from [here](https://huggingface.co/Lightricks/LTX-Video/resolve/main/ltxv-2b-0.9.6-distilled-04-25.safetensors).

### Technical Updates

We introduce the __STGGuiderAdvanced__ node, which applies different CFG and STG parameters at various diffusion steps. All flows have been updated to use this node and are designed to provide optimal parameters for the best quality.
See the [Example Workflows](#example-workflows) section.

# 5.03.2025 ⭐ LTXVideo 0.9.5 Release ⭐

### LTXVideo 0.9.5 introduces:

1. Improved quality with reduced artifacts.
2. Support for higher resolution and longer sequences.
3. Frame and sequence conditioning (beyond the first frame).
4. Enhanced prompt understanding.
5. Commercial license availability.

### Technical Updates

Since LTXVideo is now fully supported in the ComfyUI core, we have removed the custom model implementation. Instead, we provide updated workflows to showcase the new features:

1. **Frame Conditioning** – Enables interpolation between given frames.
2. **Sequence Conditioning** – Allows motion interpolation from a given frame sequence, enabling video extension from the beginning, end, or middle of the original video.
3. **Prompt Enhancer** – A new node that helps generate prompts optimized for the best model performance.
   See the [Example Workflows](#example-workflows) section for more details.

### LTXTricks Update

The LTXTricks code has been integrated into this repository (in the `/tricks` folder) and will be maintained here. The original [repo](https://github.com/logtd/ComfyUI-LTXTricks) is no longer maintained, but all existing workflows should continue to function as expected.

## 22.12.2024

Fixed a bug which caused the model to produce artifacts on short negative prompts when using a native CLIP Loader node.

## 19.12.2024 ⭐ Update ⭐

1. Improved model - removes "strobing texture" artifacts and generates better motion. Download from [here](https://huggingface.co/Lightricks/LTX-Video/resolve/main/ltx-video-2b-v0.9.1.safetensors).
2. STG support
3. Integrated image degradation system for improved motion generation.
4. Additional initial latent optional input to chain latents for high res generation.
5. Image captioning in image to video [flow](example_workflows/ltxvideo-i2v.json).

## Installation

Installation via [ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) is preferred. Simply search for `ComfyUI-LTXVideo` in the list of nodes and follow installation instructions.

### Manual installation

1. Install ComfyUI
2. Clone this repository to `custom-nodes` folder in your ComfyUI installation directory.
3. Install the required packages:

```bash
cd custom_nodes/ComfyUI-LTXVideo && pip install -r requirements.txt
```

For portable ComfyUI installations, run

```
.\python_embeded\python.exe -m pip install -r .\ComfyUI\custom_nodes\ComfyUI-LTXVideo\requirements.txt
```

### Models

1. Download [ltx-video-2b-v0.9.1.safetensors](https://huggingface.co/Lightricks/LTX-Video/blob/main/ltx-video-2b-v0.9.1.safetensors) from Hugging Face and place it under `models/checkpoints`.
2. Install one of the t5 text encoders, for example [google_t5-v1_1-xxl_encoderonly](https://huggingface.co/mcmonkey/google_t5-v1_1-xxl_encoderonly/tree/main). You can install it using ComfyUI Model Manager.

## Example workflows

Note that to run the example workflows, you need to have some additional custom nodes, like [ComfyUI-VideoHelperSuite](https://github.com/kosinkadink/ComfyUI-VideoHelperSuite) and others, installed. You can do it by pressing "Install Missing Custom Nodes" button in ComfyUI Manager.

### Easy to use multi scale generation workflows

🧩 [Image to video mixed](example_workflows/ltxv13b-i2v-mixed-multiscale.json): mixed flow with full and distilled model for best quality and speed trade-off.<br>

### 13B model<br>
🧩 [Image to video](example_workflows/ltxv-13b-i2v-base.json)<br>
🧩 [Image to video with keyframes](example_workflows/ltxv-13b-i2v-keyframes.json)<br>
🧩 [Image to video with duration extension](example_workflows/ltxv-13b-i2v-extend.json)<br>
🧩 [Image to video 8b quantized](example_workflows/ltxv-13b-i2v-base-fp8.json)

### 13B distilled model<br>
🧩 [Image to video](example_workflows/13b-distilled/ltxv-13b-dist-i2v-base.json)<br>
🧩 [Image to video with keyframes](example_workflows/13b-distilled/ltxv-13b-dist-i2v-keyframes.json)<br>
🧩 [Image to video with duration extension](example_workflows/13b-distilled/ltxv-13b-dist-i2v-extend.json)<br>
🧩 [Image to video 8b quantized](example_workflows/13b-distilled/ltxv-13b-dist-i2v-base-fp8.json)

### Inversion

#### Flow Edit

🧩 [Download workflow](example_workflows/tricks/ltxvideo-flow-edit.json)<br>
![workflow](example_workflows/tricks/ltxvideo-flow-edit.png)

#### RF Edit

🧩 [Download workflow](example_workflows/tricks/ltxvideo-rf-edit.json)<br>
![workflow](example_workflows/tricks/ltxvideo-rf-edit.png)
