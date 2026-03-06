# Building with Gemini 3 Flash — GDG UCSD Workshop 2026

A hands-on workshop for UCSD developers on building with Google's Gemini 3 Flash model via the Vertex AI API. By the end of this workshop, you'll know **when to make AI think harder — and when not to.**

---

## What's Covered

**01 — How Hard Should AI Think?**
Introduction to the `thinking_level` parameter. Learn the trade-off between speed (MINIMAL) and deep reasoning (HIGH) through a Big-O lens.

**02 — Giving the AI "Eyes"**
Introduction to multimodal inputs and the `media_resolution` parameter. Control how many tokens the model spends processing images and video.

**03 — See the Thinking**
Hands-on challenge using Thought Summaries (`include_thoughts=True`) to visualize the difference between MINIMAL and HIGH reasoning in real time.

---

## Prerequisites

- A Google account
- A Google Cloud Project ([create one here](https://console.cloud.google.com/))
- Vertex AI API enabled on your project ([enable it here](https://console.cloud.google.com/flows/enableapi?apiid=aiplatform.googleapis.com))
- Billing account attached to your project (required for Vertex AI — **you will not be charged** for this workshop)

---

## Getting Started

1. Open the notebook in Google Colab: **[intro_gemini_3_flash.ipynb](./intro_gemini_3_flash.ipynb)**
2. Click **File → Save a copy in Drive** — work from your own copy
3. Run cells 1–3 to install the SDK, import libraries, and authenticate
4. Paste your Google Cloud Project ID into cell 4
5. You're ready to go

---

## Notebook Structure

| Section | Cells | Description |
|---|---|---|
| Setup | 1–5 | Install SDK, authenticate, configure project and model |
| Quickstart | 6 | Your first `generate_content` call |
| Thinking Level | 7–9 | MINIMAL vs LOW vs MEDIUM vs HIGH — latency/reasoning trade-off |
| Media Resolution | 10–12 | Control token usage for images and video |
| Thought Signatures | 13–16 | Preserving reasoning state across multi-turn function calls |
| Streaming Function Calling | 17 | Stream partial function call arguments |
| Multimodal Function Responses | 18 | Return images and files from tool calls |
| Supported Features | 19–35 | System instructions, parameters, streaming, chat, safety, async, multimodality, structured output, search, code execution, URL context, function calling, token counting |

---

## Key Concepts

### `thinking_level`
Controls how much the model deliberates before responding.

| Level | Use When | Trade-off |
|---|---|---|
| `MINIMAL` | Simple Q&A, translations, summaries | Fastest, cheapest — minimal self-checking |
| `LOW` | Straightforward tasks with light reasoning | Slightly slower, slightly more thorough |
| `MEDIUM` | Moderate complexity | Balanced latency and reasoning depth |
| `HIGH` | Complex code, math, multi-step logic | Slowest, most thorough — model self-corrects |
| *(default)* | Unspecified | Dynamically adjusts based on prompt complexity |

### `media_resolution`
Controls how many tokens the model spends processing visual inputs.

| Level | Use When |
|---|---|
| `LOW` | General scene understanding, fast processing |
| `MEDIUM` | Balanced detail and cost |
| `HIGH` | Fine detail, small text, labels |
| `ULTRA_HIGH` | Maximum detail — per-part only, not global |

---

## Resources

- [Gemini 3 Flash on Vertex AI](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/models/gemini/3-flash)
- [Google Gen AI SDK for Python](https://pypi.org/project/google-genai/)
- [Vertex AI Generative AI docs](https://cloud.google.com/vertex-ai/generative-ai/docs)
- [GDG UCSD](https://gdg.community.dev/gdg-on-campus-university-of-california-san-diego-la-jolla-usa/)

---

## About GDG UCSD

Google Developer Group UCSD is UCSD's official Google Developer Group. We run technical workshops, tech talks, and build projects together — aligned with Google developer standards across Firebase, TensorFlow, Gemini, and more.
