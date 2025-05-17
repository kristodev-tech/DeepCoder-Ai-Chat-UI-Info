# Deep-Coder-Ai-Chat-UI
Custom  Ai Web chat UI built on java, Python, flask, Ollama, Cloudflare, Deepseek coder v2/Open Chat/ Text to image generator/deepseek v2/Codellama by Meta for Personal, developer or commercial use.
# 🚀 DeepCoder AI Chat UI

A Developer-Focused, Fully Featured AI Chat Assistant Powered by Ollama
Demo it here: https://deepcoderai.deepcoderai.org/

---

## 📄 Description

DeepCoder AI Chat UI offers a feature-rich, customizable chat experience for developers, creators, and tech enthusiasts.  
Built using Flask and Ollama, it integrates powerful models like DeepSeek Coder V2, DeepSeek V2, Open Chat, Text to image generator and Codellama Meta — providing a modern alternative to ChatGPT with enhanced functionality and is also mobile friendly.

---

## ✨ Key Features

- 💬 Interactive AI chat assistant for coding, math, science, and technical questions
- 🧠 Streaming, animated assistant responses with smooth auto-scroll
- 📝 Inline editing and resending of user prompts
- 📦 Download assistant responses as **PDF, Markdown, or Plain Text**
- 📄 Download code blocks with proper file extensions and custom filenames
- 🗃️ Up to **10 concurrent project sessions** with rename, organize, delete options
- 🔀 Switch between **DeepSeek Coder V2**, **DeepSeek V2**, and **Codellama Meta** anytime
- 🔐 Secure login system with Admin/Guest roles
- 🌙 Dark mode support and beautiful animated UI enhancements
- 🧮 Token and character usage counters to monitor response sizes
- 🚀 Lightweight, built on Flask + Ollama for fast setup and portability
- 🔁 Smart model tracking — session auto-remembers which model was used
  🔁 Tracks user logins globally to prevent duplicate logins by checking active users
- 🚮 Clear individual sessions or wipe all history easily
- 🎯 Download your chat sessions for record-keeping or documentation
- ✨ Copy code cleanly — without annoying triple backticks or language noise

---

## 📊 Model Information

- **Primary:** DeepSeek Coder V2 16B (Q4_0 Quantized)
- **Additional:** DeepSeek V2 14B, Codellama Meta 13B and Open Chat
- These models are specifically optimized for technical, scientific, coding, and project-based tasks.
- Token range: Configured for **up to 3000 tokens per response** for excellent detail without cutting off.

---

## 🆚 Why Choose This Over ChatGPT?

| Feature | DeepCode AI Chat UI | ChatGPT |
|:--------|:-------------------:|:-------:|
| Inline Edit + Resend | ✅ | ❌ |
| Download responses (PDF/TXT/MD) | ✅ | ❌ |
| Download code files correctly | ✅ | ❌ |
| Custom session naming & exporting | ✅ | ❌ |
| Token counter shown | ✅ | ❌ |
| Dark Mode | ✅ | ✅ |

---

## 🧠 Additional Advantages

- **Full Local Ownership:** Host it yourself — no external servers needed.
- **Private Models:** Run DeepSeek Coder or other Ollama models securely on your own hardware.
- **Multi-Session Power:** Manage up to 10 independent project sessions with full model-switching support.
- **Auto Model Persistence:** When you load an old session, the model selection automatically matches.
- **Future Proof:** Structured for easy scaling as bigger models like DeepSeek-32B are released.

---

## ⚙️ How to Install and Run

1. Clone the repository:

```

2. Install Python dependencies:

from flask import Flask, request, render_template, redirect, url_for, session, flash, jsonify, send_file
import json
import os
import requests
from datetime import datetime, timedelta
import re
import time
from flask import render_template_string
from flask import make_response
from reportlab.lib.pagesizes import letter
from reportlab.lib.utils import simpleSplit
import uuid
from io import BytesIO
from reportlab.pdfgen import canvas
# Load once globally
from transformers import GPT2TokenizerFast
```
pip install -r requirements.txt

3. Ensure **Ollama** is installed and running locally (GPU or CPU supported).  
👉 [Install Ollama](https://ollama.com) download the models and correct model sizes we are already using in this version

4. Launch the app:

```bash
python app.py
```

5. Open in your browser:

```
http://localhost:5000
```

---

## 🛠️ Important Setup Notes

- **Usernames and passwords are currently hardcoded** in `app.py` (demo default).  
  ➡️ Purchasers will need to update the authentication system for production.
- **Chat history is saved as local JSON files**.  
  ➡️ For commercial deployments, upgrading to a database like **SQLite**, **PostgreSQL**, or **MongoDB** is highly recommended.
- **Default model** after clearing history or starting new chat: **DeepSeek Coder V2**.

---

## ☁️ Tunnel Access Requirement

To access the Flask application remotely (outside `localhost`), this project requires a reverse tunnel tool like:

- 🔐 **Cloudflared (Cloudflare Tunnel)** – *recommended*
- 🌐 **Ngrok** – alternative option

These tools securely expose your `http://localhost:5000` app to the public internet without needing to open firewall ports or configure DNS.

### Why It's Needed

- Your app runs on a local Flask server
- To share the chat UI with other users or devices, a **secure HTTPS tunnel** is required
- These tools also **protect you from unauthorized access**

---

## 🔧 Backend (Flask - Python)

Handles:

- Authentication and user sessions
- Chat session storage in per-user JSON files
- LLM prompt formatting and dispatch
- Code block extraction + token/char counting via HuggingFace tokenizer
- Secure response regeneration when editing messages
- Session timeouts + logout handling

---

## 🎨 Frontend (HTML, JS, CSS)

Provides:

- Live, responsive chat interface
- Editable message history with re-generation
- Code block highlighting, copying, and download
- Export buttons (PDF, MD, TXT)
- Dark mode toggle
- Session selector with rename/delete features
- Custom animations for text/code responses

---

## ✅ Customization Ready

You can easily:

- Plug in **Ollama**, **OpenAI**, or **LM Studio**
- Replace the logo or modify color schemes
- Integrate Stripe or license key validation
- Add SSO, email login, or external auth

---

## 📦 Project Structure

```
project/
├── app.py                     # Backend logic and routes
├── templates/chat.html        # UI frontend with Jinja2
├── static/                    # Logo, JS, CSS
├── <username>_chat_history.json #Chat histories for logged in users are automatically created in your project folder. You dont need to manually add anything here
├── requirements.txt
└── README.md
```

---

## 🧠 Ideal For

- Developers building custom LLM tools  
- Educators and coders using local AI models  
- Companies seeking a private, branded assistant  
- Agencies reselling AI chat apps  


## 🔒 Security Features

- Session-based user login system (Admin / Guest)
- Global session tracking for active users login/logout/browser close (Admin / Guest)
- Auto logout after 15 minutes inactivity
- Forced logout after 90 minutes continuous use
- Anti-caching safeguards to ensure secure session flow
- Flash messages for important user actions

---

## 📧 Contact Us

For feedback, questions, or licensing purchase options and inquiries:  
✉️ [msepro.software@gmail.com](mailto:msepro.software@gmail.com)

---

## 📜 License

> **Custom License Terms:**  
> Buyers are allowed to use, modify, and deploy this UI privately or commercially based on licensing terms.  
> ❌ Redistribution of the source code, resale without permission, or public sharing is prohibited.

Contact us for commercial licensing options and view our Buy_License HTML for licensing tiers and pricing.

---

# 🚀 Ready to revolutionize your private AI development experience?  
**Deploy DeepCoder AI Chat UI today and stay ahead of the future!**
