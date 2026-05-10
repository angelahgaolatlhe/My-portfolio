# Portfolio Customisation — Angelah Kgato Gaolatlhe

This document describes all changes made to the original **FolioOne Bootstrap Template** to personalise it as Angelah Kgato Gaolatlhe's professional data science portfolio.

---

## Table of Contents

1. [Overview](#overview)
2. [File Renames](#file-renames)
3. [index.html — Home Page](#indexhtml--home-page)
4. [about.html — About Page](#abouthtml--about-page)
5. [resume.html — Resume Page](#resumehtml--resume-page)
6. [skills.html — Skills Page](#skillshtml--skills-page)
7. [skills-details.html — Skill Details Page](#skills-detailshtml--skill-details-page)
8. [portfolio.html — Portfolio Page](#portfoliohtml--portfolio-page)
9. [portfolio-details.html — Project Details Page](#portfolio-detailshtml--project-details-page)
10. [Global Changes (All Pages)](#global-changes-all-pages)

---

## Overview

The original FolioOne template is a generic Bootstrap 5 portfolio with placeholder content (lorem ipsum text, dummy names, fake stats, and unrelated skill categories). All pages have been fully rewritten with real, accurate content. Sections that were not applicable (e.g. testimonials, fake stats, unrelated dropdowns) were removed. New sections were added where the template had gaps. A data-driven, JavaScript-based approach was adopted for both the Skills and Portfolio sections so that new content can be added without creating extra HTML files.

---

## File Renames

Two pages were renamed to better reflect the portfolio's focus on academic and technical skills rather than commercial services.

| Original filename | New filename | Reason |
|---|---|---|
| `services.html` | `skills.html` | The page lists technical skills, not commercial services |
| `service-details.html` | `skills-details.html` | Matches the rename above; the page now details individual skills |

All internal links across every page were updated accordingly — any `href` pointing to `services.html` or `service-details.html` now points to `skills.html` or `skills-details.html`.

---

## index.html — Home Page

### What was changed

| Element | Original | Updated |
|---|---|---|
| Page title | "Index - FolioOne Bootstrap Template" | "Angelah Kgato Gaolatlhe - Portfolio" |
| Hero heading | Generic placeholder name | "Hello, I am Angelah Kgato Gaolatlhe" |
| Subheading | Typed animation with unrelated items | "Big Data & Data Science \| MSc Student at AIMS Senegal" |
| Bio paragraph | Generic placeholder text | Replaced with a real personal welcome message |
| Profile photo | Generic placeholder image | Replaced with Angelah's actual photo |
| Social links | All `href="#"` placeholders | LinkedIn, GitHub, and Email linked to real URLs |
| Nav "Services" link | Pointed to `services.html` | Updated to `skills.html` |
| Nav dropdown | Present with dummy sub-items | **Removed** |

---

## about.html — About Page

### What was removed from the original

- Fake skills grid (UI/UX, React.js, Mobile-first, Photography)
- Fake journey timeline (2018 B.A. in Design, 2020 Freelance, etc.)
- Skills section with HTML/CSS/JavaScript/Photoshop progress bars
- Stats section with avatar images and counters (185+, 32K, 128+)
- Testimonials section (Saul Goodman, Sara Wilsson, etc.)
- Placeholder profile photo

### What was added

**Intro Section**
- First-person introduction paragraph
- CTA buttons: "See My Projects" → `portfolio.html` and "View Full Resume" → `resume.html`

**Areas of Deep Interest** — 6 cards covering:
- Data Analysis & Visualisation
- Informed Machine Learning
- Neural Networks
- Explainable AI & Model Interpretability
- Multimodal AI & LLMs
- Applied Mathematics

**Languages Section** — Three badges with flags and proficiency levels:
- 🇧🇼 Setswana — Native
- 🇬🇧 English — Fluent
- 🇫🇷 French — Beginner

**Personal Tags:**
- Team player & communicator, Curious problem-solver, Research enthusiast, Organised & time-aware, Community volunteer, Adaptable & resilient, Cross-cultural learner, Maths nerd at heart

---

## resume.html — Resume Page

### Layout

The original two-column layout was preserved. New sections were inserted into the appropriate column following the same `resume-item` structure used throughout the page.

### Education & Experience Timeline

A vertical timeline of every real career and education milestone in chronological order:

| Entry | Institution | Period |
|---|---|---|
| BSc Pure & Applied Mathematics | BIUST | 2020–2024 |
| Finance & Risk Compliance Attaché | BIFM | May–Jul 2023 |
| Academic Tutor | Dr Wada's Tutorials | Jul 2024–Jun 2025 |
| Data Analytics Intern | Alpha Direct Insurance | Jun–Sep 2025 |
| MSc Big Data & Data Science | AIMS Senegal | Oct 2025–present |

### What was removed

- Professional skills section with generic progress bars

### What was added

- Certificates section listing real certificates in the order they were obtained

---

## skills.html — Skills Page

*Previously `services.html` in the original template.*

### What was changed

| Element | Original | Updated |
|---|---|---|
| Page title | "Services - FolioOne Bootstrap Template" | "Skills - Angelah Kgato Gaolatlhe" |
| `<body>` class | `services-page` | `services-page` (preserved for CSS compatibility) |
| Section heading | "Services" | "Skills" |
| Section subtitle | Lorem ipsum placeholder | Real description of AIMS Senegal coursework and practical experience |
| Service cards | 6 generic commercial services (Web Dev, Mobile App, UI/UX, etc.) | 11 real skill cards based on AIMS Senegal coursework |
| "Learn More" links | All pointed to the same static `service-details.html` | Each passes a unique `?service=` URL parameter to `skills-details.html` |
| Service icons | Several used the same generic `bi-code-slash` icon | Replaced with distinct, contextually relevant Bootstrap Icons per skill |
| LinkedIn social link | `href="#"` | Updated to real LinkedIn profile URL |
| Nav dropdown | Present with dummy sub-items | **Removed** |
| Nav "Services" item | Pointed to `services.html` | Renamed to "Skills" and points to `skills.html` |

### The 11 skill cards and their URL parameters

| Skill Card | URL Parameter Passed |
|---|---|
| Data Preprocessing | `?service=data-preprocessing` |
| Data Collection | `?service=data-collection` |
| Machine Learning | `?service=machine-learning` |
| Deep Learning | `?service=deep-learning` |
| Data Mining | `?service=data-mining` |
| High Dimensional Data Analysis | `?service=high-dimensional` |
| Computer Vision | `?service=computer-vision` |
| Natural Language Processing | `?service=nlp` |
| Database Systems | `?service=database` |
| Mathematical Methods for Climate Science | `?service=climate-science` |
| Web & Android Development | `?service=web-android` |

---

## skills-details.html — Skill Details Page

*Previously `service-details.html` in the original template.*

### What was changed

The original page was a **single static page** with entirely unrelated content (Business Process Optimization, a fake client testimonial from "Michael Chen at TechCorp Industries", fake pricing of $15K–$45K, and a fake 16-week implementation timeline). It has been **completely rewritten** as a fully dynamic page.

### How it works

On page load, a `<script>` block reads the `?service=` query parameter from the URL and looks up the matching entry in a `services` JavaScript data object embedded in the page. All visible elements are then populated dynamically without any page reload. If no valid parameter is found, a graceful "Skill Not Found" message is displayed.

### Content structure per skill

Every skill entry in the data object contains the following fields, all written with real, accurate content:

| Field | Description |
|---|---|
| `category` | Skill category label (e.g. "Data Engineering", "Artificial Intelligence") |
| `readTime` | Estimated reading time |
| `title` | Full skill name |
| `description` | One-sentence summary displayed in the section subtitle |
| `narrativeHeading` | Heading for the main body narrative section |
| `narrativeBody` | Explanation of how and where the skill was developed at AIMS Senegal |
| `benefits` | 6 cards, each with a Bootstrap Icon, a sub-skill title, and a detailed description |
| `timeline` | 4–6 timeline items listing specific tools/libraries covered, with descriptions and labels |
| `stats` | 3 stat boxes shown in the sidebar Course Overview card |
| `details` | Key-value rows for the sidebar (Primary Language, Libraries, Applied In, etc.) |
| `related` | List of related skills shown in the sidebar with a back link to `skills.html` |

### Skills with full content

| Skill key | Notable sub-skills and tools documented |
|---|---|
| `data-preprocessing` | Python dataclasses, Pydantic, Pandas, EDA, datetime, time series feature extraction, NLTK, TF-IDF |
| `data-collection` | Pandas, BeautifulSoup, Selenium, Tabula, KoboToolbox, SQLite3, Streamlit, GitHub deployment |
| `machine-learning` | Linear/logistic regression, LDA/QDA, CART, KNN, Naive Bayes, Ridge/Lasso/Elastic-net, GAMs, Random Forests, PCA, K-Means, SVMs, intro to neural nets, Scikit-learn, TensorFlow |
| `deep-learning` | ANN, CNN, RNN, LSTM, GRU, gradient descent, SGD, dropout, early stopping, L2, TensorFlow/Keras |
| `data-mining` | Big Data analytics, SOMs, correspondence analysis, categorical clustering, association rules (CRM), sparse factorial methods, component-based regression, clusterwise regression |
| `high-dimensional` | Linear regression, nonparametric regression, PCA, SVD, NumPy, SciPy, Scikit-learn |
| `computer-vision` | CNNs, image pipelines, anomaly detection, transfer learning (VGG16, ResNet50, MobileNet), object detection, segmentation, ViT, contrastive learning (SimCLR) |
| `nlp` | Classic NLP, BoW, TF-IDF, n-grams, Word2Vec, GloVe, RNNs, seq2seq, transformers, LLMs, BERT, summarisation, QA, chatbots, HuggingFace |
| `database` | ER modelling (Chen, Crow's foot, UML), relational model, normalisation (1NF–BCNF), SQL (SELECT, JOINs, window functions), MongoDB, Big Data distributed systems |
| `climate-science` | Linux, Bash scripting, NetCDF, CDO, Python climatology (Xarray, NumPy), K-Means, PCA, SOMs, wavelet analysis |
| `web-android` | Web architecture, REST, SOAP, XML, JSON, Android (Activities, Intents, Mobile IHM), Flutter/Dart, SQL, MySQL, PostgreSQL |

### Sidebar changes

The original sidebar contained:
- A fake client testimonial ("Michael Chen, Operations Director, TechCorp Industries")
- A consultation form with a hidden subject field set to "Business Process Optimization Consultation"
- Fake pricing ($15K–$45K) and team size (3–5 Specialists) details

These were replaced with:
- A real **Course Overview card** with skill-specific stats and key-value detail rows
- A **Related Skills panel** listing connected skill areas with a "Back to All Skills" link to `skills.html`
- A **"Get In Touch" contact form** directed to Angelah for collaboration enquiries

---

## portfolio.html — Portfolio Page

### What was changed

The original portfolio displayed static project cards linked to `#` (no destination). The filter categories (Strategy, Finance, Operations, Technology) were unrelated to data science work. The page was redesigned as an interactive, filterable project gallery with real links.

| Change | Detail |
|---|---|
| Page title | Updated to "Portfolio - Angelah Kgato Gaolatlhe" |
| Section subtitle | Lorem ipsum replaced with real description of the portfolio |
| Filter labels | "Strategy / Finance / Operations / Technology" → "Data Preprocessing / Data Collection / Machine Learning / High Dimensional Data" |
| Filter CSS classes | Updated (`filter-ML`, `filter-finance`, `filter-operations`, `filter-technology`) to match the new filter labels |
| Project cards | 6 generic placeholder projects replaced with Angelah's 6 real projects |
| Project images | Replaced with relevant domain-specific images (`python.jpg`, `ML.jpg`, `HDDA.jpg`, `DL.jpg`, `CV.jpg`, `webdev.jpg`) |
| Detail links | `href="#"` replaced with `href="portfolio-details.html?project=<key>"` for each project |
| Nav dropdown | **Removed** |
| Nav "Services" item | Renamed to "Skills" and updated to `skills.html` |
| LinkedIn social link | Updated to real LinkedIn profile URL |
| "View All Case Studies" button | Removed (not applicable to a student portfolio) |

### Projects added

| Project | Category Tag | URL Parameter |
|---|---|---|
| Student Registration Number | Python / Automation | `?project=student-registration-number` |
| Air Quality Analysis | Machine Learning | `?project=air-quality-analysis` |
| Phone Usage Analysis | High Dimensional Data Analysis | `?project=phone-usage-analysis` |
| Digital Transformation | Deep Learning (CNN/RNN) | `?project=digital-transformation` |
| Computer Vision | AI / Image Recognition | `?project=computer-vision` |
| HTML Web Development | Frontend / Bootstrap | `?project=html-project` |

---

## portfolio-details.html — Project Details Page

### What was changed

The original `portfolio-details.html` contained generic placeholder content: a Swiper image slider using unrelated stock images, placeholder accordion sections ("Business Growth Strategy", "The Challenge", "The Solution"), a fake client badge ("DigitalCraft Solutions"), and tech stack badges (Angular, Express.js, GraphQL, Firebase) unrelated to Angelah's work.

The page was **completely rewritten** as a lightweight, reusable dynamic project page.

### How it works

On page load, a `<script>` block reads the `?project=` query parameter from the URL and looks up the matching entry in a `projects` JavaScript object. The page title, heading, description, image, feature list, and GitHub button are all populated dynamically. If an unknown key is passed, a "Project Not Found" message is displayed with guidance to return to the portfolio.

### Content structure per project

| Field | Description |
|---|---|
| `title` | Full project name |
| `description` | One-paragraph project summary |
| `image` | Path to the project's cover image |
| `features` | Array of 3 key technologies or highlights |
| `github` | Direct URL to the project's GitHub repository |

### Projects with real content

| Project key | GitHub Repository |
|---|---|
| `student-registration-number` | `github.com/angelahgaolatlhe/group2_python_programming_project` |
| `air-quality-analysis` | `github.com/angelahgaolatlhe/gaolatlhe.a.kgato_machine_learning_repository-.../Project` |
| `phone-usage-analysis` | `github.com/angelahgaolatlhe/gaolatlhe.a.kgato_HDDA_repository-.../Project` |
| `digital-transformation` | `github.com/angelahgaolatlhe/DeepLearningCompetition` |
| `computer-vision` | `github.com/angelahgaolatlhe/computer-vision` |
| `html-project` | `github.com/angelahgaolatlhe/html-project` |

### Layout simplification

The heavy original layout (Swiper slider, thumbnail grid, accordion, tech-stack badges, "Next Project" button) was replaced with a clean two-column layout:
- **Left column:** single project cover image
- **Right column:** project title, description, key features list, GitHub link button, and a "Back to Portfolio" button

This makes the page faster to load and easier to maintain. The Swiper carousel and its associated JavaScript configuration were removed entirely.

---

## Global Changes (All Pages)

| Change | Detail |
|---|---|
| **File renames reflected everywhere** | All internal `href` links updated from `services.html` → `skills.html` and `service-details.html` → `skills-details.html` |
| **Nav "Services" → "Skills"** | The navigation item label and link were updated on every page |
| **Nav dropdown removed** | The "Dropdown" menu item with five dummy sub-links was removed from all pages |
| **LinkedIn link** | Updated from `href="#"` to `https://www.linkedin.com/in/angelah-kgato-gaolatlhe` in both the header social links and footer on all modified pages |
| **GitHub link** | Added where appropriate, pointing to `https://github.com/angelahgaolatlhe` |
| **Email link** | Added `mailto:angelahkgatogaolatlhe@gmail.com` where social icons appear |
| **Page titles** | Updated from "FolioOne Bootstrap Template" to descriptive, personalised titles per page |
| **Dynamic content approach** | Both `skills-details.html` and `portfolio-details.html` now use a single-page JavaScript data object pattern, meaning new skills or projects can be added by inserting one new entry into the respective data object — no additional HTML files needed |
| **Template license comments** | Original BootstrapMade license comments preserved as required |

---

No placeholder or fictional content remains in any of the modified pages. All text, links, statistics, project descriptions, and skill content reflect Angelah Kgato Gaolatlhe's real academic background, coursework at AIMS Senegal, and project work.
