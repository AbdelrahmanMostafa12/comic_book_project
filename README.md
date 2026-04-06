# 🎨 Comic Book Project

<p align="center">
  <strong>AI-powered comic story generation with consistent characters, comic-style panels, dialogue captions, and evaluation tools.</strong>
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.10%2B-blue">
  <img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-2.x-red">
  <img alt="Transformers" src="https://img.shields.io/badge/Transformers-HuggingFace-yellow">
  <img alt="Diffusers" src="https://img.shields.io/badge/Diffusers-SDXL-green">
  <img alt="Status" src="https://img.shields.io/badge/Project-Experimental-purple">
</p>

---

## 📚 Overview

This project is an end-to-end **AI comic generation pipeline** built in Jupyter Notebook.  
It transforms a simple story idea into a short comic experience by combining:

- **LLM-based story generation**
- **structured scene extraction**
- **character-consistent image generation**
- **comic-style prompt engineering**
- **automatic dialogue caption rendering**
- **basic image-text evaluation**

The workflow is designed around a storytelling pipeline:

> **Prompt → Story Scenes → Image Prompts → Reference Characters → Comic Panels → Captions → Evaluation**

---

## ✨ What This Project Does

This notebook generates a short comic story in multiple stages:

1. **Generates a structured 10-scene story** using **Qwen2.5-7B-Instruct**
2. **Parses each scene** into:
   - shot type
   - location
   - action
   - visual detail
   - dialogue
3. **Builds reference prompts** for the main characters
4. **Generates comic-style panels** using **Stable Diffusion XL / RealVisXL**
5. **Uses a custom attention mechanism** to improve character consistency across scenes
6. **Adds dialogue captions** directly onto the generated images
7. **Evaluates text-image quality** using:
   - **CLIP similarity**
   - **GPT-2 perplexity**

---

## 🧠 Core Idea

Generating one beautiful image is easy.

Generating a **sequence of comic panels** where:
- the **same characters stay visually consistent**,
- the **story changes across locations and actions**,
- the **dialogue stays readable**,
- and the output feels like a comic rather than random text-to-image generations...

...is a much harder problem.

This project explores exactly that.

---

## 🚀 Features

- ✅ Structured **10-scene story generation**
- ✅ Locked character descriptions for consistency
- ✅ Reference image generation for both main characters
- ✅ StoryDiffusion-style consistency logic via custom spatial attention
- ✅ Comic-style visual prompting
- ✅ Automatic caption box rendering
- ✅ Scene-by-scene output saving
- ✅ Lightweight evaluation with CLIP and GPT-2
- ✅ Notebook-friendly workflow for experimentation

---

## 🏗️ Pipeline Architecture

```text
User Prompt / Character Sheet
            │
            ▼
Qwen2.5-7B-Instruct
(Generate 10 structured story scenes)
            │
            ▼
Scene Parsing
(Shot / Location / Action / Detail / Dialogue)
            │
            ▼
Prompt Builder
(Comic style + character locks + negative prompts)
            │
            ▼
Reference Character Generation
(Visual identity anchors)
            │
            ▼
SDXL / RealVisXL Panel Generation
(Custom consistency attention)
            │
            ▼
Caption Rendering
(Dialogue boxes added to panels)
            │
            ▼
Evaluation
(CLIP similarity + GPT-2 perplexity)
            │
            ▼
Final Comic Outputs
