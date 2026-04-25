# Awsaf-Style Website Rebuild Plan (v3 — locked)

## Objective
Rebuild [jdickamaaz.github.io](https://jdickamaaz.github.io) to closely match [awsaf49.github.io](https://awsaf49.github.io), populated with Shourov Joarder's content. Reference template: **al-folio** Jekyll theme — https://github.com/alshedivat/al-folio.

## Locked Decisions

| # | Decision | Value |
|---|---|---|
| 1 | Stack | **Option B — fork al-folio (Jekyll)** |
| 2 | Identity / role / affiliation | From current `index.html` + `CV_Shourov_Joarder.pdf` |
| 3 | Social links | From current `index.html` |
| 4 | Awards / Experience / Projects | Pulled from `CV_Shourov_Joarder.pdf` |
| 5 | Publications source | Pulled from `CV_Shourov_Joarder.pdf` (built into a `_bibliography/papers.bib`) |
| 6 | "More" menu | Mentorship · Lore · PhD App Tips · Research · Archives · RSS |
| 7 | Placeholder policy | Option 3 — realistic placeholders flagged with `<!-- TODO: replace -->` |

## Stack Plan (Option B specifics)

- Fork al-folio into this repo (preserve `CNAME`, existing `images/`, `theme/img/`, `doc/`, `CV_Shourov_Joarder.pdf`).
- Move existing top-level HTML and Pelican-rendered output into `_legacy/` at cutover so they don't conflict with Jekyll routes.
- Use al-folio's standard Jekyll structure:
  - `_pages/about.md` — home
  - `_pages/publications.md` (renders `_bibliography/papers.bib`)
  - `_pages/projects.md` (renders `_projects/*.md`)
  - `_pages/cv.md` (PDF link + summary card)
  - `_pages/blog.md` (renders `_posts/*.md`, empty for now)
  - New: `_pages/awards.md`, `_pages/experience.md`
- GitHub Pages: use al-folio's GitHub Actions deploy workflow (al-folio uses unsupported Jekyll plugins, so GH Pages' native build won't work). `CNAME` stays at repo root and gets included in the published artifact.

## Content Map (sourced from CV + current index.html)

### Identity
- **Full name**: Shourov Joarder (header style: **Shourov** Joarder)
- **Headline**: Adjunct Lecturer @ BRAC University (CSE) · ML Engineer @ ACI Ltd · BUET EEE '25
- **Location**: Bangladesh
- **Email**: joardershourov60@gmail.com
- **Profile photo**: `theme/img/shourov_img.jpeg` (will move to `assets/img/prof_pic.jpg` per al-folio convention)
- **CV PDF**: `CV_Shourov_Joarder.pdf` (canonical; the older `doc/Shourov_Joarder_cv.pdf` is superseded)

### Social links (from current index.html)
- GitHub: https://github.com/shourovj
- LinkedIn: https://www.linkedin.com/in/shourovj
- X / Twitter: https://x.com/shourovjo
- Email: joardershourov60@gmail.com
- Google Scholar: `<!-- TODO: replace -->` (icon present in CV but URL missing)
- Kaggle: `<!-- TODO: replace -->` (handle "shourovj" referenced in CV)

### About / bio
Reuse the two paragraphs from current `index.html`:
1. "With the recent advancements in state-of-the-art multimodal AI, I am passionate about building real-world systems that are not only accurate but also fundamentally reliable and fair…"
2. "My work focuses on the critical challenges of fairness, generalization, and reasoning and test time training of multimodal models…"

**Interests** (CV "Research Interests"): Computer Vision · Multimodal LLMs (VLMs) · Fairness & Safety of VLMs · Medical Imaging · Autonomous Vehicle

**Detailed interest list** (reuse the 4 numbered items already in current `index.html`).

### Education (CV)
- BUET — B.Sc. EEE, Communication & Signal Processing — Feb 2020 → Mar 2025 — CGPA 3.88/4.00 (2nd in CSP major)

### Publications (CV → `_bibliography/papers.bib`)
1. **MUSSE-Net** — Joarder, Talukder, Hasan. "Multi-Stage Residual-Aware Unsupervised Deep Learning Framework for Consistent Ultrasound Strain Elastography." *Preprint, ready for submission.*
2. **Multilingual Voice-Controlled Smart Wheelchair** — Hasan, Joarder, Nayem, Hasan, Fattah. *IEEE ECCE 2025.* DOI 10.1109/ECCE64574.2025.11013785
3. **Skin Cancer Semantic Segmentation** — Dhar, Sikder, Shovon, Joarder. *IEEE ECCE 2025.* DOI 10.1109/ECCE64574.2025.11013785

Year groupings: 2025, plus a "preprints" slot for #1. Badges: `abs`, `bib`, `pdf`, `code`, `dataset`, `poster`, `video` (al-folio supports these natively). Thumbnails: placeholder per pub.

### Awards (CV → `_pages/awards.md`)
Sections mirroring awsaf (only those Shourov has data for):
- **Competitions**
  - 1st Runner-Up, Undergraduate Project Idea Contest, 25th ICCIT 2022 *(Certificate link — TODO)*
  - Best Notebook Award, DL Sprint — BUET CSE Fest 2022 (Bengali ASR)
  - 57th Public Leaderboard, DL Sprint — BUET CSE Fest 2024 (Bengali AI Math Olympiad)
- **Scholarships / Grants**
  - University Merit Scholarship × 3 (2020, 2021, 2023)
  - University Dean's List Scholarship × 2 (2021, 2022)
  - University Stipend × 2 (2021, 2022)

Skip "Codes / Notebooks" sub-section unless user supplies a Kaggle medal list.

### Experience (CV → `_pages/experience.md`, sticky-side TOC)
**Research**
- Undergraduate Thesis Student, EEE, BUET — *Mar 2024 – Mar 2025* — Supervisor: Dr. Kamrul Hasan — MUSSE-Net thesis bullets.
- Ongoing: Unsupervised RL for LLM Reasoning *(Feb 2026 – Present)*
- Ongoing: Autonomous Driving with VLM + LoRA Distillation *(Github)*
- Ongoing: Debiasing & Explainability of VLM *(Jul 2025 – Present)*

**Professional**
- Adjunct Lecturer, CSE, BRAC University — *Jun 2025 – Present* — Courses: Image Processing (CSE428), Digital Electronics (CSE350)
- Machine Learning Engineer (Part-time), ACI Ltd. — *Apr 2025 – Present* — Medical-ExpertVLM, OCR for prescriptions/cheques (Qwen2.5VL), AI-Assisted Drug Discovery

**Teaching**
- BRAC University — CSE428 (Image Processing), CSE350 (Digital Electronics)

(Reviewer / Open Source / Leadership / Extracurricular: omit until user supplies — do not stub empty.)

### Projects (CV → `_projects/*.md`, masonry grid)
1. Coding Google's PaliGemma VLM from Scratch — Github
2. Autonomous Inventory Robot — Github
3. Deep-Learning-based Breast Cancer Classification (VGGIN) — Github
4. Voice Controlled Wheelchair for Disabled Patients — Github + Video
5. Extracting Audio from Muted Video — Github

Optional future cards (placeholder until public): Medical-ExpertVLM, prescription/cheque OCR tool, AI-Assisted Drug Discovery.

Each card: title, 1-line description, tags (PyTorch / VLM / Medical Imaging / Robotics / etc.), thumbnail (placeholder).

### CV page extras (CV)
- Skills table: PyTorch · TensorFlow · Transformers · vLLM · LangChain · Python · MATLAB · C/C++ · Linux · Verilog · LaTeX · Git · Raspberry Pi · Arduino · FastAPI · Flask · Gradio
- Standardized tests: TOEFL 102 (R26 / L26 / S24 / W26)
- Languages: Bangla, English

### News (reuse from current `index.html`)
- Jun 2025 — Joined CSE, BRAC University as Adjunct Lecturer
- May 2025 — Two papers published on IEEE Xplore (ECCE 2025)
- Apr 2025 — Joined ACI Limited as ML Engineer
- Mar 2025 — Defended undergraduate thesis on Ultrasound Strain Elastography

## Phased Execution

### Phase 0 — Decisions (gate)
Done. All seven items in the Locked Decisions table are answered.

### Phase 1 — Bring in al-folio
- Clone al-folio into a working directory and merge into this repo. Pin to a known-good tag/commit and add `upstream` remote for opt-in updates.
- Preserve at root: `CNAME`, `CV_Shourov_Joarder.pdf`, `theme/img/shourov_img.jpeg` (relocate to `assets/img/prof_pic.jpg`), and `awsaf_site/` reference screenshots.
- Quarantine legacy files into `_legacy/`: `index.html`, `index1.html`, `research.html`, `phd_app_tips.html`, `404.html`, `blog/`, `publications/`, `mentorship/`, `lore/`, `feeds/`, `theme/` (post-photo-relocation), and `bggen/`.
- Configure `_config.yml`:
  - `first_name: Shourov`, `last_name: Joarder`
  - `email`, `description`, `keywords`, `url: https://jdickamaaz.github.io`
  - Social block: scholar (TODO), github, linkedin, twitter, email, kaggle (TODO)
  - Nav order: About · Blog · Publications · Awards · Experience · Projects · CV · More ▾
  - More dropdown items: Mentorship · Lore · PhD App Tips · Research · Archives · RSS (each linking to legacy file or restyled stub)
  - Disable unused al-folio default pages by setting `nav: false` (e.g. `repositories.md`, sample dropdown).
  - `theme_color`: tune to awsaf purple (~#6f42c1).

### Phase 2 — Populate content
1. `_pages/about.md` — bio + photo + interests + news + selected publications (auto-pulled from bib `selected: true`).
2. `_bibliography/papers.bib` — 3 entries with `abbr`, `bibtex_show: true`, `selected: true`; placeholders for `pdf`, `arxiv`, `code` until URLs supplied.
3. `_pages/publications.md` — auto-renders bib by year.
4. `_pages/awards.md` — sections per the Awards content map; enable `toc: true` for sticky sidebar.
5. `_pages/experience.md` — Research / Professional / Teaching only.
6. `_projects/*.md` — five project cards from CV.
7. `_pages/cv.md` — render summary card + PDF download link to `CV_Shourov_Joarder.pdf`.
8. `_pages/blog.md` — empty for now (al-folio default works); flag `<!-- TODO: import legacy posts -->`.
9. `_pages/404.md` — restyle 404.

### Phase 3 — Visual fidelity pass
- Confirm purple accent matches awsaf.
- Confirm header weight pattern (**Shourov** Joarder).
- Year-pill, badge chips, thumbnail-left pub layout — native to al-folio; verify visually.
- Footer text: keep "Adopted from al-folio theme."

### Phase 4 — Cutover
- Add `.github/workflows/deploy.yml` (al-folio's standard one).
- Switch GitHub Pages build source to "GitHub Actions".
- Verify `CNAME` is published in the artifact.
- Test deploy on a `gh-pages-preview` branch first, then merge to `master`.

### Phase 5 — QA
- Desktop + mobile (375 / 768 / 1024 / 1440).
- Theme toggle persistent across pages.
- All `<!-- TODO: replace -->` markers either resolved or explicitly accepted by user.
- All nav links resolve (no 404s into `_legacy/`).
- Lighthouse pass on Home + Publications.

### Phase 6 — Handoff
- Edit guide: how to add a publication (`_bibliography/papers.bib`), a project (`_projects/<slug>.md`), an award (`_pages/awards.md`), update CV (`CV_Shourov_Joarder.pdf`).
- Final punch list of remaining placeholders.

## Outstanding Placeholders (`<!-- TODO: replace -->`)
- Google Scholar URL
- Kaggle URL
- ICCIT 2022 certificate URL
- Per-publication arXiv / PDF / code links
- Publication thumbnails (3)
- Project thumbnails (5)
- Higher-res profile photo (optional — current `shourov_img.jpeg` works as-is)

## Risks & Mitigations
- **al-folio upstream changes break local edits** → pin to a tag; track upstream as `upstream` remote.
- **GH Pages plugin restrictions** → use al-folio's GitHub Actions deploy (CI-built static output).
- **Legacy URLs break inbound links** → add `redirect_from:` Jekyll redirects for any externally-linked legacy paths after cutover.
- **Image path drift between `theme/img/` and al-folio's `assets/img/`** → consolidate under `assets/img/` in Phase 1.
- **Placeholders ship to production** → final pre-launch `grep -r "TODO: replace"` must return zero or be user-signed-off.

## Deliverables
- al-folio-based site at `jdickamaaz.github.io` populated from CV + current `index.html`.
- `_legacy/` snapshot of the pre-rebuild repo.
- Edit guide.
- Open placeholder list.
