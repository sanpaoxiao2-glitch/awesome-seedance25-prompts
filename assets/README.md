# 素材说明

## 目录

```
assets/
├── refs/      参考素材示例（49 张 WebP，≤ 960px）
└── clips/     效果预览（28 条 3 秒循环 WebP，480px，无声）
```

## 来源

本目录的图片与动图**整理自火山引擎公开发布的 Seedance 2.5 对客资料**，用于说明文档中的写法与效果，版权归原权利人所有。

它们在本仓库中的作用是配图说明，不构成对原素材的授权。如需将这些素材用于其他用途，请自行向火山引擎 / 字节跳动确认权利状态。

不包含官方控制台、体验中心界面的截图与录屏。

## 格式

| 类型 | 规格 | 说明 |
|---|---|---|
| `refs/*.webp` | 最长边 ≤ 960px，quality 78 | 参考素材与成片单帧 |
| `clips/*.webp` | 480px 宽，12fps，3 秒循环，无音轨 | 效果预览，非完整成片 |

完整分辨率的成片不放在仓库里——`clips/` 只是让你在读提示词时能快速看到大概效果。

## 命名

| 前缀 | 含义 |
|---|---|
| `ref-` | 作为参考素材输入的图（产品图、角色图、场景图） |
| `out-` | 生成结果的单帧 |
| `guide-` | 路径 / 分镜引导图（红线示意，成片中不出现） |

`clips/` 下按对应的提示词或能力命名，例如 `motion-transfer.webp` 对应
[动作迁移](../prompts/film/motion-transfer.md)。

## 贡献

投稿素材请遵守 [CONTRIBUTING.md](../CONTRIBUTING.md) 的要求：

- **不要提交 mp4**。视频转成 3 秒 WebP 循环，单个控制在 500KB 以内
- 图片转 WebP，最长边 960px 以内
- 只提交你有权发布的内容

转换命令：

```bash
ffmpeg -t 3 -i input.mp4 -vf "fps=12,scale=480:-2" -c:v libwebp -q:v 62 -loop 0 -an out.webp
```

---

## 素材总览

### 参考图与成片帧 · 49 张

|  |  |  |  |
|---|---|---|---|
| ![guide-canyon-route](refs/guide-canyon-route.webp) | ![guide-shanghai-route](refs/guide-shanghai-route.webp) | ![guide-tokyo-route](refs/guide-tokyo-route.webp) | ![out-3d-house](refs/out-3d-house.webp) |
| `guide-canyon-route` | `guide-shanghai-route` | `guide-tokyo-route` | `out-3d-house` |
| ![out-3d-mansion](refs/out-3d-mansion.webp) | ![out-3d-shop](refs/out-3d-shop.webp) | ![out-3d-yellow-shop](refs/out-3d-yellow-shop.webp) | ![out-aquarium-window](refs/out-aquarium-window.webp) |
| `out-3d-mansion` | `out-3d-shop` | `out-3d-yellow-shop` | `out-aquarium-window` |
| ![out-arabic-woman](refs/out-arabic-woman.webp) | ![out-autumn-road](refs/out-autumn-road.webp) | ![out-brazil-boy](refs/out-brazil-boy.webp) | ![out-butcher](refs/out-butcher.webp) |
| `out-arabic-woman` | `out-autumn-road` | `out-brazil-boy` | `out-butcher` |
| ![out-castle-platform](refs/out-castle-platform.webp) | ![out-china-florist](refs/out-china-florist.webp) | ![out-church-window](refs/out-church-window.webp) | ![out-desert-lizard](refs/out-desert-lizard.webp) |
| `out-castle-platform` | `out-china-florist` | `out-church-window` | `out-desert-lizard` |
| ![out-felt-painter](refs/out-felt-painter.webp) | ![out-fire-breather](refs/out-fire-breather.webp) | ![out-fireworks-street](refs/out-fireworks-street.webp) | ![out-forest-flowers](refs/out-forest-flowers.webp) |
| `out-felt-painter` | `out-fire-breather` | `out-fireworks-street` | `out-forest-flowers` |
| ![out-indonesia-child](refs/out-indonesia-child.webp) | ![out-japan-office](refs/out-japan-office.webp) | ![out-jellyfish](refs/out-jellyfish.webp) | ![out-kitchen-host](refs/out-kitchen-host.webp) |
| `out-indonesia-child` | `out-japan-office` | `out-jellyfish` | `out-kitchen-host` |
| ![out-korea-street](refs/out-korea-street.webp) | ![out-mexico-market](refs/out-mexico-market.webp) | ![out-mother-child](refs/out-mother-child.webp) | ![out-night-market](refs/out-night-market.webp) |
| `out-korea-street` | `out-mexico-market` | `out-mother-child` | `out-night-market` |
| ![out-ribbons](refs/out-ribbons.webp) | ![out-snow-street](refs/out-snow-street.webp) | ![out-thai-market](refs/out-thai-market.webp) | ![out-train-window](refs/out-train-window.webp) |
| `out-ribbons` | `out-snow-street` | `out-thai-market` | `out-train-window` |
| ![out-uk-street](refs/out-uk-street.webp) | ![ref-armor-brown](refs/ref-armor-brown.webp) | ![ref-armor-dark](refs/ref-armor-dark.webp) | ![ref-coffee-machine](refs/ref-coffee-machine.webp) |
| `out-uk-street` | `ref-armor-brown` | `ref-armor-dark` | `ref-coffee-machine` |
| ![ref-coral-reef](refs/ref-coral-reef.webp) | ![ref-door](refs/ref-door.webp) | ![ref-elephant](refs/ref-elephant.webp) | ![ref-empty-room](refs/ref-empty-room.webp) |
| `ref-coral-reef` | `ref-door` | `ref-elephant` | `ref-empty-room` |
| ![ref-fireworks](refs/ref-fireworks.webp) | ![ref-grey-coat](refs/ref-grey-coat.webp) | ![ref-headphones](refs/ref-headphones.webp) | ![ref-illustrated-character](refs/ref-illustrated-character.webp) |
| `ref-fireworks` | `ref-grey-coat` | `ref-headphones` | `ref-illustrated-character` |
| ![ref-male-model](refs/ref-male-model.webp) | ![ref-portrait-woman](refs/ref-portrait-woman.webp) | ![ref-steam-oven](refs/ref-steam-oven.webp) | ![ref-sunflower-field](refs/ref-sunflower-field.webp) |
| `ref-male-model` | `ref-portrait-woman` | `ref-steam-oven` | `ref-sunflower-field` |
| ![ref-trench-coat](refs/ref-trench-coat.webp) |  |  |  |
| `ref-trench-coat` |  |  |  |

### 效果预览 · 28 条

|  |  |  |  |
|---|---|---|---|
| ![3d-animated-ad](clips/3d-animated-ad.webp) | ![age-expression-edit](clips/age-expression-edit.webp) | ![assembly-demo](clips/assembly-demo.webp) | ![band-mv](clips/band-mv.webp) |
| `3d-animated-ad` | `age-expression-edit` | `assembly-demo` | `band-mv` |
| ![catchlight](clips/catchlight.webp) | ![dialogue-audio](clips/dialogue-audio.webp) | ![emotion-layers](clips/emotion-layers.webp) | ![ensemble-scene](clips/ensemble-scene.webp) |
| `catchlight` | `dialogue-audio` | `emotion-layers` | `ensemble-scene` |
| ![fpv-flythrough](clips/fpv-flythrough.webp) | ![furniture-tvc](clips/furniture-tvc.webp) | ![headphone-ad](clips/headphone-ad.webp) | ![kids-animation](clips/kids-animation.webp) |
| `fpv-flythrough` | `furniture-tvc` | `headphone-ad` | `kids-animation` |
| ![motion-transfer](clips/motion-transfer.webp) | ![moving-light](clips/moving-light.webp) | ![multilingual](clips/multilingual.webp) | ![orbit-shot](clips/orbit-shot.webp) |
| `motion-transfer` | `moving-light` | `multilingual` | `orbit-shot` |
| ![perfume-ad](clips/perfume-ad.webp) | ![science-visualization](clips/science-visualization.webp) | ![sprout-extend-1](clips/sprout-extend-1.webp) | ![sprout-extend-2](clips/sprout-extend-2.webp) |
| `perfume-ad` | `science-visualization` | `sprout-extend-1` | `sprout-extend-2` |
| ![street-dance](clips/street-dance.webp) | ![style-swap](clips/style-swap.webp) | ![subject-swap](clips/subject-swap.webp) | ![trailer-en](clips/trailer-en.webp) |
| `street-dance` | `style-swap` | `subject-swap` | `trailer-en` |
| ![trailer-ja](clips/trailer-ja.webp) | ![train-breakout](clips/train-breakout.webp) | ![walk-cycle](clips/walk-cycle.webp) | ![window-4k](clips/window-4k.webp) |
| `trailer-ja` | `train-breakout` | `walk-cycle` | `window-4k` |
