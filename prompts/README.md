# 提示词库

每条都是自包含的，复制到生成框就能跑。需要参考素材的会写明传什么。

所有提示词遵循同一套结构，改写时对照 [提示词公式](../docs/02-prompt-formula.md) 替换对应部分即可。

## 影视创作

| 提示词 | 模式 | 时长 | 用到的能力 |
|---|---|---|---|
| [无对白叙事短片](./film/silent-narrative.md) | 文生视频 | 30s | 30s 直出、一镜到底 |
| [多角色群像戏](./film/ensemble-scene.md) | 参考生成 | 30s | 多主体参考、多音色 |
| [动作迁移](./film/motion-transfer.md) | 参考生成 | 10s | 视频动作参考 |
| [改年龄与表情](./film/age-and-expression-edit.md) | 视频编辑 | 对齐原片 | 局部编辑、微表情 |
| [一键换画风](./film/style-swap.md) | 视频编辑 | 对齐原片 | 风格改写 |

## 广告电商

| 提示词 | 模式 | 时长 | 用到的能力 |
|---|---|---|---|
| [家居 TVC](./ads-ecommerce/furniture-tvc.md) | 文生视频 | 30s | 30s 直出、影棚转场景 |
| [3D 动画广告](./ads-ecommerce/3d-animated-ad.md) | 文生视频 | 30s | 时间轴分镜、夸张演出 |
| [SKU 批量换款](./ads-ecommerce/sku-batch-swap.md) | 视频编辑 | 对齐原片 | 主体替换 |
| [出海本地化](./ads-ecommerce/localization.md) | 视频编辑 | 对齐原片 | 多语种、换人种 |

## 知识科普

| 提示词 | 模式 | 时长 | 用到的能力 |
|---|---|---|---|
| [科学原理可视化](./education/science-visualization.md) | 文生视频 | 30s | 时间轴、旁白同步 |
| [儿童科普动画](./education/kids-animation.md) | 文生视频 | 30s | 风格化、口播 |
| [多语言讲解](./education/multilingual-guide.md) | 文生视频 | 30s | 语言切换、形象一致 |

## 工业制造

| 提示词 | 模式 | 时长 | 用到的能力 |
|---|---|---|---|
| [FPV 穿越飞行](./industrial/fpv-flythrough.md) | 文生视频 | 25s | 路径控制、一镜到底 |
| [装配流程演示](./industrial/assembly-demo.md) | 参考生成 | 30s | 说明书图参考 |
| [白模转成片](./industrial/whitebox-render.md) | 参考生成 | 对齐原片 | 白模渲染 |

## 创意实验

| 提示词 | 模式 | 时长 | 用到的能力 |
|---|---|---|---|
| [多空间穿梭](./creative/room-to-room.md) | 文生视频 | 30s | 一镜到底、风格突变 |
| [拟人化 IP 角色](./creative/anthropomorphic-ip.md) | 文生视频 | 20s | 角色演出、口音控制 |
| [音频驱动卡点](./creative/audio-driven-beat.md) | 参考生成 | 30s | 只参考音频 🆕 |

---

## 文件格式

投稿请遵循这个结构：

````markdown
# 标题

**模式**：文生视频 / 参考生成 / 视频编辑 | **时长**：30s | **画幅**：16:9

## 需要的素材
- @图片1 — 说明
（无需素材则写「无」）

## 提示词
```text
...
```

## 效果说明
一两句话说清这条能出什么。

## 改法
- 换场景：改哪一句
- 换风格：改哪一句
````

---

回到 [README](../README.md)
