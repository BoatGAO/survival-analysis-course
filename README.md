# Survival Lab

An English, interactive study companion following the 13 chapters of John P. Klein and Melvin L. Moeschberger, *Survival Analysis: Techniques for Censored and Truncated Data*, second edition (Springer, 2003).

## First release

- Complete chapter and section navigation.
- Original introductory lessons for Chapters 1–4; Chapters 5–13 are planned outlines.
- Weibull survival explorer, administrative censoring timeline, and editable Kaplan–Meier calculator with Nelson–Aalen estimates.
- Knowledge checks and browser-local review progress.
- Responsive, dependency-free static site. No account, backend, or build needed.

Open `index.html` directly, or run `python3 -m http.server 4173` from this directory and visit http://localhost:4173.

## Publish

Upload the **contents of this directory** to a GitHub repository root, then select Settings → Pages → Deploy from a branch → main → / (root). See `GITHUB_PAGES_CN.md` for a Chinese walkthrough.

## Extend the course

`chapters.js` contains the chapter titles, printed textbook starting pages, section outlines, and `available` flags. `app.js` contains the original notes in `lessons`, checks in `quizzes`, and interactive labs. `styles.css` controls presentation. Add a lesson and quiz before changing its chapter's `available` flag to true. Update the homepage lesson count and progress denominator when expanding beyond the four starter lessons. Available means a starter lesson exists, not that every textbook section is covered.

The calculator accepts nonnegative times and binary event indicators, up to 500 records. Ties process events before censoring; delayed entry, confidence intervals, and competing-risk estimation are not implemented. The examples are synthetic and are intended for learning.

The textbook PDF is deliberately outside this website directory and is not part of the upload package. Notes are original summaries; consult your own textbook for the full treatment and exercises. No full textbook text, figures, or original datasets are reproduced.


## Online course

Visit [Survival Lab](https://boatgao.github.io/survival-analysis-course/) after GitHub Pages deployment completes.
