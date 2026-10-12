# Survival Lab

**Learn survival analysis one chapter at a time, with explanations, formulas, worked examples, and interactive experiments.**

## Open the course website

### [Visit Survival Lab → https://boatgao.github.io/survival-analysis-course/](https://boatgao.github.io/survival-analysis-course/)

Open the link in a browser to use the course. You do not need to download the repository, install software, or sign in to GitHub. The repository's **Code** tab displays source files; the **github.io** link above opens the actual learning website.

- **Live course:** https://boatgao.github.io/survival-analysis-course/
- **Source repository:** https://github.com/BoatGAO/survival-analysis-course
- **Deployment status:** https://github.com/BoatGAO/survival-analysis-course/actions

## About this project

Survival Lab is an English-language study companion for *Survival Analysis: Techniques for Censored and Truncated Data*, **second edition**, by **John P. Klein and Melvin L. Moeschberger** (Springer, 2003).

The chapter and section structure follows the textbook supplied for this project. The explanations are original study notes, designed to connect the mathematical definitions with what researchers actually observe. Printed textbook page ranges appear beside the notes, so learners can return to the corresponding section for its full derivations, original illustrations, datasets, exercises, and references.

The website is intended for learners who know introductory probability and statistical inference and want to understand time-to-event data. It supports independent study or a chapter-based course. It is an educational companion and does not replace the textbook or a validated statistical analysis package.

## Current content

| Chapter | Topic | Current coverage |
|---|---|---|
| 1 | Examples of Survival Data | Detailed notes for all 19 sections: introduction and 18 study examples |
| 2 | Basic Quantities and Models | Detailed notes for all 8 sections, including theory and exercise skills |
| 3 | Censoring and Truncation | Detailed notes for all 7 sections, including likelihood and counting-process theory |
| 4 | Nonparametric Estimation of Basic Quantities for Right-Censored and Left-Truncated Data | Starter explanation and a right-censored Kaplan–Meier/Nelson–Aalen calculator |
| 5 | Estimation of Basic Quantities for Other Sampling Schemes | Textbook section outline; learning notes planned |
| 6 | Topics in Univariate Estimation | Textbook section outline; learning notes planned |
| 7 | Hypothesis Testing | Textbook section outline; learning notes planned |
| 8 | Semiparametric Proportional Hazards Regression with Fixed Covariates | Textbook section outline; learning notes planned |
| 9 | Refinements of the Semiparametric Proportional Hazards Model | Textbook section outline; learning notes planned |
| 10 | Additive Hazards Regression Models | Textbook section outline; learning notes planned |
| 11 | Regression Diagnostics | Textbook section outline; learning notes planned |
| 12 | Inference for Parametric Regression Models | Textbook section outline; learning notes planned |
| 13 | Multivariate Survival Analysis | Textbook section outline; learning notes planned |

### Chapter 1: Learn to describe a survival study

Every textbook example has a study-design explanation: the time origin, event definition, observed information, predictors, censoring/truncation mechanism, and the later methods the example motivates. Topics include leukemia remission, transplantation and intermediate events, dialysis infection, biomarker prognosis, burns, kidney transplantation, laryngeal cancer, transplant type, lymphoma, tumor ploidy, reinfection, infant pneumonia, weaning, psychiatric mortality, retirement-community delayed entry, first marijuana use, interval-observed breast retraction, and right-truncated AIDS induction times.

### Chapter 2: Connect quantities and models

The notes explain survival and distribution functions; continuous densities and discrete masses; hazard and cumulative hazard; conditional survival; hazard shapes; IFR, DFR and IFRA; means, variances, quantiles, residual mean/median lifetime; mixed distributions and product-integral logic; and model-checking plots.

The parametric reference covers all 11 families listed in the chapter: exponential, Weibull, gamma, lognormal, log-logistic, normal, exponential power, Gompertz, inverse Gaussian, Pareto, and generalized gamma. It also explains Erlang/chi-square relationships, Makeham's extension, threshold times, parameter conventions, and moment-existence conditions.

Regression notes distinguish AFT time ratios, multiplicative/Cox hazard ratios, additive hazard differences, and the log-logistic proportional-odds relationship. Competing-risk notes distinguish cause-specific hazards, crude cumulative incidence, net and partial crude probabilities, latent dependence, and identifiability.

### Chapter 3: Understand the observation process

Coverage includes Type I, progressive Type I, generalized Type I, Type II, progressive Type II and random censoring; left, right, double and interval censoring; left, right and interval truncation; delayed-entry risk sets; likelihood contributions; censoring factorization and dependence; truncated/censored conditional likelihoods; and exponential estimation from event counts and exposure.

Counting-process notes cover event/risk processes, filtration and predictability, intensity, compensators, martingales, predictable variation, stochastic integrals, Nelson–Aalen derivation and variance, martingale central limit intuition, Kaplan–Meier product limits, and intensity-based likelihoods. The exercise skill map includes independent exponential censoring and the compensated Poisson process.

For the auditable section/topic map, see [content/COVERAGE.md](content/COVERAGE.md). All **34 sections** in Chapters 1–3 have notes. This is a coverage claim about topics and sections, not a reproduction of every textbook paragraph, dataset, proof, citation, or original exercise answer.

## Interactive features

| Experiment | Location | What you can change and learn |
|---|---|---|
| Weibull playground | Chapter 2 | Change shape and scale; inspect survival, median, and hazard direction |
| Competing risks experiment | Chapter 2 | Change two cause-specific rates and time; compare event-free survival, crude incidence and a net probability |
| Follow-up timeline | Chapter 3 | Move the administrative cutoff; see which events become right-censored |
| Likelihood contribution explorer | Chapter 3 | Select exact/censored/truncated information; inspect its exponential likelihood term |
| Kaplan–Meier lab | Chapter 4 | Edit event/censoring records; inspect the step curve, risk sets, median, and Nelson–Aalen cumulative hazard |

Additional study tools include searchable chapter navigation, within-chapter section jump buttons, expandable original worked explanations, chapter knowledge checks, mastery checklists, and responsive layouts for smaller screens.

## How to study

1. Start with Chapter 1 and practice identifying the clock, endpoint, and observation design.
2. In Chapter 2, work through the quantity relationships before comparing model families.
3. Use the Weibull and competing-risk experiments to check your interpretation of formulas.
4. Read Chapter 3 before treating incomplete event times as ordinary complete data.
5. Open each **Practice** item, attempt it yourself, and then reveal the worked explanation.
6. Use the mastery checklist to identify topics to revisit in the textbook.
7. Mark a chapter as reviewed, then move to the Chapter 4 estimator lab.

Review marks and checklist selections are saved in the current browser's local storage. They do not synchronize between devices or accounts. Clearing browser storage resets them. Calculators run entirely in the browser; entered records are not sent to an analysis server.

## Calculator assumptions and scope

- The Weibull lab uses shape `k` and scale `η`; notes also show the textbook convention `S(t) = exp(−λt^α)`, with `k = α` and `η = λ^(−1/α)`.
- The competing-risk experiment assumes independent latent exponential times with constant rates; it illustrates known-model probabilities, rather than fitting a dataset.
- The likelihood explorer assumes a continuous exponential lifetime distribution with the selected observation/inclusion rule.
- The KM lab accepts up to 500 lines of `time,event`, with finite nonnegative time and event status `1` or `0`. At tied times it processes events before censoring. Censoring marks use a `+` symbol.
- The KM lab covers right censoring without delayed entry. It does not implement left/interval censoring, competing-risk estimation, confidence intervals/bands, or regression fitting. Those distinctions are explained in the notes.
- Interactive data/examples are synthetic. No original textbook dataset tables are distributed with the site.

## Project structure

```text
index.html                 Entry page; uses relative asset paths for GitHub Pages
styles.css                 Responsive styles and print layout
chapters.js                All 13 chapter titles, printed start pages and section outlines
app.js                     Main navigation, review state, original labs and quizzes
content/
  course-notes.js           Detailed English section notes and mastery checklists
  course-ui.js              Section navigation and additional interactive experiments
  chapter-1.md              Readable source notes for Chapter 1 (with HTML formulas)
  chapter-2.md              Readable source notes for Chapter 2 (with HTML formulas)
  chapter-3.md              Readable source notes for Chapter 3 (with HTML formulas)
  COVERAGE.md               Section/topic coverage audit
.nojekyll                  Serve this project as static assets
README.md                  Project introduction and live course link
GITHUB_PAGES_CN.md          Chinese publishing instructions
UPDATE_GITHUB_CN.md         Chinese update commands and troubleshooting
```

The website directly reads `course-notes.js`; the Markdown notes are companion exports. If editing text manually, update the rendered JS notes and the corresponding companion export consistently. Future tooling can automate that synchronization. Adding a new detailed chapter also requires updating the chapter availability, lesson/quiz rendering, and homepage counts; an outline does not by itself mark a chapter as fully taught.

## Local preview

No npm install or build is required. Open `index.html` directly, or serve the directory:

```bash
python3 -m http.server 4173
```

Then visit http://localhost:4173. Stop the local server with Ctrl+C.

## GitHub Pages publishing and updates

The repository publishes **`main` → `/ (root)`** through **Settings → Pages → Deploy from a branch**. When an update is committed and pushed, GitHub Pages builds the new version. Check **Actions** for deployment completion, then refresh the live website.

Typical update commands from this repository directory:

```bash
git add index.html styles.css app.js chapters.js content README.md GITHUB_PAGES_CN.md UPDATE_GITHUB_CN.md .nojekyll .gitignore
git commit -m "Expand Chapters 1-3 and document the live course"
git -c http.version=HTTP/1.1 pull --rebase origin main
git -c http.version=HTTP/1.1 push origin main
```

If a rebase reports a conflict, resolve it before pushing; do not force-push. See [UPDATE_GITHUB_CN.md](UPDATE_GITHUB_CN.md) for the complete Chinese instructions.

## Reference and attribution

Klein, J. P., & Moeschberger, M. L. (2003). *Survival Analysis: Techniques for Censored and Truncated Data* (2nd ed.). Springer.

The supplied textbook is the reference for chapter organization and concepts. These original English learning notes are not an authorized textbook edition. The textbook PDF, full original text, figures, dataset tables and complete exercise collection are not part of the public repository. Consult a copy of the textbook for its full proofs and original supporting material.
