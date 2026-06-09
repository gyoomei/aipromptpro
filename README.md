# 🎬 AI Prompt Generator Pro

### Image & Video to Professional AI Prompts — Free · No API Key · Single HTML

Generate production-ready prompts for Midjourney, DALL-E, Stable Diffusion, Kling, Runway, and Pika from any image or video. Deep visual analysis with AI-powered prompt engineering.

[![Live Demo](https://img.shields.io/badge/Live-Demo-6366f1?style=for-the-badge&logo=github)](https://gyoomei.github.io/aipromptpro/)
[![Try Now](https://img.shields.io/badge/Try-Now-06b6d4?style=for-the-badge&logo=googlechrome)](https://gyoomei.github.io/aipromptpro/)
[![AI](https://img.shields.io/badge/AI-Pollinations.ai-8b5cf6?style=for-the-badge)](https://pollinations.ai)
[![Features](https://img.shields.io/badge/Features-2%20Modes-f0c040?style=for-the-badge)](#core-features)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 📖 The Problem

AI image/video generators produce inconsistent results. Every prompt is a guess — you waste hours tweaking words hoping the model understands your vision. Worse, video generation platforms (Kling, Runway, Pika) cap at 8 seconds and lose consistency between clips.

**AI Prompt Generator Pro** solves this by analyzing the ACTUAL visual content of your reference image or video — extracting colors, composition, lighting, mood, texture, and style — then generating precise, copy-ready prompts optimized for each AI platform.

## ✨ How it works

**Image Mode:**
```
You upload:    A moody street photo at golden hour
AI analyzes:   Colors, brightness, edges, composition, mood
You get:       "A lone figure walking through rain-soaked cobblestone streets
                at golden hour, warm amber sidelight casting long shadows,
                shallow depth of field with bokeh reflections, cinematic
                film grain, muted desaturated color grading..."
```

**Video Mode:**
```
You upload:    A 30-second nature montage
AI analyzes:   4 segments × 3 keyframes each
You get:       Segment 1: "Wide aerial establishing shot of misty mountain
                            valley at dawn, drone descending slowly..."
               Segment 2: "Close-up of dew-covered wildflowers swaying in
                            gentle breeze, macro lens, soft focus..."
               Segment 3-4: Continuity-preserving cinematic prompts
```

**That's the entire UX** — upload, analyze, copy, generate.

## 🎯 Core Features

| Capability | Detail |
|---|---|
| **Image to Prompt** | Upload any image → 10-axis visual analysis → optimized AI prompt |
| **Video to Prompt** | Upload video → auto-segmented into 8s shots → per-segment cinematic prompts |
| **Keyframe Extraction** | 3 keyframes per segment (start, mid, end) for comprehensive analysis |
| **Segment Continuity** | AI maintains cinematic flow between video segments |
| **Aspect Ratio** | 8 options: 1:1, 16:9, 9:16, 4:3, 3:4, 21:9, 3:2, 2:3 |
| **Color Palette** | Extracted dominant colors with hex codes and percentages |
| **JSON + Text Output** | Structured JSON for developers, copy-ready text for creators |
| **Copy & Download** | One-click copy or download as .txt / .json |
| **10-Axis Analysis** | Subject, elements, environment, lighting, camera, DOF, texture, mood, color, style |
| **Dark/Light Theme** | Toggle between premium dark and clean light modes |

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────┐
│                    Browser (Client-Side)              │
│                                                      │
│  Upload → Canvas Analysis → Visual Data Extraction   │
│           ↓                                          │
│  Pollinations.ai (free LLM) → Prompt Generation      │
│           ↓                                          │
│  Render: English Prompt + JSON + Color Palette        │
│           ↓                                          │
│  Copy / Download .txt / .json                        │
└──────────────────────────────────────────────────────┘
```

## 💡 Architecture Decisions

**Why single HTML?** Zero deployment friction. No build step, no npm, no server. Works offline after first load. GitHub Pages serves it for free.

**Why client-side analysis?** The Canvas API extracts real visual data (colors, brightness, edges, composition) directly from pixels. This gives the AI model concrete data to work with instead of guessing from text descriptions.

**Why Pollinations.ai?** Free, no API key, OpenAI-compatible endpoint. The `/openai` path returns proper JSON with `choices[0].message.content`. Rate limit ~1 req/10s is fine for single-file analysis.

**Why 8-second segments?** All major AI video platforms (Kling, Runway, Pika, Sora) generate clips in 5-10 second ranges. 8 seconds is the sweet spot for cinematic continuity.

## 🧪 Try these examples

| Upload | Expected Output |
|---|---|
| Portrait photo | Shallow DOF, subject-focused prompt, warm/cool lighting analysis |
| Cityscape at night | Neon lighting, high edge density, urban environment, dramatic mood |
| Nature landscape | Wide angle, natural lighting, organic textures, serene atmosphere |
| Product photography | Clean background, studio lighting, sharp focus, commercial style |
| 30s video montage | 4 segment prompts with evolving camera movement and consistent style |

## 🛠️ Stack

- **Frontend:** Vanilla JavaScript, single HTML file (~62KB)
- **AI:** [Pollinations.ai](https://pollinations.ai) — free, no API key
- **Analysis:** Canvas 2D pixel analysis (colors, brightness, edges, composition)
- **Video:** HTML5 Video API + keyframe extraction via canvas
- **Fonts:** [Sora](https://fonts.google.com/specimen/Sora) + [Nunito](https://fonts.google.com/specimen/Nunito) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
- **Hosting:** GitHub Pages (zero infra cost)

## 🚀 Quick Start

```bash
git clone https://github.com/gyoomei/aipromptpro.git
cd aipromptpro
open index.html    # or python3 -m http.server 8080
```

## 📄 License

MIT — Use freely for personal and commercial projects.

**Built with ✦ AI Prompt Generator Pro · Powered by [Pollinations.ai](https://pollinations.ai)**
