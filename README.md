<!-- Profile README – Pedro A. A. Silva -->

<h1 align="center">Pedro A. A. Silva</h1>
<p align="center">
  <b>Data Engineer&nbsp;&bull;&nbsp;PhD in Computational Engineering</b><br>
  Juiz de Fora, MG&nbsp;&mdash;&nbsp;Brazil
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/pedro-andre-arroyo-silva/">LinkedIn</a> •
  <a href="https://pedrororo.github.io/remote-jobs-index/">Jobs Index</a> •
  <a href="https://www.kaggle.com/peterroro">Kaggle</a> •
  <a href="https://huggingface.co/pedrororo">Hugging Face</a>
</p>

---

## About me

I build data pipelines that run every day without anyone watching them:
collect messy data from many sources, clean and enrich it, keep its history,
and publish something people can use. Before data engineering I did a PhD in
computational engineering, simulating excitable media (heart tissue models).

---

## Featured project: Jobs Index

**Live → [pedrororo.github.io/remote-jobs-index](https://pedrororo.github.io/remote-jobs-index/)** · updated every day

A job-market data pipeline I designed and run on my own. It collects public
job postings (tech and non-tech; remote, hybrid and on-site; Europe, US, LATAM
and Brazil), tracks each posting over time, and publishes a free, searchable
site.

- **Scale:** about **268,000 open jobs** in the latest run, from about **3,300
  company career boards** (Greenhouse, Ashby, Lever, Workable, Recruitee,
  Workday), job boards, and Brazilian portals such as Gupy.
- **Runs itself:** a GitHub Actions workflow fetches, enriches, checks data
  quality and publishes the site daily at 06:17 UTC. A collapsed run never
  replaces the live site.
- **Fits in a small runner:** I rewrote the fetch step to stream jobs to disk
  and enrich them in batches. Peak memory went from 5.05 GB to 2.81 GB while
  the number of jobs grew from 171k to 232k.
- **Lifecycle history:** immutable snapshots keyed by identity and content
  hashes give first seen, last seen and closed dates for every posting.
- **Lakehouse:** bronze Parquet, then a dbt project that builds silver and gold
  on DuckDB *or* Databricks (Unity Catalog, Auto Loader, SCD Type 2 with
  `MERGE`, Asset Bundles), with data tests. Kaplan-Meier estimates how long
  postings stay open.
- **Discovery:** tools that probe career pages for embedded ATS boards and add
  only verified ones. I added over 1,700 VC-backed startups this way (Y
  Combinator, Getro and Consider boards), because startups hire entry-level
  people.
- **Static site with SEO:** search, filters, an insights tab, landing pages, a
  sitemap and a blog, with no backend.
- **Tested:** 150+ offline unit tests run in CI on every push.

Python · SQL · dbt · DuckDB · Databricks · Delta Lake · Parquet · GitHub Actions · JavaScript

---

## Building now

Projects in progress. Linked ones are public; the others stay private while they mature.

| Project | What it is | Where it stands |
|---|---|---|
| **[Agro Data Platform](https://github.com/pedrororo/agro-data-platform)** | A data platform for Brazilian agro prices (Cepea) and economic indicators (Central Bank API), built in 7 phases: ingestion → dbt modeling → data quality → serving → streaming → lakehouse at scale → cloud with Terraform and LGPD governance. | Phase 1 designed: Airflow 3, MinIO and Parquet, idempotent loads, backfills within API limits, and a quarantine for files that break the contract. Design doc and ADRs written before code. |
| **[Per-client Dashboard Portal](https://github.com/pedrororo/portal-dashboards)** | A portal where each client sees only the dashboards an admin grants them. Isolation between clients is enforced by the database itself, not only by the code. | Working: signed Metabase embeds with the client filter locked in the token, login rate limiting, forced password change, 19 automated tests and an HTTP access matrix. Runs with Docker Compose; CI tests every push and publishes the image. |
| **Job Market Lab** | Analysis on top of the Jobs Index data: who is hiring, where postings appear, and how fast they close (Kaplan-Meier). | Answers job-seeker questions per topic and region from the latest daily run. |
| **Business Automation Lab** | Small tools for small Brazilian businesses: a quote comparator, an accounting-documents tracker and a budget tracker. | Streamlit app, used to test whether small businesses would pay for simple automation. |
| **Recupera Orçamentos** | Reads WhatsApp sales conversations to find quotes nobody followed up on, and suggests the next message. | MVP with transparent rules and no AI API; the conversation text is not stored. |
| **MarketFit CV** | Compares a CV with recent job postings to suggest adjacent titles and missing skills. | Front-end prototype for validation; no processing yet. |

I also practice the unglamorous part: deliberately breaking my own projects (failing CI, access-control bugs, bad files from a source) and writing up what happened and how I fixed it.

---

## Tech stack

**Data:** Python · PySpark · SQL · dbt · DuckDB · Databricks · Delta Lake · PostgreSQL · Parquet<br>
**Cloud & ops:** AWS (S3, Lambda, IAM) · Docker · Terraform · GitHub Actions<br>
**Apps:** Node/TypeScript · React · JavaScript<br>
**ML:** PyTorch · YOLOv8 · BLIP · Hugging Face<br>
**BI:** Power BI · Tableau

---

## Experience

<table>
  <tr>
    <td><b>Artemis Smart Data</b><br><i>Data Engineer (Full-Stack)</i><br><sub>2024–present</sub></td>
    <td>
      • Automated 20+ Databricks pipelines per day and cut failures by 50%<br>
      • Built a secure Node/TS API and React dashboard used by 40 analysts<br>
      • Cut AWS compute spend by 35% with a serverless redesign
    </td>
  </tr>
  <tr>
    <td><b>FrameNet Brasil / UFJF</b><br><i>ML Researcher</i><br><sub>2023–2024</sub></td>
    <td>
      • Fine-tuned YOLOv8 and BLIP on English/Portuguese FrameNet data<br>
      • Published checkpoints on Hugging Face with a Gradio demo
    </td>
  </tr>
  <tr>
    <td><b>Vox Radar</b><br><i>Data Scientist</i><br><sub>2021–2022</sub></td>
    <td>
      • Automated 70% of social-data reporting with Selenium bots
    </td>
  </tr>
</table>

---

## Education

- **Ph.D. Computational Engineering**, UFJF (2018). Thesis on
  discretization-dependent models for excitable media, published in *Physical
  Review E*.
- **M.Sc. Mathematics**, UFJF (2013) · **B.Sc. Mathematics**, UFES (2011)

---

## Languages

Portuguese (native) · English (C1) · Spanish (B2)

---

## Contact

**Email:** arroyo.andre@gmail.com · **LinkedIn:** [pedro-andre-arroyo-silva](https://www.linkedin.com/in/pedro-andre-arroyo-silva/)

Happy to talk about data pipelines, lakehouses or the job market.
