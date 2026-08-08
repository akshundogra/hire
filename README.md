# 🚀 hire.akshundogra.com — Autonomous ABM & GTM Engine Host

[![Status](https://img.shields.io/badge/Status-Live-success?style=for-the-badge&logo=github)](https://hire.akshundogra.com)
[![Phase 1 Engine](https://img.shields.io/badge/Phase_1-n8n_%2B_Flask_%2B_Screaming_Frog-blue?style=for-the-badge)](https://hire.akshundogra.com)
[![Phase 2 Engine](https://img.shields.io/badge/Phase_2-RevPilot_AI_(Chatur)-blueviolet?style=for-the-badge)](https://github.com/akshundogra/Chatur)
[![Tracking](https://img.shields.io/badge/Analytics-GA4_%2B_Telegram-orange?style=for-the-badge)](https://hire.akshundogra.com)

**`hire.akshundogra.com`** is the live deployment domain for **Akshun Dogra's** automated Account-Based Marketing (ABM) and GTM Engineering systems. 

Instead of submitting standard PDF resumes to Applicant Tracking Systems (ATS), this platform automatically crawls target companies, analyzes their marketing/tech stack, audits their SEO/funding signals, and generates bespoke, interactive 90-day execution landing pages with personalized outreach copy.

---

## 🔄 System Evolution: Phase 1 (n8n + Flask) vs. Phase 2 (RevPilot AI)

```mermaid
timeline
    title Evolution of hire.akshundogra.com Infrastructure
    Phase 1 : n8n Webhook Architecture
            : Self-Hosted Docker n8n + Flask Webhook Server
            : Screaming Frog CLI (SEO Crawl & Privacy Policy Tech Stack Scan)
            : DuckDuckGo Funding Lookup Engine
            : Claude Sonnet (Page Generation) & Haiku (Outreach Copy)
            : Python Pillow GIF OG-Image Generator ("HI COMPANY, I HAVE A PROPOSITION")
            : GitHub API Automated Page Commits
    Phase 2 : RevPilot AI (Chatur) Agentic Engine
            : Single-Repo Python 3.11 + FastAPI Architecture
            : Native Technical SEO Auditor (SERP Titles, Meta Descriptions, Alt Text Ratios, OG Cards)
            : Multi-Agent Intelligence Network (Discovery, Qualification, Research, Scoring, Outreach)
            : 33/33/33 Hybrid JD-Resume Skill Matcher
            : Bottom-Up Confidence Scoring & PII Sanitizer
            : Real-Time GA4 UTM Attribution & Instant Telegram Bot Telemetry
```

---

## 🏗️ Architecture & Component Diagrams

### 1. Phase 1: n8n + Flask + Screaming Frog Workflow Architecture

```mermaid
graph TD
    Form[n8n Form Trigger] --> FlaskSEO[Flask: /seo-crawl\nScreaming Frog CLI + Tech Stack Scan]
    Form --> FlaskFunding[Flask: /funding-lookup\nDuckDuckGo Funding Stage Search]
    
    FlaskSEO --> PrepPrompt[Prepare Prompt Node - JS]
    FlaskFunding --> PrepPrompt
    
    PrepPrompt --> ClaudeSonnet[Call Claude Sonnet API\nPage Content Generation]
    ClaudeSonnet --> BuildHTML[Build HTML Node - JS\nPopulates page-template.html]
    BuildHTML --> GHApi[GitHub API Node\nCommits to hire repo]
    
    BuildHTML --> FlaskOG[Flask: /generate-og-image\nPillow GIF Dynamic Meme Overlay]
    FlaskOG --> GHApi
    
    PrepPrompt --> PrepOutreach[Prepare Outreach Node - JS]
    PrepOutreach --> ClaudeHaiku[Call Claude Haiku API\nOutreach Email + LinkedIn Copy]
    ClaudeHaiku --> ParseOutreach[Parse Outreach Node - JS]
    ParseOutreach --> FlaskCSV[Flask: /save-outreach\nAppends to ABM-Outreach-Tracker.csv]
```

---

### 2. Phase 2: RevPilot AI (Chatur) Agentic Architecture

```mermaid
graph TD
    subgraph Signal Intelligence Engine ["🧠 RevPilot AI (Chatur Engine)"]
        JD[Job Alert / Job Description] --> Discovery[Discovery & Qualification Agent]
        Discovery --> Research[Research Agent - DDGS / Glassdoor / Funding]
        Research --> SEOAudit[Native SEO Auditor - app/scrapers/seo_auditor.py]
        SEOAudit --> Intel[Intelligence Agent - PII Scrubbing]
        Intel --> Scoring[Lead Scoring Agent - 100-pt Fit Matrix]
        Scoring --> Matcher[33/33/33 Hybrid JD Matcher]
    end

    subgraph Publisher & Deployment ["🌐 hire.akshundogra.com Repository"]
        Matcher --> Publisher[Publisher Agent - clean_template.html]
        Publisher --> GitCommit[Git Auto-Commit & Push to main]
        GitCommit --> GHPages[GitHub Pages Live Route Deployment]
    end

    subgraph Real-Time Telemetry ["📡 Analytics & Stakeholder Alerts"]
        GHPages --> GA4[Google Analytics 4 UTM Engine]
        GA4 --> Telegram[Telegram Bot Instant Alert]
    end
```

---

### 3. End-to-End Stakeholder Engagement & Telemetry Sequence

```mermaid
sequenceDiagram
    autonumber
    actor Leader as Target Stakeholder (VP Marketing / Director)
    participant Channel as Email / LinkedIn InMail
    participant Host as hire.akshundogra.com
    participant GA4 as Google Analytics 4
    participant Telegram as Telegram Alert Bot

    Leader->>Channel: Receives personalized outreach with tracked URL
    Leader->>Host: Clicks link (hire.akshundogra.com/robco/?utm_content=mona)
    Host->>GA4: Fires PageView event with UTM campaign metadata
    Host-->>Leader: Renders 90-day roadmap, SEO audit findings & fit score
    GA4->>Telegram: Triggers instant Telegram notification to Akshun
```

---

## 🛠️ Stack & Component Reference

### Phase 1: Microservice Engine (`n8n-files`)
* **`n8n` (Docker)**: Workflow orchestration & form webhook processing.
* **`webhook_server.py`**: Flask master server hosting API routes.
* **`seo_crawler_route.py` (`/seo-crawl`)**: Executes Screaming Frog CLI for SEO data (missing alt text, title lengths) and scans privacy policies for tracking tags (`HubSpot`, `Salesforce`, `LinkedIn Ads`, `GA4`).
* **`funding_lookup_route.py` (`/funding-lookup`)**: Queries DuckDuckGo HTML search for funding stage (Seed vs Series A vs Series B+) to calibrate prompt tone.
* **`og_image_route.py` (`/generate-og-image`)**: Uses Python Pillow to dynamically overlay target company names onto custom hero GIFs (`"HI [COMPANY], I HAVE A PROPOSITION"`).
* **`outreach_tracker_route.py` (`/save-outreach`)**: Appends generated email subjects, bodies, and LinkedIn connection notes to local `ABM-Outreach-Tracker.csv`.

### Phase 2: Agentic Engine ([Chatur / RevPilot AI](https://github.com/akshundogra/Chatur))
* **FastAPI Orchestrator**: Async single-repo engine running 8 specialized AI sub-agents.
* **`app/scrapers/seo_auditor.py`**: Native Technical SEO & GTM Stack Auditor:
  * **Title Tag SERP Bounds**: Detects missing titles, titles <30 chars, or SERP truncations (>60 chars).
  * **Meta Description Inspection**: Validates presence and SERP snippet length (70–160 chars).
  * **Heading Hierarchy**: Identifies missing H1s or duplicate H1 tag conflicts.
  * **Image Alt Text Ratios**: Calculates exact ratio of images missing `alt` text.
  * **Open Graph / Social Preview Cards**: Checks for missing `og:image` or `og:title` metadata.
  * **Tech Stack Fingerprinting**: Detects `HubSpot`, `Salesforce`, `GA4`, `PostHog`, `Segment`, `Intercom`, `Drift`.
* **`app/gtm_pipeline/email_finder.py`**: Multi-key Hunter.io API pool with live SMTP email verification.
* **`app/gtm_pipeline/telegram.py`**: Role-title regex sanitizer (`clean_role_title`) & Telegram bot dispatcher.
* **`app/utils/confidence.py`**: Bottom-up evidence, signal, and lead score confidence algorithms.

---

## 📂 Active Live Routes

Below is an index of company landing pages deployed on this host:

| Target Company | Open Role | Route | Infrastructure |
| :--- | :--- | :--- | :--- |
| **RobCo** | Marketing Operations Specialist | [`hire.akshundogra.com/robco/`](https://hire.akshundogra.com/robco/) | 🟢 RevPilot AI (Fit: 100/100) |
| **Alasco** | Revenue Operations & Growth Manager | [`hire.akshundogra.com/alasco/`](https://hire.akshundogra.com/alasco/) | 🟢 RevPilot AI |
| **Eye-Able** | GTM & Growth Lead | [`hire.akshundogra.com/eye-able/`](https://hire.akshundogra.com/eye-able/) | 🟢 RevPilot AI |
| **Celonis** | Enterprise Growth Specialist | [`hire.akshundogra.com/celonis/`](https://hire.akshundogra.com/celonis/) | 🟢 n8n + Flask |
| **Vercel** | Developer Experience Lead | [`hire.akshundogra.com/vercel/`](https://hire.akshundogra.com/vercel/) | 🟢 n8n + Flask |
| **PostHog** | Growth & Analytics Engineer | [`hire.akshundogra.com/posthog/`](https://hire.akshundogra.com/posthog/) | 🟢 n8n + Flask |

---

> [!NOTE]
> All landing pages on `hire.akshundogra.com` are created dynamically as proof-of-work GTM engineering demonstrations for targeted company applications.
