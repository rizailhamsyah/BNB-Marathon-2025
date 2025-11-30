 # 🌱 AI Agricultural Consultant

![Project Status](https://img.shields.io/badge/Status-Prototype-green)
![Tech Stack](https://img.shields.io/badge/Stack-Next.js%20%7C%20Vertex%20AI%20%7C%20Gemini-blue)
![Focus](https://img.shields.io/badge/Focus-PT%20Pupuk%20Kujang-red)

> **An intelligent agronomy assistant powered by Google Vertex AI to diagnose plant health and recommend precise product solutions.**

## 📖 About The Project

**AI Agricultural Consultant** is a Progressive Web Application (PWA) built to democratize access to agricultural expertise. By harnessing the multimodal capabilities of **Gemini 2.5 Flash**, the app acts as a virtual plant pathologist that is available 24/7.

Beyond just diagnosis, this project features a specialized **Product Recommendation Engine**. It utilizes AI Function Calling to strictly map identified plant issues (like pests or fungi) to the relevant localized solutions from **PT Pupuk Kujang**, bridging the gap between detection and action.

### 🌟 Key Features

* **📸 Visual Disease Diagnosis:** Zero-shot image analysis to detect plant diseases, pests, or nutrient deficiencies via camera upload.
* **🤖 Context-Aware Chatbot:** Acts as a professional agronomist (Senior Plant Pathologist persona) for Q&A.
* **📦 Smart Product Recommendation:** Maps the diagnosis to specific PT Pupuk Kujang products (e.g., *Jeranti*, *Nitrea*, *Bion Up*) using Strict Relevance Checks.
* **🛡️ Safety Guardrails:** Filters out non-agricultural topics and provides safety warnings for chemical usage.
* **🇮🇩 Localized Experience:** Optimized for interaction in Bahasa Indonesia and local dialects.

## 🏗️ Tech Stack

* **Framework:** [Next.js 16](https://nextjs.org/) (App Router)
* **AI Platform:** [Google Cloud Vertex AI](https://cloud.google.com/vertex-ai)
* **Model:** Gemini 2.5 Flash (Multimodal)
* **Styling:** Tailwind CSS + Shadcn UI
* **Deployment:** Google Cloud Run / Vercel
* **Database:** Google Cloud SQL (MySQL)
* **ORM:** Prisma

## ⚙️ Architecture & Workflow

1.  **Input:** User uploads an image of a leaf or asks a text question.
2.  **Processing:** Next.js API Route processes the image to Base64.
3.  **Reasoning (Vertex AI):** * The prompt engine injects the "Agronomist Persona" and "Few-Shot Examples".
    * Gemini 2.5 Flash analyzes the visual/text input.
4.  **Tool Use (Function Calling):**
    * The AI evaluates the `products.ts` catalog.
    * If a product matches the diagnosis, the `recommend_products` tool is triggered.
5.  **Output:** A structured response containing the diagnosis, handling steps, and a rendered Product Card (if applicable).
6.  **Deployment:** The response is rendered in the UI.
7.  **Database:** Google Cloud SQL (MySQL)
