<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0b1220,100:0b3a6e&height=190&section=header&text=Suraj%20Kumar%20Singh&fontSize=46&fontColor=f8fafc&fontAlignY=42&desc=Software%20Engineer%20%C2%B7%20Backend-Focused%20Full%20Stack%20%C2%B7%20Applied%20AI&descAlignY=68&descSize=17&descColor=93c5fd" width="100%" alt="Suraj Kumar Singh banner"/>

<b>Cloud-native microservices on AWS</b> &nbsp;·&nbsp; <b>RAG and semantic caching</b> &nbsp;·&nbsp; <b>On-device AI</b> &nbsp;·&nbsp; <b>ICPC 2026 Global Rank 1025</b>

<br/> <br/>

<a href="https://www.linkedin.com/in/suraj-singh-b0962830a"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
<a href="mailto:surajkumar854000@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
<a href="https://leetcode.com/CodeSurajX"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black" alt="LeetCode"/></a>
<a href="https://ai-code-companion-v1-web-app.vercel.app/"><img src="https://img.shields.io/badge/Live%20Demo-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Live demo"/></a>
<img src="https://img.shields.io/github/followers/Suraj854204?style=for-the-badge&logo=github&label=Followers&color=0891b2&labelColor=0f172a" alt="GitHub followers"/>
<img src="https://hits.sh/github.com/Suraj854204.svg?style=for-the-badge&label=Profile%20Views&color=0891b2&labelColor=0f172a" alt="Profile views"/>

<br/><br/>

<img src="https://img.shields.io/badge/Open%20to-Internships%20%C2%B7%20Backend%20%C2%B7%20Full--Stack-0891b2?style=flat-square&labelColor=0f172a" alt="Open to work"/>
<img src="https://img.shields.io/badge/Location-Lucknow%2C%20India-0b3a6e?style=flat-square&labelColor=0f172a" alt="Location"/>
<img src="https://img.shields.io/badge/B.Tech%20CSE-2027-0891b2?style=flat-square&labelColor=0f172a" alt="B.Tech CSE 2027"/>

</div>

---

## ⚡ At a glance

<div align="center">

| 🏆 **ICPC 2026** | 🧠 **Problems solved** | 📊 **Naukri Young Turks** | ☁️ **Production-style infra** | 🔒 **On-device AI** |
|:---:|:---:|:---:|:---:|:---:|
| Global Rank **1025** | **2,000+** across 4 platforms | **96.83** percentile | **AWS + Terraform** CI/CD | **Qwen3-4B** on Snapdragon NPU |

</div>

---

## 👋 About me

I'm a **software engineer who builds backend-first products** and pairs them with applied AI. I like systems that are reliable under load: clean API contracts, event-driven pipelines, tenant-safe data models, and infrastructure that is reproducible from code.

I've shipped a **5-service microservices job portal**, a **multi-tenant AI support platform on AWS** provisioned entirely with Terraform, and an **on-device AI code reviewer** where no source code ever leaves the machine. Backed by strong DSA and design-pattern fundamentals.

| | |
|---|---|
| 🔭 **Building** | Multi-tenant AI platforms: RAG, semantic caching, agent workflows |
| 🌱 **Learning** | System design, Kubernetes, cloud architecture at scale |
| 🎓 **Education** | B.Tech CSE, Ambalika Institute of Management and Technology (2023 to 2027) |
| 💼 **Experience** | Web Development Intern at Labmentix (Next.js, React, Tailwind) |
| 🎯 **Looking for** | Software Engineering, Backend and Full-Stack **internships** |
| 🤝 **Open to** | Open-source collaboration and hackathon teams |

---

## 🚀 Featured projects

### 1. Support SaaS: multi-tenant AI support platform
> `Mar 2026 – Jul 2026` · Architecture-heavy, cloud-native, production-style

A multi-tenant support platform with organization-isolated knowledge bases, real-time chat and RAG-grounded AI replies. A dedicated **Java 21 / Spring Boot semantic cache** reduces LLM calls and latency.

```mermaid
flowchart LR
    U["Customer / Agent<br/>Next.js + TypeScript"] -->|"REST + WebSocket"| API["Express + TypeScript<br/>JWT / RBAC / multi-tenant"]
    API --> PG[("PostgreSQL<br/>Prisma")]
    API --> K{{"Kafka / MSK"}}
    K --> AI["FastAPI AI service"]
    AI --> SC["Semantic Cache<br/>Java 21 / Spring Boot"]
    SC --> RD[("Redis")]
    AI --> RAG["RAG pipeline<br/>LangChain + LlamaIndex"]
    RAG --> QD[("Qdrant<br/>org-scoped vectors")]
    RAG --> GM["Gemini"]
```

**Semantic cache request path**

```mermaid
flowchart LR
    Q["Query"] --> E["Embed"]
    E --> BF{"Bloom filter<br/>maybe seen?"}
    BF -->|no| LLM["LLM call"]
    BF -->|maybe| LSH["Random-hyperplane<br/>LSH bucket"]
    LSH --> CS{"Cosine similarity<br/>above threshold?"}
    CS -->|hit| H["Return cached answer<br/>O(1) LRU, TTL eviction"]
    CS -->|miss| LLM
    LLM --> S["Store in Redis<br/>+ update metrics"]
```

<details>
<summary><b>📌 Engineering highlights</b></summary>

<br/>

- **Architecture:** API-first, domain-driven microservices with JWT/RBAC and strict **tenant isolation** down to the knowledge-base level.
- **Infrastructure as code:** production AWS stack (**ECS Fargate, RDS, ElastiCache, Elasticsearch/OpenSearch, MSK**) provisioned with **Terraform**, deployed through **GitHub Actions OIDC** (no long-lived cloud keys).
- **CI quality gate:** automated API and AI-service test suites gate every pull request.
- **RAG pipeline:** LangChain and LlamaIndex with embeddings, Qdrant and Gemini for org-scoped retrieval.
- **Semantic cache:** O(1) LRU, Bloom filter, random-hyperplane LSH, cosine similarity, Redis, TTL eviction.
- **Resilience:** cache-aside graceful fallback and tenant-aware validation.
- **Observability:** hits, misses, latency, evictions and **LLM requests avoided**.

</details>

<div align="center">

`Next.js` · `Express` · `FastAPI` · `Java 21` · `Spring Boot` · `AWS` · `Terraform` · `Redis` · `Qdrant` · `Kafka` · `Gemini`

</div>

<br/>

### 2. CoderX: private on-device AI code review
> `2026` · Built for the **Snapdragon® Multiverse Hackathon**

An AI code reviewer that runs **Qwen3-4B entirely on a Snapdragon NPU** via GenieX. **Zero source code ever leaves the machine.**

```mermaid
flowchart LR
    G["Git post-commit hook<br/>or GitHub PR webhook<br/>HMAC-verified"] --> F["FastAPI backend"]
    F --> R{"Risk-aware router<br/>per diff hunk"}
    R -->|trivial| SK["Fast path"]
    R -->|"standard / critical"| C[("SQLite review cache<br/>normalized diff hash")]
    C -->|miss| N["Qwen3-4B on<br/>Snapdragon NPU"]
    N --> W["WebSocket stream"]
    W --> M["React Native / Expo<br/>triage app"]
    M --> H["Human-in-the-loop<br/>reiteration"]
    M --> P["Offline PDF / JSON<br/>audit reports"]
```

- **Risk-aware routing engine** classifies every diff hunk as critical, standard or trivial *before* it reaches the NPU.
- **Incremental review cache** keyed on normalized diff hashes skips redundant re-reviews.
- **Live findings** stream to a mobile triage app with a human-in-the-loop flow and exportable audit reports.

<div align="center">

`Python` · `FastAPI` · `React Native` · `Qwen3-4B` · `Snapdragon NPU` · `GenieX` · `SQLite` · `WebSockets`

</div>

<br/>

### 3. NextHire: AI-powered job portal
> `Aug 2025 – Nov 2025`

A **5-service microservices platform** (Auth, User, Job, Payment, Utils) with four AI career tools.

```mermaid
flowchart LR
    FE["Next.js"] --> GW["Services"]
    subgraph GW["Microservices"]
      A["Auth"] 
      U["User"]
      J["Job"]
      P["Payment"]
      T["Utils"]
    end
    A --> RD[("Redis<br/>token revocation")]
    GW --> K{{"Kafka<br/>async processing"}}
    GW --> PG[("PostgreSQL<br/>NeonDB")]
    T --> GM["Gemini API<br/>Resume Builder, Analyzer,<br/>ATS Checker, Career Guidance"]
```

- JWT authentication with **Redis-backed token revocation**; RBAC across services.
- **Kafka** for asynchronous workflows; Redis caching for hot paths.
- Recruiter subscriptions and payments over REST APIs.

<div align="center">

`Next.js` · `Node.js` · `PostgreSQL` · `Redis` · `Kafka` · `Gemini`

</div>

<br/>

### 4. AI Code Companion: GitHub-integrated developer assistant
> [**▶ Live demo**](https://ai-code-companion-v1-web-app.vercel.app/)

Connect a repository and ship with confidence.

| Capability | What it does |
|---|---|
| 🗂️ **Repository analysis** | Understands structure and codebase layout |
| 🔍 **AI code review** | Automated review feedback |
| 🛡️ **Security scanner** | Surfaces potential vulnerabilities |
| ✅ **Deploy readiness** | Pre-release checks |

<div align="center">

[**📂 Browse all repositories →**](https://github.com/Suraj854204?tab=repositories)

</div>

---

## 🧰 Tech stack

<div align="center">

<img src="https://skillicons.dev/icons?i=java,spring,ts,js,py,cs,react,nextjs,tailwind,nodejs,express,fastapi,dotnet,postgres,mongodb,redis,sqlite,kafka,prisma,elasticsearch,aws,terraform,docker,kubernetes,githubactions,git,github&perline=9" alt="Tech stack icons"/>

</div>

<br/>

| Category | Technologies |
|---|---|
| **Languages** | Java, TypeScript, JavaScript, Python, C#, SQL |
| **Frontend** | React.js, Next.js, React Native, Tailwind CSS, HTML, CSS, responsive and accessible UI |
| **Backend** | Spring Boot, J2EE / Java EE, .NET, Node.js, Express.js, FastAPI, REST APIs, Microservices, API-first design, JWT, Prisma |
| **Databases and search** | PostgreSQL, MongoDB, Redis, SQLite, Qdrant, Elasticsearch / OpenSearch |
| **AI / GenAI** | LangChain, LlamaIndex, RAG, embeddings, Gemini API, Qwen, on-device / edge inference, vector search, AI agents |
| **Cloud and DevOps** | AWS (ECS Fargate, RDS, ElastiCache, MSK), Terraform, Docker, Kubernetes, GitHub Actions, CI/CD, IaC |
| **CS fundamentals** | Data structures, algorithms, design patterns, OOP, graphs, dynamic programming, heaps, hashing |
| **Practices** | Agile / Scrum, code reviews, system design |

---

## 💼 Experience

**Web Development Intern · Labmentix** `Aug 2025 – Nov 2025 · Remote`

- Built and deployed a **responsive, mobile-first landing page** with reusable Next.js / React components and Tailwind CSS ([grinning.vercel.app](https://grinning.vercel.app)).
- Implemented layouts, navigation, product sections and CTA flows; handled component development and cross-device testing independently.
- Took part in Agile sprint ceremonies and peer code reviews.

---

## 🏆 Competitive programming and achievements

<div align="center">

| 🌐 **Contest / Platform** | 🎖️ **Result** |
|:---|:---|
| **ICPC 2026 Online Challenge 1** (powered by Huawei) | Global Rank **1025** |
| **LeetCode** | Contest Global Rank **874** among 27,000+ participants |
| **Codeforces** | Rating **1200** |
| **CodeChef** | DSA Rating **1640** |
| **Naukri Campus Codequezt #31** | Rank **#441** among 14,000+ participants |
| **Pardis Technology Olympics 2026** (Tehran) | Rank **#45** of 1,065 in the Algorithm Track qualifier |
| **Naukri Young Turks 2025** | **96.83 percentile** nationwide |
| **College hackathon** | 🥉 **3rd place**: Image-Provenance Utility using cryptographic signatures |

</div>

**Community and leadership:** organized coding and technical events with **100 to 200+ participants** as an Unstop Campus Ambassador and event lead. Ranked in the top 10% of my institute for coding and leadership.

---

## 📈 GitHub analytics

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Suraj854204&hide_border=true&theme=tokyonight">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Suraj854204&hide_border=true&theme=default" width="98%" alt="profile-details"/>
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Suraj854204&hide_border=true&theme=tokyonight">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Suraj854204&hide_border=true&theme=default" width="49%" alt="repos-per-language"/>
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Suraj854204&hide_border=true&theme=tokyonight">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Suraj854204&hide_border=true&theme=default" width="49%" alt="most-commit-language"/>
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=Suraj854204&hide_border=true&theme=tokyonight">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=Suraj854204&hide_border=true&theme=default" width="49%" alt="stats"/>
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Suraj854204&hide_border=true&theme=tokyonight">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Suraj854204&hide_border=true&theme=default" width="49%" alt="productive-time"/>
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=Suraj854204&theme=tokyonight&hide_border=true&ring=0891b2&fire=06b6d4&currStreakLabel=0891b2&disable_animations=true">
  <img src="https://streak-stats.demolab.com?user=Suraj854204&theme=default&hide_border=true&ring=0891b2&fire=0891b2&currStreakLabel=0891b2&disable_animations=true" width="75%" alt="Contribution streak"/>
</picture>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Suraj854204&bg_color=0d1117&color=0891b2&line=0891b2&point=ffffff&area=true&area_color=0891b2&hide_border=true" width="100%" alt="Contribution graph"/>

</div>

---

## 🤝 Let's connect

I'm actively looking for **Software Engineering, Backend and Full-Stack internships**. If you're building something with distributed systems, applied AI or developer tooling, I'd love to talk.

<div align="center">

<a href="mailto:surajkumar854000@gmail.com"><img src="https://img.shields.io/badge/Email_me-surajkumar854000%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
<a href="https://www.linkedin.com/in/suraj-singh-b0962830a"><img src="https://img.shields.io/badge/Connect_on-LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>

<br/><br/>

<sub>Built with care. Open to feedback, collaboration and good problems.</sub>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0b3a6e,100:0b1220&height=60&section=footer" width="100%" alt=""/>

</div>
