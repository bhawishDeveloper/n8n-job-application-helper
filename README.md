### N8N Job Application Helper

Accelerate your job search with smarter, data‑driven applications.

![n8n](https://img.shields.io/badge/Automation-n8n-orange)
![Status](https://img.shields.io/badge/Project-Portfolio%20Ready-brightgreen)
![Domain](https://img.shields.io/badge/Domain-Data%20Science-blue)

---

### Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Workflow Architecture](#workflow-architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Importing the Workflow into n8n](#importing-the-workflow-into-n8n)
  - [Configuration](#configuration)
- [Usage](#usage)
- [Example Use Case](#example-use-case)
- [Project Structure](#project-structure)
- [Roadmap / Ideas](#roadmap--ideas)
- [License](#license)

---

### Overview

`n8n-job-application-helper` is a low‑code automation workflow built in **n8n** to help you optimize job applications.

It analyzes:

- A **job description**  
- Your **resume**  
- Your **cover letter**

and then:

- Extracts the most important **keywords** from the job description  
- Compares them against your documents  
- Highlights **missing** and **present** keywords  
- Generates **actionable suggestions** you can use to improve your application

This is ideal for **data roles** (Data Scientist, ML Engineer, Analyst, etc.) but can be adapted to any domain.

---

### Features

- 🔍 **Keyword Analysis**  
  Extracts top keywords from a job description (with stopwords removed) using a simple frequency‑based approach.

- 🧠 **Smart Comparison**  
  Compares JD keywords with your resume and cover letter text to find:
  - `missingKeywords`
  - `presentKeywords`
  - `missingFromResume`
  - `missingFromCoverLetter`
  - Overall `matchPercentage`

- ✉️ **Tailored Suggestions**  
  Generates human‑readable suggestions like:  
  _“Consider adding these keywords: Python, A/B testing, experimentation, dashboarding…”_

- 📂 **Google Drive Integration (Text Files)**  
  Reads your resume and cover letter from `.txt` files stored in Google Drive.

- ⚙️ **Fully Built in n8n**  
  No paid APIs or external SaaS dependencies—ideal for portfolio and personal use.

---

### Workflow Architecture

High‑level steps:

1. **Job Description Input**  
   - Paste or fetch the job description into n8n (`Job Description Input` node).

2. **Read Documents from Google Drive**  
   - `Read Resume from Google Drive` → reads `resume.txt`  
   - `Read Cover Letter from Google Drive` → reads `cover_letter.txt`

3. **Extract & Compare Keywords (Code Node)**  
   - Extracts top N keywords from the JD.  
   - Computes:
     - `missingKeywords`
     - `presentKeywords`
     - `missingFromResume`
     - `missingFromCoverLetter`
     - `matchPercentage`
     - `suggestions`

4. **Output Keyword Suggestions**  
   - Maps JSON fields to clean text strings for display or emails.

5. **(Optional) Email Node**  
   - Sends you a formatted email with the suggestions and analysis.

You can include a diagram or screenshot of the n8n workflow here in your repo:

```markdown
![Workflow Overview](./images/n8n-job-search-workflow.png)
