# 模型测试记录

每下载一个模型就填一条。目的：避免重复下载、记住哪个模型适合什么用途、控制授权风险。

---

## 管理原则

- 按类型分目录：checkpoints / diffusion_models / loras / vae / controlnet / upscale_models
- 每个模型记录来源和授权，商业用途前必须确认 license
- 定期清理低质量和重复模型
- 同类模型优先保留测试效果最好的 1-2 个

---

## 入门阶段推荐模型

| 类型 | 模型名 | 优先级 | 原因 |
|---|---|---|---|
| SDXL | RealVisXL | 高 | 写实效果好，资料多 |
| SDXL | Juggernaut XL | 高 | 人像表现强 |
| SDXL | DreamShaper XL | 中 | 风格多样 |
| Flux | Flux.1 schnell GGUF Q4/Q5 | 中 | 速度快，Mac 兼容好 |
| Flux | Flux.1 dev GGUF Q4/Q5 | 低 | 质量更高但慢 |

Mac 上 Flux 优先选 GGUF Q4/Q5/Q6，不建议入门阶段用 FP8（MPS 兼容性问题）。

---

## 模型记录表

### 模板

```
## 模型名称

- 类型：checkpoints / lora / vae / controlnet / ...
- 文件名：
- 文件大小：
- 来源网站：
- 版本：
- 下载日期：
- 适合用途：
- 推荐正向提示词关键词：
- 推荐反向提示词：
- 推荐采样器：
- 推荐步数：
- 推荐 CFG：
- 是否适合商用：是 / 否 / 需确认
- License 链接：
- 综合评分（1-5）：
- 备注：
```

---

<!-- 在下方按模板添加每个模型的记录 -->
