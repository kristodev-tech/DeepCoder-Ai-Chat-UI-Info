# 📦 Requirements for DeepCode AI Chat UI

This repository provides a developer-friendly AI chat UI with editing, formatting, and export features designed for seamless integration with Ollama-hosted models.

---

## 🐍 Python Requirements

- **Python 3.10+** (tested with Python 3.12)
- Required packages:
- pip install -r requirements.txt

```
from flask import Flask, request, render_template, redirect, url_for, session, flash, jsonify, send_file
import json
import os
import requests
from datetime import datetime, timedelta
import re
import time
from flask import render_template_string
from transformers import GPT2TokenizerFast
from flask import make_response
from io import BytesIO
from reportlab.lib.pagesizes import letter
from reportlab.lib.utils import simpleSplit
import uuid
from io import BytesIO
from reportlab.pdfgen import canvas
# Load once globally
from transformers import GPT2TokenizerFast
```

---

## 💻 Minimum Hardware Requirements

For running the backend + Ollama models effectively:

- **CPU**: 8-core (16 thread CPU or better)
- **RAM**: 32 GB DDR4 minimum
- **Disk**: Gen 4 fast SSD with at least 500 GB free (for models + exports)
- **GPU** (16-24GB VRAM recommended for speed and larger models):
  - NVIDIA GTX/RTX with CUDA/Tensor Flow support (optional but ideal or your Ai will be really slow)
  - AMD not supported by Ollama at this time

---

## 🧠 Ollama Model Compatibility

✅ Tested and optimized for:

- `deepseek-coder-v2:latest` (Q4_0 quantization)
- Any **Q4_0** quantized model that supports:
  - Prompt history
  - Code-generation formatting
  - System-style prompts

⚠️ If you wish to use **non-Q4_0 models**, **or models with different prompt/response templates**, you must:

- Modify the `get_ollama_response()` function and any other part of the code needed to support the new prompt and model style
- Adjust prompt formatting, streaming, and completion handling logic
_Thorughly review the code before you make any modifications and make sure you have backup copies
---

## 🔒 Compatibility Scope

This UI is designed to support **local Ollama model hosting**, and can be served over cloud flare domain for public access and is only limited by the:

- Hardware running your server  
- Capabilities and token limits of your selected model

---

Then visit: [http://localhost:5000](http://localhost:5000)

---

## 📌 Notes

- This app assumes Ollama is running locally at `http://localhost:11434`
- You can configure multi-user access and session limits inside `app.py`
- Requires internet access only for model download (Ollama), not runtime
