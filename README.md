# ComfyUI Mac 本地学习项目

在 MacBook Pro (M4 Pro, 24GB) + Crucial X9 2TB 上安装、配置、学习 ComfyUI，建立稳定可复用的本地 AI 绘图工作环境，为内容创作（课程封面、短视频素材、漫剧分镜）做准备。

---

## 1. 这个项目是干什么的

学习 ComfyUI 节点工作流，在 Mac 本地运行 SD 1.5、SDXL、Flux GGUF 等图像生成模型，沉淀可复用的工作流和提示词资产，最终服务于 AI 内容创作。

详细学习路线见 → [notes/learning_roadmap.md](notes/learning_roadmap.md)

---
在这里增加了一点文字。

## 2. 文件组织方式

**原则：程序和环境放 Mac 内置硬盘，大文件放 Crucial X9（exFAT）。**

```
Mac 内置硬盘
└── ~/AI/ComfyUI/          # ComfyUI 程序 + Python 虚拟环境

Crucial X9 (exFAT)
└── AI_ComfyUI/
    ├── models/
    │   ├── checkpoints/   # SD1.5 / SDXL 大模型
    │   ├── diffusion_models/  # Flux / 新架构模型
    │   ├── clip/
    │   ├── vae/
    │   ├── loras/
    │   ├── controlnet/
    │   └── upscale_models/
    ├── workflows/         # 工作流 JSON
    ├── outputs/           # 生成图片与视频
    ├── references/        # 参考图、素材
    └── notes/             # 学习笔记（本目录镜像）
```

通过 `extra_model_paths.yaml` 让 ComfyUI 读取 X9 上的模型目录。

详细安装与硬盘配置见 → [notes/install_log.md](notes/install_log.md)

---

## 3. ComfyUI 启动方式

```bash
cd ~/AI/ComfyUI
conda activate comfyui
python main.py
```

启动后在终端确认：

```
Device: mps
```

`mps` = Apple Silicon Metal GPU 加速正常。浏览器访问 `http://127.0.0.1:8188`。

模型放置位置和 `extra_model_paths.yaml` 配置见 → [notes/install_log.md](notes/install_log.md)

---

## 4. 遇到问题 / 学习记录

| 问题类型 | 查哪里 |
|---|---|
| 安装报错、路径问题、MPS 不生效 | [notes/troubleshooting.md](notes/troubleshooting.md) |
| 模型下载记录、效果评估 | [notes/model_log.md](notes/model_log.md) |
| 工作流存档、节点说明 | [notes/workflow_log.md](notes/workflow_log.md) |
| 提示词模板、采样器参数 | [notes/prompt_log.md](notes/prompt_log.md) |
| 安装过程、配置决策记录 | [notes/install_log.md](notes/install_log.md) |

---

## 当前进度

- [ ] 创建 X9 目录结构
- [ ] 安装 Python 环境（推荐 miniforge）
- [ ] 克隆并安装 ComfyUI
- [ ] 配置 `extra_model_paths.yaml`
- [ ] 确认 MPS 加速正常
- [ ] 下载第一个 SDXL 模型
- [ ] 生成第一张图片
- [ ] 保存第一个基础工作流
- [ ] 尝试 LoRA
- [ ] 尝试 Flux GGUF
