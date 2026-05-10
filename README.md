# 🐾 PetOlife — Unified Pet Identity Platform

> **Code-A-Thon Submission** · Full Stack Engineer Internship  
> Built by **Jannath Barveen R**

---

## 🌐 Live Site

**[→ View Live Site](https://your-live-url-here.com)**  
*(Deploy via GitHub Pages — instructions below)*

---

## 📋 Project Overview

PetOlife's launch homepage introduces the **Unified Pet Identity Protocol** — a digital infrastructure concept that gives every pet a single, portable, trusted identity connecting pet parents, veterinarians, and care providers.

### What's Built

| File | Description |
|------|-------------|
| `index.html` | Main launch homepage — hero, how-it-works, identity showcase, ecosystem |
| `generator.html` | AI-powered Pet ID Generator (Claude Sonnet API) |
| `README.md` | This file |

---

## ✨ Key Features

### 🏠 Launch Homepage (`index.html`)
- Animated floating Pet ID card mockup in the hero
- Live stats ticker (problem-space data)
- 4-step "How It Works" grid with scroll-reveal
- Dark-theme living identity profile with health bars & timeline
- Stakeholder ecosystem cards (Pet Parents / Vets / Care Partners)
- Custom cursor, paw particle field, scroll-linked nav
- Zero dependencies — pure HTML/CSS/JS, instant load

### 🤖 AI Pet ID Generator (`generator.html`)
- **Photo upload** → Claude AI analyzes breed, markings, personality via vision
- **Text form input** → name, species, breed, age, health notes
- **Both combined** → richest AI-generated profile
- Outputs a fully rendered digital identity card with:
  - Scientific species name, blood type, microchip ID
  - Vet clinic, last visit, allergies, personality descriptor
  - Unique Pet ID (PID) generated per pet
- Personalized **AI Health Insight** paragraph per pet
- 3D hover effect on identity card
- Powered by **Claude Sonnet 4** (Anthropic API)

---

## 🛠 Local Setup

### Prerequisites
- A modern browser (Chrome, Firefox, Safari, Edge)
- No build step required — pure HTML/CSS/JS

### Run Locally

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/petolife-launch.git
cd petolife-launch

# Option 1: Open directly
open index.html

# Option 2: Serve with Python (recommended — avoids CORS on fetch)
python3 -m http.server 8080
# Then open http://localhost:8080
```

### For the AI Generator

The generator calls the **Anthropic Claude API** directly from the browser. Claude.ai provides the API key automatically when running inside the Claude artifact environment.

To run independently, you would need to proxy the API through a backend (to protect your API key). A simple Node.js proxy:

```js
// server.js (Node + Express)
const express = require('express');
const app = express();
app.use(express.json({ limit: '10mb' }));

app.post('/api/claude', async (req, res) => {
  const response = await fetch('https://api.anthropic.com/v1/messages', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
      'x-api-key': process.env.ANTHROPIC_API_KEY,
      'anthropic-version': '2023-06-01'
    },
    body: JSON.stringify(req.body)
  });
  const data = await response.json();
  res.json(data);
});

app.listen(3001);
```

---

## 🚀 Deploy to GitHub Pages

```bash
# Push to GitHub
git add .
git commit -m "PetOlife launch submission"
git push origin main

# In GitHub repo → Settings → Pages
# Source: Deploy from branch → main → / (root)
# Your site: https://YOUR_USERNAME.github.io/petolife-launch
```

---

## 🤖 AI Tools Used

| Tool | Usage |
|------|-------|
| **Claude (Anthropic)** | Full code generation, UI architecture, copy writing |
| **Claude Sonnet 4 API** | Powers the live Pet ID Generator (vision + text) |
| **Claude.ai Artifacts** | Iterative prototyping environment |

**Automation approach:**  
Prompted Claude with the full brief → received complete HTML/CSS/JS → iterated with targeted follow-up prompts for the AI generator feature and mobile responsiveness. The AI generator itself uses Claude's vision capability to analyze pet photos — so Claude was used *both* to build the product and *within* the product.

---

## 🏗 Architecture Decisions

### Why Pure HTML/CSS/JS (no framework)?
- Zero build step — judges can open and run instantly
- Demonstrates CSS mastery (custom cursor, scroll-reveal, animations without libraries)
- Faster load = better UX demo

### Why Claude API for the AI feature?
- Vision + text in one model = simplest possible architecture
- Structured JSON output via system prompt → easy to parse and render
- No vector DB, no backend, no auth complexity for a demo

### Design Choices
- **Warm earth palette** (caramel, bark, cream) = trust, nature, warmth — antidote to cold healthtech blue
- **Playfair Display** serif = editorial authority, not "yet another SaaS"
- **Floating ID card** = shows the product concept before any copy is read

---

## 📁 File Structure

```
petolife-launch/
├── index.html        # Main launch homepage
├── generator.html    # AI Pet ID Generator
└── README.md         # This file
```

---

## 👩‍💻 Author

**Jannath Barveen R**  
Full Stack Engineer Internship Applicant  
PetOlife Code-A-Thon · May 2026

---

*Built with love for pets 🐾*
