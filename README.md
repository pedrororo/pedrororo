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
