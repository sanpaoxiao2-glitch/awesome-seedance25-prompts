# Awesome Seedance 2.5 Prompts

> Seedance 2.5（Doubao-Seedance-2.5）是字节跳动豆包大模型团队的多模态视频生成模型。
> 这个仓库整理它的能力边界、提示词写法和可直接复制的模板，不讲原理，只讲怎么写才出片。

[English](./README_EN.md) · [提示词公式](./docs/02-prompt-formula.md) · [提示词库](./prompts/) · [翻车排查](./docs/07-troubleshooting.md)

| | | | |
|---|---|---|---|
| ![FPV 穿越](./assets/clips/fpv-flythrough.webp) | ![3D 动画广告](./assets/clips/3d-animated-ad.webp) | ![动作迁移](./assets/clips/motion-transfer.webp) | ![群像戏](./assets/clips/ensemble-scene.webp) |
| [FPV 穿越](./prompts/industrial/fpv-flythrough.md) | [3D 动画广告](./prompts/ads-ecommerce/3d-animated-ad.md) | [动作迁移](./prompts/film/motion-transfer.md) | [群像戏](./prompts/film/ensemble-scene.md) |
| ![科普可视化](./assets/clips/science-visualization.webp) | ![家居 TVC](./assets/clips/furniture-tvc.webp) | ![改年龄表情](./assets/clips/age-expression-edit.webp) | ![多语种](./assets/clips/multilingual.webp) |
| [科普可视化](./prompts/education/science-visualization.md) | [家居 TVC](./prompts/ads-ecommerce/furniture-tvc.md) | [改年龄表情](./prompts/film/age-and-expression-edit.md) | [多语种口播](./prompts/ads-ecommerce/localization.md) |

---

## 它和上一代到底差在哪

一句话：**从「生成一个镜头」变成「生成一段片子」**。

| 维度 | Seedance 2.0 | Seedance 2.5 |
|---|---|---|
| 单段时长 | 15s | **30s 直出**，不用后期拼 |
| 参考素材 | 9 张图 + 3 段音视频 | **50 个**（30 图 + 10 视频 + 10 音频） |
| 音视频总时长 | 15s | 30s（视频、音频各算各的） |
| 只给音频当参考 | ❌ | ✅ 可以用一段 BGM 直接驱动画面节奏 |
| 局部编辑 | 弱 | 锁死其余画面，只改指定区域 |
| 语言 | 有限 | 原生 10+ 种，口型跟着语种走 |

对写提示词的人来说，真正改变工作方式的是两条：

1. **30 秒意味着你必须写「剧情」而不是「画面」**。15 秒可以只描述一个瞬间，30 秒不给出发展和结尾，模型会自己填，通常填得很烂。
2. **50 个参考位意味着别再用文字描述长相**。能上传的就上传，文字只负责说清楚「这个素材用来干什么」。

## 快速上手

**第一步，用基础公式写一条**（详见 [提示词公式](./docs/02-prompt-formula.md)）：

```
主体 + 动作或事件 + 场景与环境 + 视觉风格 + 运镜或切镜 + 声音
```

后四项都可以省，但省一项模型就自由发挥一项。

**第二步，按时间轴切段**。30 秒至少切三段，写清楚每段发生什么：

```
0-8s   建立：交代主体、环境、基调
8-24s  发展：一个连续动作，别塞三件事
24-30s 收尾：明确最后一帧停在哪
```

**第三步，有参考素材就写清职责**。这是 2.5 最容易写错的地方：

```
@图片1 用于主角的五官、发型和外套款式，不采用图片背景。
@视频1 用于运镜方式和剪辑节奏，不采用视频里的人物和场景。
@音频1 用于背景音乐的节奏和情绪。
```

不写职责映射，模型就自己猜哪张图对应哪个人，多素材时基本必错。

## 文档

| 文档 | 讲什么 |
|---|---|
| [01 能力与硬参数](./docs/01-capabilities.md) | 时长、画幅、素材格式与大小上限，能做什么不能做什么 |
| [02 提示词公式](./docs/02-prompt-formula.md) | 基础公式、时间轴写法、正向描述与负向限制 |
| [03 参考素材怎么配](./docs/03-reference-materials.md) | 50 个位置怎么分、主体几个最稳、素材职责怎么写 |
| [04 视频编辑与延长](./docs/04-video-editing.md) | 局部改写、删除主体、续写、无缝转场 |
| [05 声音与多语言](./docs/05-audio-and-dialogue.md) | 音乐音效台词字幕的特殊符号、口音控制、多语种发行 |
| [06 运镜与光线词表](./docs/06-camera-and-lighting.md) | 能被模型稳定识别的镜头和布光术语 |
| [07 翻车排查](./docs/07-troubleshooting.md) | 人脸漂移、动作演完剩空档、素材串味等常见症状与改法 |

## 提示词库

按场景分类，每条都是自包含的，复制就能用。需要参考素材的会写明需要传什么。

| 分类 | 内容 |
|---|---|
| [影视创作](./prompts/film/) | 无对白叙事、群像戏、动作迁移、改年龄改风格 |
| [广告电商](./prompts/ads-ecommerce/) | TVC、3D 动画广告、SKU 批量换款、出海本地化 |
| [知识科普](./prompts/education/) | 原理可视化、儿童动画、真人口播 |
| [工业制造](./prompts/industrial/) | FPV 穿越、装配流程演示、白模转成片 |
| [创意实验](./prompts/creative/) | 多空间穿梭、拟人化 IP、超现实破屏 |

## 在哪里用

Seedance 2.5 通过豆包 / 即梦（Dreamina）系产品和火山方舟提供，官方口径是体验中心与 API 于 **2026 年 8 月 7 日**全量公开，无免费额度，开通需账户余额满足门槛。具体以火山引擎官方文档为准。

不想折腾开通流程的话，[**imya.ai 的 Seedance 2.5 页面**](https://imya.ai/seedance-2-5) 可以直接用浏览器生成。需要接 API 的看 [Seedance API 文档](https://imya.ai/seedance-2-0)。

## 贡献

欢迎提 PR 投稿提示词，格式见 [CONTRIBUTING.md](./CONTRIBUTING.md)。一条提示词一个文件，附上效果说明和改写建议。

## 说明

本仓库为独立整理，非官方文档。能力参数、格式限制等事实信息整理自火山引擎公开的 Seedance 2.5 对客资料，提示词与写法建议为原创内容。模型迭代较快，参数以官方最新文档为准。

`assets/` 下的配图与效果预览同样整理自火山引擎公开资料，版权归原权利人所有，在此仅作说明用途，详见 [assets/README.md](./assets/README.md)。

## License

内容采用 [CC BY 4.0](./LICENSE) 授权，转载请注明出处。

---

Also by us: [imya.ai](https://imya.ai) — AI image & video generator · [tryonr](https://tryonr.com) — AI virtual try-on
