# 工作流记录

记录每个工作流的用途、所需模型和使用心得。工作流 JSON 文件存放在 Crucial X9 的 `AI_ComfyUI/workflows/` 目录。

---

## 目录结构规范

```
workflows/
├── 01_basic_text_to_image/    # 文生图基础
├── 02_sdxl/                   # SDXL 工作流
├── 03_lora/                   # LoRA 测试
├── 04_flux/                   # Flux 工作流
├── 05_upscale/                # 图片放大
├── 06_inpaint/                # 局部重绘
├── 07_controlnet/             # ControlNet
├── 08_video/                  # 视频相关
└── 99_archive/                # 旧版归档
```

每个工作流文件夹建议包含：
- `workflow.json` — ComfyUI 工作流文件
- `sample_output.png` — 代表性输出图
- `README.md` — 所需模型列表 + 使用说明

---

## 工作流记录表

### 模板

```
## 工作流名称

- 文件路径：workflows/xx_xxx/workflow.json
- 创建日期：
- 用途：
- 所需模型：
  - checkpoints:
  - lora:
  - vae:
  - controlnet:
- 推荐分辨率：
- 推荐采样器：
- 推荐步数：
- 平均出图时间（Mac M4 Pro）：
- 适合用于：
- 已知问题：
- 备注：
```

---

<!-- 在下方按模板添加每个工作流的记录 -->
