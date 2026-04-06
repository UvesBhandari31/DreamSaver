# 🚀 DreamSaver

DreamSaver is an AI-powered dream journaling application designed for self-reflection and mental wellness. It allows users to securely log their dreams and uses Google Gemini AI to provide personalized interpretations—uncovering symbolic meanings, identifying emotional themes, and finding connections to waking life stressors. Built with a calming, dark-mode focused aesthetic, DreamSaver helps users track patterns in their subconscious safely and beautifully.DreamSaver is an  modern web application built with React, Vite, TypeScript, Tailwind CSS, Shadcn UI, and Supabase.

---

## ✨ Features

- ⚛️ Frontend: React 18 + Vite  
- 🎨 Styling: Tailwind CSS + Shadcn UI  
- 🗄️ Backend: Supabase (Database + Auth)  
- 💳 Payments: Stripe integration  
- 🤖 AI: Google Gemini API  

---

## 📦 Prerequisites

Make sure you have installed:

- Node.js (latest LTS recommended)  
- npm / yarn / pnpm / bun  

---

## ⚡ Getting Started

### 1. Clone & Install

```bash
git clone <your-repository-url>
cd DreamSaver
npm install
```

### 2. Configure Environment Variables 🔐

Create a `.env.local` file in the root directory.

👉 Add your required API keys and secrets for:

- Google Gemini API  
- Supabase (URL + keys)  
- Stripe (secret + publishable keys)  
- JWT & encryption keys  
- App URL  

### 3. Run the App

```bash
npm run dev

App will start on:

http://localhost:8080


