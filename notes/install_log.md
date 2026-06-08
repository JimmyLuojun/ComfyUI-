# 安装记录

记录安装过程、配置决策和已解决的环境问题。

---

## 环境信息

| 项目 | 值 |
|---|---|
| 电脑 | MacBook Pro |
| 芯片 | Apple Silicon M4 Pro |
| 内存 | 24GB 统一内存 |
| 系统 | macOS |
| 外接硬盘 | Crucial X9 2TB，exFAT 格式 |
| ComfyUI 路径 | `~/AI/ComfyUI`（待确认） |
| 模型路径 | Crucial X9 `/AI_ComfyUI/models/`（待确认） |

---

## 硬盘方案决策

**决定：保留 exFAT，不格式化为 APFS。**

原因：
- 后续可能在 Windows 上使用，exFAT 跨平台兼容更好
- ComfyUI 模型文件是大文件（.safetensors/.gguf），exFAT 能胜任
- Python 虚拟环境不放 X9，避免 exFAT 权限/软链接问题

注意：每次拔盘前必须在 Finder 中点击推出，exFAT 无日志保护机制。

---

## 安装步骤

### 1. 在 Crucial X9 创建目录结构

```bash
mkdir -p /Volumes/Crucial\ X9/AI_ComfyUI/models/{checkpoints,diffusion_models,clip,vae,loras,controlnet,upscale_models}
mkdir -p /Volumes/Crucial\ X9/AI_ComfyUI/{workflows,outputs,references,notes}
```

### 2. 安装 Python 环境（miniforge，Apple Silicon 原生）

```bash
# 下载 miniforge（Apple Silicon 版本）
# https://github.com/conda-forge/miniforge/releases
# 选择 Miniforge3-MacOSX-arm64.sh

bash Miniforge3-MacOSX-arm64.sh
conda create -n comfyui python=3.11
conda activate comfyui
```

或使用系统 Python + venv（需 Python 3.10+）：

```bash
python3 -m venv ~/AI/venv
source ~/AI/venv/bin/activate
```

### 3. 克隆 ComfyUI

```bash
mkdir -p ~/AI
cd ~/AI
git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI
```

### 4. 安装依赖

```bash
pip install -r requirements.txt
```

### 5. 配置 extra_model_paths.yaml

```bash
cp ~/AI/ComfyUI/extra_model_paths.yaml.example ~/AI/ComfyUI/extra_model_paths.yaml
```

编辑文件，添加 X9 模型路径：

```yaml
x9_models:
  base_path: /Volumes/Crucial X9/AI_ComfyUI/models/
  checkpoints: checkpoints/
  diffusion_models: diffusion_models/
  clip: clip/
  vae: vae/
  loras: loras/
  controlnet: controlnet/
  upscale_models: upscale_models/
```

注意：外接硬盘未挂载时 ComfyUI 仍可启动，只是找不到 X9 上的模型。

### 6. 启动并验证

```bash
cd ~/AI/ComfyUI
python main.py
```

检查终端输出中是否有：

```
Device: mps
```

浏览器访问：`http://127.0.0.1:8188`

---

## 安装记录

| 日期 | 操作 | 结果 | 备注 |
|---|---|---|---|
| | | | |

---

## 已解决的环境问题

> 遇到安装相关报错记录在这里，排查问题记录在 troubleshooting.md。
