# 排错记录

遇到问题就记录在这里：现象、原因、解决方法。下次遇到同类问题直接查。

---

## 常见问题速查

### MPS 不生效 — 终端显示 `Device: cpu`

**现象：** 启动时显示 `Device: cpu` 而非 `Device: mps`，出图极慢。

**可能原因：**
1. 使用了 x86 版本的 Python（Rosetta 模式）
2. PyTorch 版本不支持 MPS
3. 虚拟环境激活不正确

**排查步骤：**
```bash
# 确认 Python 架构
python3 -c "import platform; print(platform.machine())"
# 应输出 arm64，若输出 x86_64 则需换 Apple Silicon 原生 Python

# 确认 PyTorch MPS 可用
python3 -c "import torch; print(torch.backends.mps.is_available())"
# 应输出 True

# 确认 PyTorch 版本
python3 -c "import torch; print(torch.__version__)"
```

**解决方法：** 使用 miniforge（arm64）重建环境，重新安装 PyTorch。

---

### 模型路径找不到

**现象：** ComfyUI 界面中找不到已下载的模型。

**排查步骤：**
1. 确认 Crucial X9 已挂载（Finder 侧栏可见）
2. 确认模型文件在正确目录（如 `checkpoints/` 而非 `models/checkpoints/`）
3. 确认 `extra_model_paths.yaml` 中路径拼写正确，注意空格要用引号或转义
4. 重启 ComfyUI（修改 yaml 后需要重启才生效）

```bash
# 检查挂载点
ls /Volumes/
# 检查模型文件是否存在
ls "/Volumes/Crucial X9/AI_ComfyUI/models/checkpoints/"
```

---

### 模型加载慢

**现象：** 加载模型时需要等待很长时间。

**可能原因：**
- 通过低速扩展坞连接 X9
- 同时运行大量占内存的软件

**解决方法：**
- 使用 Crucial X9 原装线直连 MacBook Pro USB-C/Thunderbolt 接口
- 关闭 Final Cut、剪映、多余浏览器标签页
- 首次加载后会有缓存，后续会快一些

---

### 内存不足 / 系统卡顿

**现象：** 出图时系统明显卡顿，或提示内存不足。

**解决方法：**
- 先用 SDXL 入门，不要一开始就跑 Flux dev 完整版
- 降低分辨率（从 768x768 或 1024x1024 开始）
- 减少 batch size 到 1
- 使用 GGUF 量化版 Flux（Q4/Q5）
- 关闭无关软件

---

### ComfyUI 启动后浏览器无法访问

**现象：** 终端显示启动成功，但 `http://127.0.0.1:8188` 无法打开。

**排查：**
```bash
# 检查端口是否被占用
lsof -i :8188
```

若端口被占用，用 `--port` 换一个端口：
```bash
python main.py --port 8189
```

---

## 报错记录表

| 日期 | 报错信息（摘要） | 原因 | 解决方法 |
|---|---|---|---|
| | | | |
