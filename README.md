<!-- Profile README – Pedro A. A. Silva -->

<h1 align="center">Pedro A. A. Silva</h1>
<p align="center">
  <b>Data Engineer&nbsp;&bull;&nbsp;Python, SQL, PySpark, Databricks, dbt&nbsp;&bull;&nbsp;PhD in Computational Modeling</b><br>
  Juiz de Fora, MG&nbsp;&mdash;&nbsp;Brazil&nbsp;&bull;&nbsp;Remote, U.S./EU time-zone overlap&nbsp;&bull;&nbsp;<b>Open to work</b>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/pedro-andre-arroyo-silva/">LinkedIn</a> •
  <a href="https://pedrororo.github.io/remote-jobs-index/">Jobs Index (live)</a> •
  <a href="https://github.com/pedrororo/jobs-index-showcase">Case study</a> •
  <a href="https://www.kaggle.com/peterroro">Kaggle</a>
</p>

---

## About me

I build data pipelines that run every day without anyone watching them:
collect messy data from many sources, clean and enrich it, keep its history,
check its quality, and publish something people can use. I spent two years
running production ELT on Databricks, Delta Lake and AWS for multiple clients.
Before data engineering I did a PhD and a postdoc in computational modeling,
simulating heart tissue with large numerical models.

---

## Featured project: Jobs Index

**Live → [pedrororo.github.io/remote-jobs-index](https://pedrororo.github.io/remote-jobs-index/)** · rebuilt every day ·
**Case study → [jobs-index-showcase](https://github.com/pedrororo/jobs-index-showcase)**: architecture, design trade-offs, what failed and how I fixed it, and a runnable sample on fake data

A job-market data platform I designed and run on my own. It collects public
job postings (tech and non-tech; remote, hybrid and on-site; Europe, US, LATAM
and Brazil), tracks each posting over time, and publishes a free, searchable
site.

- **Scale:** about **690,000 open jobs** per daily run from **16,000+
  companies** in 100+ countries: about **9,800 company career boards on 25+ ATS
  platforms** (Workday, Greenhouse, Ashby, Lever, SmartRecruiters, Teamtailor
  and others), job boards, and Brazilian portals such as Gupy.
- **Lakehouse:** bronze Parquet, then a dbt project that builds silver and gold
  from the same models on DuckDB *or* Databricks (Unity Catalog, Auto Loader,
  Asset Bundles), with data tests.
- **Lifecycle history:** an SCD Type 2 `MERGE` gives first seen, updates and
  closed dates for every posting, so new, closed and reposted jobs are
  reliable from day to day. Kaplan-Meier estimates how long postings stay open.
- **Quality gates:** each run is compared with the previous ones (failed
  sources, volume drops, gaps). A broken run never replaces the live site.
- **Memory stays flat as volume grows:** streaming and batching cut the
  pipeline's peak from 5.05 GB to 2.81 GB (−44%) and the alert job's from
  8.2 GB to 2.4 GB.
- **$0 infrastructure:** when the daily run outgrew the free CI quota (about
  4,300 of 2,000 monthly minutes), I moved it to a self-hosted ARM runner on
  Oracle Cloud Free Tier, validated with tests and a dry run before cut-over.
- **Orchestration:** GitHub Actions for the pipeline; the downstream daily
  alert also ships as an Airflow 3 DAG (sensor, retries, two quality-gate
  tasks, Docker Compose).
- **Discovery:** tools that probe career pages for embedded ATS boards and add
  only verified ones, in screened batches: about 5,000 boards added in two
  weeks, including VC-backed startups (Y Combinator, Getro and Consider boards).
- **Tested:** 400+ automated tests on every push.

Python · SQL · dbt · DuckDB · Databricks · Delta Lake · Parquet · Airflow · GitHub Actions · Oracle Cloud

### LLM tooling on the same data

**Repo → [job-market-lab](https://github.com/pedrororo/job-market-lab)**: MCP server, agent harness, evals and the salary pilot, runnable on the public site data

- **MCP server** that exposes the job data to LLM agents through 5 tools, plus a
  small harness that runs the same agent on local (Ollama) and hosted models.
- **LLM fallback for salary extraction** where regex rules fail: 45/48 correct
  on a labeled sample of hard postings, vs 16/48 for the rules.
- **Application assistant** (local Python API + Chrome extension) that scores a
  posting against a profile, lists missing skills, flags old or reposted
  postings from the history data, and drafts answers with the Claude API or a
  local model.

- **Agent evals:** 12 questions with independently computed answers; a local 7B model
  (`qwen2.5:7b`, CPU) went from 9/12 to 11/12 on the same snapshot while I iterated on
  the tool descriptions ([results](https://github.com/pedrororo/job-market-lab/tree/master/evals/agent)).

---

## Also public

| Project | What it is |
|---|---|
| **[Per-client Dashboard Portal](https://github.com/pedrororo/portal-dashboards)** | A portal where each client sees only the dashboards an admin grants them. Isolation between clients is enforced by the database itself, not only by the code. Signed Metabase embeds with the client filter locked in the token, login rate limiting, 19 automated tests and an HTTP access matrix; Docker Compose, CI on every push. |

I also practice the unglamorous part: deliberately breaking my own projects
(failing CI, access-control bugs, bad files from a source) and writing up what
happened and how I fixed it.

<!-- Removed 2026-11-14 (restore with git if wanted):
     - "Building now" rows for Agro Data Platform (design docs only, no code yet),
       Job Market Lab, Business Automation Lab, Recupera Orçamentos, MarketFit CV
       (private or prototypes; re-add when they are public and runnable).
-->

---

## Tech stack

**Data:** Python · PySpark · SQL · Pandas · dbt · DuckDB · Databricks · Delta Lake · PostgreSQL · Parquet<br>
**Orchestration & ops:** Airflow · Databricks Workflows · GitHub Actions (self-hosted runners) · Docker · Linux/systemd · Terraform (basic)<br>
**Cloud:** AWS (S3, Lambda, IAM, boto3) · Oracle Cloud (OCI)<br>
**LLM & ML:** Claude API · Ollama · MCP · LLM evals · PyTorch · Hugging Face · YOLOv11 · BLIP

---

## Experience

<table>
  <tr>
    <td><b>Artemis Smart Data</b><br><i>Data Engineer</i><br><sub>Aug 2024 – Sep 2026</sub></td>
    <td>
      • Designed and maintained 20+ scheduled production ELT pipelines (PySpark, Databricks, Delta Lake, AWS S3) at about 99.5% SLA across client environments<br>
      • Cut pipeline failures by an estimated 50% with schema, completeness, deduplication and reconciliation checks<br>
      • Modeled financial and operational data in Bronze/Silver/Gold layers; configuration-driven pipelines for new clients and sources
    </td>
  </tr>
  <tr>
    <td><b>FrameNet Brasil</b><br><i>Multimodal ML Engineer</i><br><sub>2023 – 2024</sub></td>
    <td>
      • Curated 30,000+ English–Portuguese image-caption pairs<br>
      • Fine-tuned YOLOv11 and adapted BLIP with PyTorch and Hugging Face
    </td>
  </tr>
  <tr>
    <td><b>Vox Radar</b><br><i>Data Analyst</i><br><sub>2021 – 2022</sub></td>
    <td>
      • Automated social-media data collection and reporting with Python and Selenium, saving an estimated 500+ hours a year
    </td>
  </tr>
  <tr>
    <td><b>UFJF / PGMC</b><br><i>Postdoctoral Researcher</i><br><sub>2019 – 2021</sub></td>
    <td>
      • Computational models of cardiac electrophysiology in Python and C++; published in <i>Phil. Trans. R. Soc. A</i>
    </td>
  </tr>
</table>

<!-- Removed 2026-11-14 because they are not on the CV (an interviewer will ask):
     "Built a secure Node/TS API and React dashboard used by 40 analysts",
     "Cut AWS compute spend by 35% with a serverless redesign",
     "Published checkpoints on Hugging Face with a Gradio demo" (the HF account shows nothing public).
     Re-add any that are true, and add them to the CV too. -->

---

## Education

- **Ph.D. Computational Modeling**, UFJF (2018). Thesis on
  discretization-dependent models of electrical propagation in excitable media,
  published in *Physical Review E* and *IEEE Transactions on Biomedical
  Engineering*.
- **M.Sc. Mathematics**, UFJF (2013) · **B.Sc. Mathematics**, UFES (2011)

---

## Languages

Portuguese (native) · Spanish (native) · English (C1)

---

## Contact

**Email:** arroyo.andre@gmail.com · **LinkedIn:** [pedro-andre-arroyo-silva](https://www.linkedin.com/in/pedro-andre-arroyo-silva/)

Open to remote Data Engineer roles (including contractor). Happy to talk about
data pipelines, lakehouses or the job market.
