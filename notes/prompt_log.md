# 提示词记录

积累有效的提示词模板和采样器参数组合，避免重复试错。

---

## 通用负向提示词

适用于大多数写实类 SDXL 模型：

```
worst quality, low quality, normal quality, jpeg artifacts, blurry, out of focus,
watermark, text, signature, username, extra limbs, extra fingers, missing fingers,
deformed hands, bad anatomy, disfigured, ugly, poorly drawn face
```

---

## 采样器参数参考

| 场景 | 采样器 | Steps | CFG | 说明 |
|---|---|---|---|---|
| 写实人像（SDXL） | DPM++ 2M Karras | 25-30 | 6-7 | 稳定，细节好 |
| 快速出图 | LCM | 6-8 | 1.5-2 | 速度快，质量略低 |
| 风格插画 | Euler a | 20-25 | 7-8 | 多样性强 |
| Flux schnell | — | 4 | 1 | Flux 专用，步数少 |
| Flux dev | — | 20-25 | 3.5 | 质量更高 |

---

## 提示词模板库

### 模板格式

```
## 模板名称

**用途：**
**适配模型：**
**正向提示词：**

**负向提示词：**

**参数：** 采样器 / Steps / CFG / 分辨率
**效果说明：**
**来源 / 日期：**
```

---

### 写实人像基础模板

**用途：** 写实风格人物图，适合课程封面、内容创作
**适配模型：** RealVisXL、Juggernaut XL

**正向提示词：**
```
masterpiece, best quality, ultra detailed, 1girl, 25 years old, beautiful face,
natural lighting, professional photography, sharp focus, 8k uhd
```

**负向提示词：**
```
worst quality, low quality, blurry, deformed, bad anatomy, extra limbs
```

**参数：** DPM++ 2M Karras / 28 steps / CFG 7 / 832x1216
**效果说明：** 稳定，适合初学练习提示词

---

<!-- 在下方继续添加提示词模板 -->
