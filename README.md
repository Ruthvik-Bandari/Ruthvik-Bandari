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

<a href="https://www.linkedin.com/in/ruthvik-nath-bandari/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
<a href="https://ruthvik-bandari-portfolio.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio"/></a>
<a href="mailto:ruthvik299@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
<a href="https://x.com/itz_ruthvik"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white" alt="X"/></a>
<img src="https://komarev.com/ghpvc/?username=Ruthvik-Bandari&style=for-the-badge&color=22D3EE&label=PROFILE+VIEWS" alt="profile views"/>

</div>

---

MS Applied AI at Northeastern (4.0 GPA, graduating May 2027). I work on medical imaging, retrieval systems, and security tooling, and most of what I build ends up being an argument about measurement: audit the split before you trust the benchmark, publish the negative result, put the isolation in the database instead of the application layer.

Currently on co-op at Beth Israel Lahey Health building lung cancer screening tooling. First author on a medical imaging paper under review at SPIE, co-first author on a published TechRxiv preprint.

**Open to new-grad AI/ML roles starting May 2027.** F-1 visa, STEM-designated degree (36 months of OPT, three H-1B lottery attempts).

---

## Now

&bull; **Student Intern, Innovation Hub** — Lahey Clinic, Beth Israel Lahey Health. Screening-eligibility and outreach prototype for low-dose CT lung cancer screening, working on synthetic clinical data<br/>
&bull; **Research Assistant**, Center for the Future of Higher Education and Work (CHEW), Northeastern: full-stack redesign and data-ingestion automation for a higher-education compliance web application<br/>
&bull; **Research Assistant** for Dr. Rominder Singh, Northeastern: building **RA Copilot**, a Canvas-embeddable RAG tutor for Regulatory Affairs; earlier built the Global Drug Regulatory RAG dataset pipeline<br/>
&bull; Shipping **DiaFoot.AI v2** and first-authoring a diabetic-foot-ulcer segmentation manuscript with a Harvard Medical School collaborator, under review at SPIE Medical Imaging 2027

---

## Featured Projects

### DiaFoot.AI &middot; Diabetic Foot Ulcer Segmentation &nbsp;<sub>(first author)</sub>

Does adding more wound data improve diabetic foot ulcer segmentation? It makes it worse, and the study holds architecture, hyperparameters, and epoch budget fixed to show it. **Five training compositions across three architectures under five-fold cross-validation — 75 trained models** on one leakage-controlled test set.

The ordering `DFU+Healthy > DFU-only > All > DFU+Non-DFU > Random-mixed` came out identical for a convolutional encoder-decoder (U-Net++), a hierarchical transformer (SegFormer-B0), and a frozen self-supervised backbone (DINOv2), so the effect belongs to the data and not to any one inductive bias. The `All` composition trained on 5,497 images against DFU-only's 1,427, a 3.8× increase, and scored **lower on every architecture**. Adding non-DFU wounds pushed false positives on healthy skin to **44.8%** (SegFormer); in-domain healthy negatives held them **below 1%**.

The curation is part of the contribution: a perceptual-hash audit found **96,829 near-duplicate train–test image pairs** in the naive split, and the rebuilt splits bring that to **zero** across path-overlap, content-hash, and near-duplicate checks. Paired bootstrap on per-image DFU Dice reached p < 0.05 in **44 of 45** fold-level comparisons.

Also in the repo: a cascaded triage → segmentation → wound-area pipeline (DINOv2 ViT-B/14 with LoRA, UPerNet decoder, ONNX export), trained on NVIDIA B200 (MGHPCC) and H200 (Northeastern Explorer) under SLURM. Cascade metrics are documented but their result artifacts are not committed, so the composition study is the part with full provenance.

`PyTorch` `DINOv2` `U-Net++` `SegFormer` `LoRA` `ONNX` `DVC` `SLURM` &nbsp;&middot;&nbsp; [Repository](https://github.com/Ruthvik-Bandari/DiaFoot.AI)

### CTPPO &middot; Cyber Threat Propagation Path Optimizer &nbsp;<sub>(solo)</sub>

Scanners rank CVEs by severity. CTPPO asks which attack *path* an attacker can actually walk, and which single fix shrinks that exposure most. It runs **NAMOA\***, an exact multi-objective label-setting search, and returns the complete Pareto front over time-to-exploit, success probability, and business impact.

Across 300 seeded networks the Pareto-recommended fix recovers **84.1% of oracle reachability reduction (95% CI [80.0, 87.9])** against **24.0% ([19.5, 28.8])** for ranking by CVSS severity. Edge costs are grounded in a committed snapshot of **340,247 FIRST EPSS scores** and **1,621 CISA KEV CVEs**, with CVSS v3.1 sub-scores implemented from the specification. Validated end to end against live exploitation: a real `nmap -sV` scan of an Apache httpd 2.4.49 testbed surfaced CVE-2021-41773, a working path-traversal proof of concept confirmed it, and the predicted path matched ground truth at recall 1.00.

The GNN exploitability refiner ships **default-off**, because it changed the recommended fix in 0 of 60 real-CVE networks.

`Python` `NAMOA*` `PyTorch Geometric` `FastAPI` `React 19` &nbsp;&middot;&nbsp; [Repository](https://github.com/Ruthvik-Bandari/CTPPO-Cyber_Threat_Propagation_Path_Optimizer)

### RA Copilot &middot; RAG Tutor for Regulatory Affairs &nbsp;<sub>(research)</sub>

A Canvas-embeddable text-and-voice tutor running a five-stage **route → retrieve → generate → ground → frame** pipeline over a course knowledge base and a module-and-topic curriculum map. Hybrid retrieval (pgvector dense + BM25) with cross-encoder reranking and LettuceDetect / MiniCheck groundedness checks. Ports-and-adapters backend with a config-only GPU-to-CPU serving switch (vLLM + Qwen3), plus Playwright end-to-end coverage.

`FastAPI` `pgvector` `BM25` `vLLM` `Qwen3` `React` `LTI 1.3`

### Global Drug Regulatory RAG Dataset Pipeline &nbsp;<sub>(research)</sub>

A healthcare regulatory-intelligence pipeline covering **199 countries and 200 regulatory authorities**, of which 195 are reachable. Five stages — clean → normalize → enrich → validate → export — with a human-medicines classifier and a SimHash dedup gate, plus a gap-filler that recovers unreachable authorities from WHO country profiles, ICH adoption records, and Wayback Machine snapshots. **1,350 test functions** across 34 test modules.

`Python` `Crawl4AI` `httpx` `BeautifulSoup4` `SimHash` `langdetect`

### Research Intelligence Pipeline &middot; IEEE TechRxiv &nbsp;<sub>(co-first author)</sub>

A 17-author study comparing AI-agent-generated research pipelines against manually designed ones. I am **listed first among 16 equal-contribution co-first authors**, and my contribution is **Pipeline 2's clustering stage and LinkedIn collection**: 5,028 items retrieved across arXiv, bioRxiv, PubMed, news, and LinkedIn, converging on **18 clusters** (largest 623 items, 15.5%) with cluster count chosen by silhouette scoring across 2–20 configurations, core analysis in 343 seconds.

The finding: no AI framework produced a working pipeline without substantial human intervention. The Claude-generated platform wrote 3,800+ lines across 31 files in eight minutes, then needed **35 hours of expert debugging** to reach basic functionality, against roughly 60 hours to build the pipeline manually from scratch.

`Python` `scikit-learn` `NLTK` `BeautifulSoup4` &nbsp;&middot;&nbsp; [Paper](https://doi.org/10.36227/techrxiv.177040642.26830215/v1)

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

| Title | Venue | Status | Link |
|---|---|---|---|
| Beyond Bigger Datasets: How Training Data Composition Influences Diabetic Foot Ulcer Segmentation | SPIE Medical Imaging 2027 | Under review (first author) | — |
| Automating Research Intelligence: Advanced-AI-Generated vs Manually Designed Pipelines | IEEE TechRxiv | Preprint, 2026 (co-first author) | [DOI](https://doi.org/10.36227/techrxiv.177040642.26830215/v1) |

---

## Achievements

| Achievement | Year |
|---|---|
| AI Innovation Award &middot; [Lahey Clinic Care-AI-thon](https://cps.northeastern.edu/news/when-45-minutes-was-all-they-needed-cps-students-win-lahey-clinic-care-ai-thon-2/) &mdash; only student team in the competition | 2026 |
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

<a href="mailto:ruthvik299@gmail.com"><img src="https://img.shields.io/badge/Reach%20out-22D3EE?style=for-the-badge&logo=minutemailer&logoColor=white" alt="reach out"/></a>

</div>
