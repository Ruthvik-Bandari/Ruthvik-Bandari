<!-- ============================================================ -->
<!-- HERO  (animated, theme-aware — see assets/hero-*.svg)         -->
<!-- ============================================================ -->

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/hero-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/hero-light.svg">
  <img alt="Ruthvik Bandari · Applied AI · Computer Vision · RAG · Agentic AI" src="./assets/hero-dark.svg" width="100%">
</picture>

<br/>
<br/>

<a href="https://www.linkedin.com/in/ruthvik-nath-bandari-908b00247/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
<a href="https://ruthvik-bandari-portfolio.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio"/></a>
<a href="mailto:bandari.ru@northeastern.edu"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
<a href="https://x.com/itz_ruthvik"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"/></a>
<img src="https://komarev.com/ghpvc/?username=Ruthvik-Bandari&style=for-the-badge&color=22D3EE&label=PROFILE+VIEWS" alt="profile views"/>

</div>

---

## Now

&bull; **Research Assistant**, Center for the Future of Higher Education and Work (CHEW), Northeastern: full-stack redesign and data-ingestion automation for a higher-education compliance web application<br/>
&bull; **Research Assistant** for Dr. Rominder Singh, Northeastern: building **RA Copilot**, a Canvas-embeddable RAG tutor for Regulatory Affairs; earlier built the Global Drug Regulatory RAG dataset pipeline<br/>
&bull; Shipping **DiaFoot.AI v2** and co-authoring a diabetic-foot-ulcer segmentation manuscript (in progress) with a Harvard collaborator, targeting SPIE Medical Imaging<br/>
&bull; Exploring agentic AI systems, retrieval-augmented generation and graph learning<br/>
&bull; Open to AI / ML **internship, co-op, and full-time** opportunities

---

## Featured Projects

### DiaFoot.AI &middot; Diabetic Foot Ulcer Intelligence &nbsp;<sub>(solo)</sub>
A cascaded, multi-task computer-vision pipeline for diabetic foot images: a DINOv2 ViT-B/14 triage classifier (LoRA fine-tuned) &rarr; UPerNet wound segmenter &rarr; wound-area measurement in mm&sup2;, with image-quality gates and a defer-to-clinician path. Reaches **98.4% triage accuracy**, **0.999 macro-AUROC** and **DFU-only Dice 0.891** on leakage-audited splits, with an ONNX export validated at **99.99% mask parity** and **4.5x faster** inference. Trained on NVIDIA **B200** (MGHPCC) and **H200** (Northeastern Explorer) via SLURM.

`PyTorch` `DINOv2` `UPerNet` `LoRA` `ONNX` `FastAPI` `SLURM` &nbsp;&middot;&nbsp; [Repository](https://github.com/Ruthvik-Bandari/DiaFoot.AI)

### RA Copilot &middot; RAG Tutor for Regulatory Affairs &nbsp;<sub>(research, with Om Patel)</sub>
A Canvas-embeddable text-and-voice RAG tutor running a five-stage **route &rarr; retrieve &rarr; generate &rarr; ground &rarr; frame** pipeline over a 611-chunk course knowledge base and an 11-module / 70-topic curriculum map. Hybrid retrieval (pgvector dense + BM25) with optional cross-encoder reranking and LettuceDetect / MiniCheck groundedness checks; a ports-and-adapters backend with a config-only GPU-to-CPU serving switch (vLLM + Qwen3). **201 passing backend tests** plus Playwright end-to-end coverage.

`FastAPI` `pgvector` `BM25` `vLLM` `Qwen3` `React` `LTI 1.3`

### Global Drug Regulatory RAG Dataset Pipeline &nbsp;<sub>(research)</sub>
A healthcare regulatory-intelligence pipeline spanning **199 countries and 200 authorities**. A five-stage clean &rarr; normalize &rarr; enrich &rarr; validate &rarr; export flow with a classifier and SimHash dedup gate produces **59,284 semantic chunks** across 9,321 validated documents (195/200 ISO codes reachable), backed by **539+ tests**.

`Python` `BeautifulSoup4` `httpx` `SimHash` `langdetect`

### Research Aggregation Pipeline &middot; IEEE TechRxiv &nbsp;<sub>(team)</sub>
A multi-source academic aggregator (arXiv, BioRxiv, PubMed, Google News) rebuilt in clean OOP with retrying abstract scrapers and TF-IDF + K-means clustering with automatic K selection. The rewrite hit a **73.8x speedup** (571.7s &rarr; 7.8s) and 3.3x finer clustering versus the manual baseline. Published on IEEE TechRxiv.

`Python` `scikit-learn` `NLTK` `BeautifulSoup4` &nbsp;&middot;&nbsp; [Repository](https://github.com/Ruthvik-Bandari/Research_aggeregation_pipeline) &nbsp;&middot;&nbsp; [Paper](https://doi.org/10.36227/techrxiv.177040642.26830215/v1)

### CTPPO &middot; Cyber Threat Prioritization with PPO
GraphSAGE + DistilBERT + Dueling DQN over **276,049 CVEs** to learn and rank cyber-threat remediation paths.

`Python` `PyTorch` `PyTorch Geometric` `Transformers` `Stable-Baselines3`

---

## Tech Stack

**Languages**
<p>
  <img src="https://skillicons.dev/icons?i=python,ts,js,bash,html,css" alt="languages"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white" />
</p>

**AI / ML / Deep Learning**
<p>
  <img src="https://skillicons.dev/icons?i=pytorch,tensorflow,sklearn,opencv" alt="ml"/>
  <img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat&logo=huggingface&logoColor=black" />
  <img src="https://img.shields.io/badge/DINOv2-5A2AA0?style=flat&logo=meta&logoColor=white" />
  <img src="https://img.shields.io/badge/ONNX-005CED?style=flat&logo=onnx&logoColor=white" />
  <img src="https://img.shields.io/badge/MONAI-0E7C7B?style=flat&logoColor=white" />
</p>

**LLMs / RAG / Agents**
<p>
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white" />
  <img src="https://img.shields.io/badge/vLLM-1668DC?style=flat&logoColor=white" />
  <img src="https://img.shields.io/badge/pgvector-4169E1?style=flat&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/Anthropic-D4A27F?style=flat&logo=anthropic&logoColor=white" />
</p>

**Data & MLOps**
<p>
  <img src="https://skillicons.dev/icons?i=postgres,redis,sqlite" alt="data"/>
  <img src="https://img.shields.io/badge/Polars-CD792C?style=flat&logo=polars&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/DuckDB-FFF000?style=flat&logo=duckdb&logoColor=black" />
  <img src="https://img.shields.io/badge/MLflow-0194E2?style=flat&logo=mlflow&logoColor=white" />
  <img src="https://img.shields.io/badge/W%26B-FFBE00?style=flat&logo=weightsandbiases&logoColor=black" />
  <img src="https://img.shields.io/badge/DVC-13ADC7?style=flat&logo=dvc&logoColor=white" />
</p>

**Backend & Frontend**
<p>
  <img src="https://skillicons.dev/icons?i=fastapi,flask,nodejs,react,nextjs,tailwind,vite" alt="web"/>
</p>

**DevOps / HPC / Tools**
<p>
  <img src="https://skillicons.dev/icons?i=docker,git,githubactions,linux,vscode,bun" alt="tools"/>
  <img src="https://img.shields.io/badge/SLURM-00A98F?style=flat&logoColor=white" />
  <img src="https://img.shields.io/badge/CUDA-76B900?style=flat&logo=nvidia&logoColor=white" />
</p>

---

## Publications

| Title | Venue | Year | Link |
|---|---|---|---|
| Automating Research Intelligence: AI-Generated vs Manually Designed Pipelines | IEEE TechRxiv | 2026 | [DOI](https://doi.org/10.36227/techrxiv.177040642.26830215/v1) |
| NeuroFace Recognition System | IOSR Journal of Computer Engineering, Vol. 27 Issue 2 | 2025 | [Journal](https://www.iosrjournals.org/) |

---

## Achievements

| Achievement | Year |
|---|---|
| Best AI Innovation Award &middot; Lahey CARE-AI-THON | 2026 |
| Runner-Up &middot; BASE 44 Hackathon | 2026 |
| Finalist &middot; Subconscious AI &times; ACM Hackathon | 2025 |
| ACM Student Chapter Lead | 2022&ndash;2025 |
| Class Representative (4 years) | 2021&ndash;2025 |

---

## GitHub Stats

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Ruthvik-Bandari&show_icons=true&hide_border=true&include_all_commits=true&count_private=true&theme=tokyonight&title_color=22D3EE&icon_color=22D3EE" alt="stats"/>
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ruthvik-Bandari&layout=compact&hide_border=true&theme=tokyonight&title_color=22D3EE&langs_count=8" alt="top languages"/>

<br/>

<img src="https://streak-stats.demolab.com?user=Ruthvik-Bandari&theme=tokyonight&hide_border=true&ring=22D3EE&fire=22D3EE&currStreakLabel=22D3EE" alt="streak"/>

<br/>
<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Ruthvik-Bandari/Ruthvik-Bandari/output/github-snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Ruthvik-Bandari/Ruthvik-Bandari/output/github-snake.svg">
  <img alt="contribution snake" src="https://raw.githubusercontent.com/Ruthvik-Bandari/Ruthvik-Bandari/output/github-snake.svg">
</picture>

</div>

---

<div align="center">

### Let's build something that matters

<a href="mailto:bandari.ru@northeastern.edu"><img src="https://img.shields.io/badge/Reach%20out-22D3EE?style=for-the-badge&logo=minutemailer&logoColor=white" alt="reach out"/></a>

</div>
