<div align="center">

# Mage-Flow: 

## An Efficient Native-Resolution Foundation Model for Image Generation and Editing

<p>
  <b>Microsoft Mage Team</b>
</p>

<p>
  <a href="https://microsoft.github.io/Mage"><img alt="Project Page" src="https://img.shields.io/badge/%F0%9F%8C%90-Project%20Page-blue" height="22" /></a>
  &nbsp;
  <a href="LICENSE"><img alt="Mage-Flow License: MIT" src="https://img.shields.io/badge/Mage--Flow%20License-MIT-green.svg" height="22" /></a>
  &nbsp;
  <a href="https://arxiv.org/abs/2607.19064"><img alt="arXiv" src="https://img.shields.io/badge/arXiv-Mage--Flow-b31b1b" height="22" /></a>
  
</p>



</div>

<div align="center">

</div>

---


**Mage-Flow** is a compact 4B generative stack for **text-to-image generation** and **instruction-based image editing**, built from two co-designed components: **Mage-VAE** (a lightweight, high-fidelity latent tokenizer) and a **Native-Resolution Multimodal Diffusion Transformer** trained with rectified flow matching. Each task ships in **Base**, **RL-aligned**, and **4-step Turbo** variants.

**Highlights**

- **Compact & competitive.** A single 4B family for generation *and* editing that matches or beats much larger open systems (Qwen-Image 20B, Z-Image 6B, FLUX.2 32B, FireRed-Image-Edit 20B).
- **Efficient tokenizer.** Mage-VAE matches FLUX.2-VAE reconstruction fidelity using **~12× / ~22× fewer encode / decode MACs per pixel**, removing the VAE high-resolution bottleneck.
- **Native resolution.** One checkpoint generates from **512 to 2048** on any aspect ratio, including extreme **4:1** (e.g. `512×2048`, `2048×512`).
- **System-level speed.** Native-resolution packing + fused CUDA kernels cut per-step training time from **~1.93 s → ~0.78 s** (**~2.5× faster training**); at `1024²` on a single A100, **Mage-Flow-Turbo 0.59 s/image** and **Mage-Flow-Edit-Turbo 1.02 s/edit**.
- **Versatile editing.** Mage-Flow-Edit supports semantic content editing, appearance transformation, image restoration, and structure-aware outputs within a unified image-and-text-conditioned model.


## 📝 Citation

```bibtex
@article{yang2026magevl,
  title={Mage-VL: An Efficient Codec-Native Streaming Multimodal Foundation Model},
  author={Yang, Senqiao and Zhang, Kaichen and Jia, Zhaoyang and Guo, Jinghao and Shen, Yifei and Zhang, Xinjie and Zhang, Xiaoyi and Wang, Haoqing and Li, Xiao and Zhang, Peng and An, Xiang and Xie, Yin and Liu, Zhening and Guo, Xun and Li, Jiahao and Zheng, Shicheng and Wang, Jinglu and Guo, Zongyu and Xie, Wenxuan and Zheng, Zihan and Luo, Yuxuan and Li, Bin and Lu, Yan},
  journal={arXiv preprint arXiv:2607.24904},
  year={2026}
}

@article{zhang2026mageflow,
  title={Mage-Flow: An Efficient Native-Resolution Foundation Model for Image Generation and Editing},
  author={Zhang, Xinjie and Zhang, Peng and Zheng, Shicheng and Guo, Jinghao and Jia, Zhaoyang and Shen, Yifei and Guo, Xun and Luo, Yuxuan and Li, Jiahao and Xie, Wenxuan and Pu, Fanyi and Zhang, Xiaoyi and Zhang, Kaichen and Guo, Zongyu and Bi, Tianci and Gui, Dongnan and Liu, Zhening and Wen, Zimo and Zheng, Zihan and Yang, Senqiao and Li, Xiao and Wang, Jinglu and Li, Bin and Lu, Yan},
  journal={arXiv preprint arXiv:2607.19064},
  year={2026}
}
```

## Responsible AI

These models are released for research purposes only and are not intended for product or service deployment. Responsible AI considerations were incorporated throughout the development process, including data selection, model training, and evaluation. The training data includes a combination of public, licensed, and internal datasets that were processed to remove clearly identifiable personal information and reduce harmful content where possible. However, as the data is largely sourced from web-scale collections, it may contain biases or uneven representation. As a result, the models may generate outputs that are inaccurate, biased, or inappropriate under certain prompts. The models should be used in controlled research settings with appropriate human oversight, and downstream users are responsible for applying additional safeguards — such as content moderation, validation, and compliance checks — before broader use.

## License

**Mage-Flow**  [MIT](LICENSE) 
