# Awesome Seedance 2.5 Prompts

> Seedance 2.5 (Doubao-Seedance-2.5) is ByteDance's multimodal video generation model.
> This repo documents what it can actually do and how to write prompts that work — no theory, just what gets results.

[中文](./README.md) · [Prompt formula](./docs/02-prompt-formula.md) · [Prompt library](./prompts/) · [Troubleshooting](./docs/07-troubleshooting.md)

---

## What changed from 2.0

In one line: **from generating a shot to generating a scene.**

| | Seedance 2.0 | Seedance 2.5 |
|---|---|---|
| Single-pass duration | 15s | **30s**, no stitching |
| Reference inputs | 9 images + 3 audio/video | **50 total** (30 images + 10 videos + 10 audio) |
| Audio/video total length | 15s | 30s (counted separately for each) |
| Audio-only reference | ❌ | ✅ drive pacing straight from a BGM track |
| Local editing | weak | locks everything else, edits only the target region |
| Languages | limited | 10+ native, lip sync follows the language |

Two things actually change how you work:

1. **30 seconds means you write a story, not a picture.** A single moment fills 15 seconds. It does not fill 30 — and whatever the model invents to fill the gap is usually bad.
2. **50 reference slots mean stop describing appearance in text.** Upload what you can show. Text is only for what each asset is *for*.

## Quick start

**Step 1 — the base formula** ([details](./docs/02-prompt-formula.md)):

```
subject + action or event + setting + visual style + camera + sound
```

The last four are optional. Every one you drop is one the model decides for you.

**Step 2 — break 30 seconds into beats:**

```
0-8s    establish: subject, environment, tone
8-24s   develop: one continuous action, not three
24-30s  resolve: state exactly where the last frame lands
```

**Step 3 — declare what each reference is for.** This is the single most common mistake:

```
@image1 is for the lead's face, hair and jacket. Do not use its background.
@video1 is for camera movement and cutting rhythm only.
        Do not use its characters or location.
@audio1 is for the background music's tempo and mood.
```

Skip the mapping and the model guesses which asset belongs to which subject. With multiple assets it guesses wrong.

## Documentation

| Doc | Covers |
|---|---|
| [01 Capabilities & hard limits](./docs/01-capabilities.md) | Duration, aspect ratio, file formats and size caps, what's locked |
| [02 Prompt formula](./docs/02-prompt-formula.md) | Base formula, timeline structure, positive vs. negative phrasing |
| [03 Reference materials](./docs/03-reference-materials.md) | How to split 50 slots, how many subjects stay stable, asset roles |
| [04 Video editing & extension](./docs/04-video-editing.md) | Local rewrites, object removal, continuation, seamless transitions |
| [05 Audio & multilingual](./docs/05-audio-and-dialogue.md) | Sound symbols, accent control, multi-language releases |
| [06 Camera & lighting](./docs/06-camera-and-lighting.md) | Terms the model reliably understands |
| [07 Troubleshooting](./docs/07-troubleshooting.md) | Face drift, dead air, asset bleed — symptoms and fixes |

## Prompt library

Every prompt is self-contained. Copy, paste, run. Ones needing references say exactly what to upload.

| Category | Contents |
|---|---|
| [Film](./prompts/film/) | Silent narrative, ensemble scenes, motion transfer, age & style edits |
| [Ads & e-commerce](./prompts/ads-ecommerce/) | TVC, 3D animated ads, SKU batch swaps, localization |
| [Education](./prompts/education/) | Science visualization, kids' animation, multilingual guides |
| [Industrial](./prompts/industrial/) | FPV flythroughs, assembly demos, whitebox-to-final renders |
| [Creative](./prompts/creative/) | Room-to-room one-shots, anthropomorphic IP, audio-driven cuts |

Prompts are written in Chinese, which the model handles natively — as it does English, Spanish, Indonesian, Malay, Thai, Arabic, Portuguese, Vietnamese, Japanese and Korean. Translate freely; the structure carries over.

## Where to run it

Seedance 2.5 ships through ByteDance's Doubao / Dreamina products and Volcano Engine Ark. Official word is the playground and API open fully on **August 7, 2026**, with no free tier and an account balance threshold to activate. Check Volcano Engine's docs for current terms.

To skip the signup, [**imya.ai's Seedance 2.5 page**](https://imya.ai/seedance-2-5) runs it in the browser. For API integration see the [Seedance API docs](https://imya.ai/seedance-2-0).

## Contributing

PRs welcome. Format is in [CONTRIBUTING.md](./CONTRIBUTING.md) — one prompt per file, with an explanation of what makes it work and how to adapt it.

## Disclaimer

Independent project, not official documentation. Capability specs and format limits are compiled from Volcano Engine's public Seedance 2.5 materials; the prose, structure and prompts are original. The model moves fast — treat the official docs as authoritative on parameters.

## License

[CC BY 4.0](./LICENSE) — reuse freely with attribution.

---

Also by us: [imya.ai](https://imya.ai) — AI image & video generator · [tryonr](https://tryonr.com) — AI virtual try-on
