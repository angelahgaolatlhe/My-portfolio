# Portfolio Customisation — Angelah Kgato Gaolatlhe

This document describes all changes made to the original **FolioOne Bootstrap Template** to personalise it as Angelah Kgato Gaolatlhe's professional data science portfolio.

---

## Table of Contents

1. [Overview](#overview)
2. [index.html — Home Page](#indexhtml--home-page)
3. [about.html — About Page](#abouthtml--about-page)
4. [resume.html — Resume Page](#resumehtml--resume-page)
5. [services.html — Skills Page](#serviceshtml--skills-page)
6. [service-details.html — Skill Details Page](#service-detailshtml--skill-details-page)
7. [Global Changes (All Pages)](#global-changes-all-pages)

---

## Overview

The original FolioOne template was a generic Bootstrap 5 portfolio with placeholder content (lorem ipsum text, dummy names, fake stats, and unrelated skill categories). All pages have been fully rewritten with my real, accurate content. Sections that were not applicable (e.g. testimonials, fake stats, unrelated dropdowns) were removed. New sections were added where the template had gaps.

---

## index.html — Home Page

### What was changed
The original hero section was kept as the structural base but substantially reworked.

| Element | Original | Updated |
|---|---|---|
| Page title | "Index - FolioOne Bootstrap Template" | "Angelah Kgato Gaolatlhe - Portfolio" |
| Hero heading | Generic placeholder name | "Hello, I am Angelah Kgato Gaolatlhe" |
| Subheading | Typed animation with unrelated items | "Big Data & Data Science \| MSc Student at AIMS Senegal" |
| Bio paragraph | Long summary paragraph included | **Removed** — kept the page clean and minimal |
| Profile photo shape | Small circular image (300×300px) | Large rounded rectangle (520×560px) |
| Social links | All `href="#"` placeholders | LinkedIn, GitHub, and Email linked to real URLs |
| Nav dropdown | Present with dummy items | **Removed** — replaced with clean direct links |
| Hero layout | Content slightly off-centre with dead space | Full viewport height (`100vh`), content fills the screen |
| Font sizes | Fixed small sizes | Fluid `clamp()` sizing that scales with the viewport |
| Buttons | Standard size | Larger padding, pill border-radius |
| Social icon size | 40px | 52px |

### CSS additions (`<style>` block)
- Hero section set to `min-height: calc(100vh - 70px)` to eliminate dead space
- Profile image uses `min()` sizing to be responsive without overflow
- Fluid typography via `clamp()` on the heading
- Custom `.intro` span for the "Hello, I'm" prefix line
- Social links restyled with hover state (accent colour border + background tint)

---

## about.html — About Page

### What was removed from the original
- **Fake skills grid** (UI/UX, React.js, Mobile-first, Photography) 
- **Fake journey timeline** (2018 B.A. in Design, 2020 Freelance, etc.) 
- **Skills section** with HTML/CSS/JavaScript/Photoshop progress bars 
- **Stats section** with avatar images and counters (185+, 32K, 128+) 
- **Testimonials section** (Saul Goodman, Sara Wilsson, etc.) 

### What was added

#### 1. Intro Section
- First-person introduction written from the CV's professional summary
- Profile photo displayed as a large rounded image
- CTA buttons: "See My Projects" → `portfolio.html` and "View Full Resume" → `resume.html`

#### 3. Areas of Deep Interest (6 cards)
- Data Analysis & Visualisation
- Informed Machine Learning
- Neural Networks
- Explainable AI & Model Interpretability
- Multimodal AI & LLMs
- Applied Mathematics

#### 4. Journey Timeline
A vertical timeline of every real career and education milestone in chronological order:
- BSc Pure & Applied Mathematics — BIUST (2020–2024)
- Finance & Risk Compliance Attaché — BIFM (May–Jul 2023)
- Academic Tutor — Dr Wada's Tutorials (Jul 2024–Jun 2025)
- Data Analytics Intern — Alpha Direct Insurance (Jun–Sep 2025)
- MSc Big Data & Data Science — AIMS Senegal (Oct 2025–present)
- Data Science Intern — Codeva Technologies (Apr 2026–present)

#### 6. Languages Section
Three language badges with flags and proficiency levels:
- 🇧🇼 Setswana — Native
- 🇬🇧 English — Fluent
- 🇫🇷 French — Beginner

#### 7. Personal Tags
Pill-shaped tags drawn from the CV's **Personal Strengths** section:
- Team player & communicator, Curious problem-solver, Research enthusiast, Organised & time-aware, Community volunteer, Adaptable & resilient, Cross-cultural learner, Maths nerd at heart

---

## resume.html — Resume Page

### What was added

| Section | What was added |
|---|---|
| **Professional Summary** | Full paragraph + interests line, added as a full-width row above the two columns |
| **Skills — NoSQL** | Added "NoSQL (MongoDB)" as a new skill bar |
| **Skills — Excel** | Added "Microsoft Excel & Power Query" as a new skill bar |
| **Personal Strengths** | New block listing all strengths from the CV |
| **Languages** | New block with English, Setswana, and French entries |
| **Volunteering Experience** | New section: Publicity Officer at HVN Biust, with full bullet points |
| **References** | "Available upon request" added at the bottom of the right column |

### What was corrected in existing content

| Item | Original | Corrected |
|---|---|---|
| Data Analytics Intern description | Generic one-liner | Expanded with accurate detail from the CV |
| Mathematics Tutor description | Partial detail | Added second bullet about personalised learning plans |
| Finance Attaché description | Had `\&` escape error in bullet | Fixed to proper `&amp;` entity |
| LinkedIn link | `href="#"` | Updated to `https://www.linkedin.com/in/angelah-kgato-gaolatlhe` |

### Layout
The original two-column layout was preserved. New sections were inserted into the appropriate column following the same `resume-item` structure used throughout the page.

---

## services.html — Skills Page

### What was changed

| Element | Original | Updated |
|---|---|---|
| Page title section subtitle | "This section contains information about my skills and expertise." | Kept — appropriate |
| "Learn More" links | All pointed to `service-details.html` (same static page) | Each now passes a unique URL parameter: e.g. `service-details.html?service=data-collection` |
| Service icons | Several used the same generic `bi-code-slash` icon | Updated to distinct, relevant icons per skill |
| LinkedIn social link | `href="#"` | Updated to real LinkedIn URL |
| Nav dropdown | Present with dummy items | **Removed** |

### URL parameters added per skill card

| Skill | URL parameter |
|---|---|
| Data Preprocessing | `?service=data-preprocessing` |
| Data Collection | `?service=data-collection` |
| Machine Learning | `?service=machine-learning` |
| Deep Learning | `?service=deep-learning` |
| Data Mining | `?service=data-mining` |
| High Dimensional Data Analysis | `?service=high-dimensional` |
| Computer Vision | `?service=computer-vision` |
| Web & Android Development | `?service=web-android` |

---

## service-details.html — Skill Details Page

### What was changed
The original page was a **single static page** with generic, unrelated content (Business Process Optimization, fake client testimonials, fake pricing). It has been **completely rewritten** as a dynamic page that renders different content depending on the `?service=` URL parameter passed from `services.html`.

### How it works
On page load, a JavaScript block reads the `?service=` query parameter from the URL and looks up the matching entry in a `services` data object. All page elements are then populated dynamically — no page reload required.

### Content structure for each skill
Every skill entry contains the following fields, all written with real, accurate content:

| Field | Description |
|---|---|
| `category` | Skill category label (e.g. "Data Engineering", "Artificial Intelligence") |
| `title` | Full skill name |
| `description` | One-sentence summary |
| `narrativeHeading` | Section heading for the main body |
| `narrativeBody` | Two-paragraph explanation of how and where the skill was developed |
| `benefits` | 6 cards, each with an icon, title, and detailed description of a specific sub-skill or tool |
| `timeline` | 4–5 items listing specific tools/libraries used, with descriptions |
| `stats` | 3 stat boxes shown in the sidebar overview card |
| `details` | Key-value rows (Primary Language, Libraries, Applied In, etc.) |
| `related` | List of related skills shown in the sidebar |

### Skills covered with real content

| Skill key | Sub-skills / tools documented |
|---|---|
| `data-preprocessing` | Pandas, NumPy, Scikit-learn pipelines, imputation, scaling, encoding, feature engineering, outlier detection |
| `data-collection` | BeautifulSoup, WebScraper.io, KoboToolbox form creation, REST APIs (Requests), SQL extraction, open datasets |
| `machine-learning` | Logistic Regression, Random Forest, SVM, K-Means, DBSCAN, NLP classification, cross-validation, GridSearchCV |
| `deep-learning` | ANN, CNN, RNN, LSTM, TensorFlow/Keras, PyTorch, transfer learning (VGG16, ResNet), TensorBoard |
| `data-mining` | EDA, Matplotlib/Seaborn/Plotly visualisation, correlation analysis, hypothesis testing, feature importance |
| `high-dimensional` | PCA, t-SNE, UMAP, SVD, Lasso, sparse matrices — grounded in BSc Mathematics background |
| `computer-vision` | CNN design, data augmentation, transfer learning, OpenCV, Grad-CAM evaluation |
| `web-android` | HTML5/CSS3/Bootstrap, JavaScript, Flask backend, PostgreSQL/SQLite/MongoDB, Git/GitHub, Android basics |

### Sidebar changes
The original sidebar had a fake client testimonial (Michael Chen, TechCorp) and a consultation form with pricing. These were replaced with:
- A real **Skill Overview card** with stats and key-value detail rows
- A **Related Skills list** with a back link to `services.html`
- A **"Get In Touch" contact form** addressed to Angelah

---

## Global Changes (All Pages)

| Change | Detail |
|---|---|
| **Nav dropdown removed** | The "Dropdown" menu item with five dummy sub-links was removed from all pages — it served no purpose |
| **"Skills" nav link** | All pages updated so the Skills nav item points to `services.html` (not the non-existent `skills.html`) |
| **LinkedIn link** | Updated from `href="#"` to `https://www.linkedin.com/in/angelah-kgato-gaolatlhe` in both the header social links and footer on all modified pages |
| **GitHub link** | Added to relevant pages pointing to `https://github.com/angelahgaolatlhe` |
| **Email link** | Added `mailto:angelahkgatogaolatlhe@gmail.com` where social icons appear |
| **Page titles** | Updated from "FolioOne Bootstrap Template" to descriptive titles per page |
| **Template comments** | Original BootstrapMade license comments preserved as required |

---

No placeholder or fictional content remains in any of the modified pages.
