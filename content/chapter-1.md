# Chapter 1: Examples of Survival Data

Source: Klein & Moeschberger (2003), second edition. Original section-by-section study notes; textbook printed pages are used below.

## 1.1 Introduction

Textbook pp. 1–1.

<p>Survival analysis describes the time until a specified event, which need not be death or an adverse outcome. Recovery, remission, conception, and cessation of smoking can also be events. The clock and endpoint must be defined together: time since treatment is a different outcome from age at death, even when both records end at the same death.</p><h3>The minimum data description</h3><ul><li><strong>Population and sampling:</strong> who can enter the study, how they are selected, and whether observations are independent, matched, or clustered.</li><li><strong>Time origin:</strong> birth, diagnosis, remission, transplantation, or another defined starting point. Distinguish calendar date from elapsed time.</li><li><strong>Event:</strong> a precisely specified outcome; a composite endpoint may combine several outcomes.</li><li><strong>Observation:</strong> an exact event time, last known event-free time, or an interval containing the event. Record the event indicator separately from the time.</li><li><strong>Covariates:</strong> baseline attributes and measurements or intermediate events that change during follow-up.</li><li><strong>Estimand:</strong> overall survival, event-free survival, a cause-specific probability, a group contrast, or prognosis conditional on covariates.</li></ul><div class="formula">Y = min(T, C), &nbsp; δ = I(T ≤ C)<br>T: latent event time; C: right-censoring time; Y: observed follow-up time.</div><p>For a person censored at c, we know T &gt; c. Their event time is not zero, not c, and not missing in the same sense as a completely unobserved record. Deleting them discards known follow-up; treating c as a failure introduces events that were never observed.</p><h3>The observation mechanisms introduced by the examples</h3><div class="table-wrap"><table><thead><tr><th>Mechanism</th><th>Information available</th></tr></thead><tbody><tr><td>Right censoring</td><td>Included subject; event occurs after a boundary.</td></tr><tr><td>Left censoring</td><td>Included subject; event occurred before a boundary.</td></tr><tr><td>Interval censoring</td><td>Included subject; event lies between two observations.</td></tr><tr><td>Left truncation</td><td>Subjects who fail before entry are absent from the sample.</td></tr><tr><td>Right truncation</td><td>Subjects whose events occur after the sampling cutoff are absent.</td></tr></tbody></table></div><p class="note">Reading focus: Sections 1.2–1.19 introduce study designs and recurring datasets. They are not a collection of independent statistical estimators. The notes below identify the endpoint, observation scheme, covariates, and methodological lesson for every example.</p>

## 1.2 Remission Duration from a Clinical Trial for Acute Leukemia

Textbook pp. 2–3.

<h3>Study question and clock</h3><p>Remission begins; follow to leukemia relapse, measured in months.</p><h3>Design and observation</h3><p>42 children were matched within hospitals by remission status and randomized within pairs to 6-MP or placebo.</p><p><strong>Observed information.</strong> Exact relapse times and right-censored remission durations; the textbook uses + to mark censored records.</p><p><strong>Recorded predictors.</strong> Treatment, remission status, and the matching structure.</p><h3>What to learn from this example</h3><p>Learn why a longer observed time with + is only a lower bound on remission duration. Preserve pairs when comparing treatment effects.</p><p>The example returns in product-limit and Nelson–Aalen estimation, mean survival and standard errors, Bayesian estimation, stratified log-rank testing, and stratified proportional hazards modeling.</p>

## 1.3 Bone Marrow Transplantation for Leukemia

Textbook pp. 3–6.

<h3>Study question and clock</h3><p>Transplantation starts the clock. Treatment failure combines relapse and death while still in remission.</p><h3>Design and observation</h3><p>A multicenter cohort of 137 leukemia transplant recipients illustrates a complex recovery process.</p><p><strong>Observed information.</strong> Right-censored follow-up; distinct failure causes; intermediate events may occur before failure.</p><p><strong>Recorded predictors.</strong> Baseline disease/risk group, recipient and donor characteristics, CMV status, waiting time, FAB group, hospital and prophylaxis; acute/chronic GVHD and platelet or granulocyte recovery can update history.</p><h3>What to learn from this example</h3><p>Relapse and death in remission compete for the first failure endpoint. Platelet recovery and GVHD can occur in different orders and alter subsequent prognosis; their future occurrence cannot be treated as known at transplantation.</p><p>This dataset connects survival/CIF estimation, risk-group comparisons, regression, time-dependent covariates, multistate models, and diagnostics. Keep the composite failure indicator separate from the event-type code.</p>

## 1.4 Times to Infection of Kidney Dialysis Patients

Textbook pp. 6–7.

<h3>Study question and clock</h3><p>Time to first exit-site infection after catheter placement, in months.</p><h3>Design and observation</h3><p>Kidney dialysis patients are compared by surgical versus percutaneous catheter placement.</p><p><strong>Observed information.</strong> Right-censored infection times and many tied observation times.</p><p><strong>Recorded predictors.</strong> Catheter-placement group.</p><h3>What to learn from this example</h3><p>Choose the infection definition before comparing groups. Ties affect risk-set arithmetic and Cox partial likelihood. A single constant treatment hazard ratio may miss an early-versus-late effect.</p><p>The text revisits weighted log-rank comparisons, other two-sample tests, tied-time partial likelihood, and checks of proportional hazards.</p>

## 1.5 Times to Death for a Breast-Cancer Trial

Textbook pp. 7–8.

<h3>Study question and clock</h3><p>Time to death, in months, in a breast-cancer follow-up study.</p><h3>Design and observation</h3><p>Patients originally classified as node negative by standard light microscopy were re-examined using immunohistochemistry.</p><p><strong>Observed information.</strong> Deaths are exact; survivors at the observation cutoff are right-censored.</p><p><strong>Recorded predictors.</strong> Immunohistochemical classification is the main grouping variable.</p><h3>What to learn from this example</h3><p>A biomarker-group association concerns prognosis, not automatically a randomized treatment effect. Compare follow-up lengths as well as death counts.</p><p>The dataset motivates survival comparison. Classification method, eligibility, and the survival endpoint are separate design choices.</p>

## 1.6 Times to Infection for Burn Patients

Textbook pp. 8–8.

<h3>Study question and clock</h3><p>Days to staphylococcus infection of a burn wound.</p><h3>Design and observation</h3><p>A change in bathing/disinfection practice is compared with historical routine care.</p><p><strong>Observed information.</strong> Time to infection plus an event indicator; follow-up without infection is censored.</p><p><strong>Recorded predictors.</strong> Baseline sex, race, burn severity, burn sites and type; wound excision and antibiotic treatment have occurrence times and indicators.</p><h3>What to learn from this example</h3><p>Historical controls may differ in calendar period or case mix. Excision and antibiotics are time-dependent: status at a given time uses only what has occurred by that time.</p><p>The example is useful for practicing adjustment and proper coding of intermediate treatments. Association after adjustment is not by itself proof that the protocol caused the difference.</p>

## 1.7 Death Times of Kidney Transplant Patients

Textbook pp. 8–9.

<h3>Study question and clock</h3><p>Time from kidney transplantation to death.</p><h3>Design and observation</h3><p>A transplant-center cohort contains 863 recipients.</p><p><strong>Observed information.</strong> Death or right censoring at loss to follow-up or the common study cutoff.</p><p><strong>Recorded predictors.</strong> Age at transplant, sex, and race.</p><h3>What to learn from this example</h3><p>Administrative censoring and migration/loss to follow-up have different mechanisms. Whether loss is independent of prognosis requires a study-based argument.</p><p>The text uses the example to study smoothed hazard estimation, kernel/bandwidth choices, and discretization of continuous covariates.</p>

## 1.8 Death Times of Male Laryngeal Cancer Patients

Textbook pp. 9–10.

<h3>Study question and clock</h3><p>Years from first treatment for laryngeal cancer to death.</p><h3>Design and observation</h3><p>90 men are classified into four ordered disease stages.</p><p><strong>Observed information.</strong> Exact death times or right censoring at the study end.</p><p><strong>Recorded predictors.</strong> Stage, age at diagnosis, and year of diagnosis.</p><h3>What to learn from this example</h3><p>An ordered stage trend is a different hypothesis from any difference among stages. Stage-by-age interaction asks whether the age association differs by stage.</p><p>Later uses include trend tests; global and local Cox tests; contrasts and confidence intervals; interaction; predicted survival; additive hazards; AFT model fitting and residual checks.</p>

## 1.9 Autologous and Allogeneic Bone Marrow Transplants

Textbook pp. 10–11.

<h3>Study question and clock</h3><p>Months of leukemia-free survival following transplantation.</p><h3>Design and observation</h3><p>Autologous transplant uses the patient’s marrow; allogeneic transplant uses a matched donor’s marrow.</p><p><strong>Observed information.</strong> Exact failures and right-censored leukemia-free durations.</p><p><strong>Recorded predictors.</strong> Transplant type.</p><h3>What to learn from this example</h3><p>The endpoint is remaining alive and free of leukemia. State whether failure means death, relapse, or the first of the two. Early and late differences may influence the choice of comparison statistic.</p><p>The text uses weighted log-rank and censored median/t-type comparisons, Cox diagnostics, outlier/influence analysis, and parametric AFT fit checks.</p>

## 1.10 Bone Marrow Transplants for Hodgkin’s and Non-Hodgkin’s Lymphoma

Textbook pp. 11–12.

<h3>Study question and clock</h3><p>Days from transplant until death or relapse.</p><h3>Design and observation</h3><p>Patients with Hodgkin’s or non-Hodgkin’s lymphoma received autologous or allogeneic transplantation.</p><p><strong>Observed information.</strong> Observed follow-up time Tᵢ with δᵢ = 1 for death/relapse and 0 otherwise.</p><p><strong>Recorded predictors.</strong> Disease category, transplant type, pretransplant Karnofsky score, and months from diagnosis to transplant.</p><h3>What to learn from this example</h3><p>Compare transplant types while accounting for disease category. Stratification allows disease categories to have different baseline survival patterns. A continuous score need not have a linear regression effect.</p><p>The example returns in stratified testing and martingale-residual assessment of the functional form of covariates.</p>

## 1.11 Times to Death for Patients with Cancer of the Tongue

Textbook pp. 12–13.

<h3>Study question and clock</h3><p>Weeks from the study’s surgical/tissue-sampling setting to death during follow-up.</p><h3>Design and observation</h3><p>Tongue-cancer tumors are classified by flow cytometry as aneuploid or diploid.</p><p><strong>Observed information.</strong> Death times plus right-censored observations.</p><p><strong>Recorded predictors.</strong> DNA ploidy group.</p><h3>What to learn from this example</h3><p>Define the survival clock consistently and distinguish tissue classification from the endpoint. A group’s number of deaths alone does not summarize its survival distribution when follow-up varies.</p><p>The dataset supports applied exercises in censored survival comparisons. No original individual records are reproduced here.</p>

## 1.12 Times to Reinfection for Patients with Sexually Transmitted Diseases

Textbook pp. 13–14.

<h3>Study question and clock</h3><p>Time until reinfection after an initial gonorrhea or chlamydia diagnosis.</p><h3>Design and observation</h3><p>A cohort of 877 people with an initial infection is followed for reinfection.</p><p><strong>Observed information.</strong> Follow-up time and a reinfection indicator.</p><p><strong>Recorded predictors.</strong> Demographics, schooling, initial infection type, partners and sexual practices, condom use, and initial symptoms.</p><h3>What to learn from this example</h3><p>The endpoint here is reinfection following the initial episode. This example motivates risk-factor prediction; analyzing many recurrent episodes per person would require an additional dependence structure.</p><p>Interpret predictors conditional on their timing and measurement. Behavioral and symptom variables should not be confused with randomized interventions.</p>

## 1.13 Time to Hospitalized Pneumonia in Young Children

Textbook pp. 14–14.

<h3>Study question and clock</h3><p>Age at hospitalization for pneumonia during the first year of life.</p><h3>Design and observation</h3><p>Longitudinal survey information is used to compare feeding choices and other infant/maternal characteristics.</p><p><strong>Observed information.</strong> Hospitalization age with an indicator of whether hospitalization occurred.</p><p><strong>Recorded predictors.</strong> Feeding choice, birthweight, race, siblings, maternal age/schooling, region, poverty, urban setting, smoking and alcohol during pregnancy.</p><h3>What to learn from this example</h3><p>Hospitalized pneumonia is the recorded event, which differs from every episode of pneumonia. Feeding choice is observational; measured covariates help describe adjustment needs.</p><p>The example supports exercises about event definition, covariate coding, and censored follow-up.</p>

## 1.14 Times to Weaning of Breast-Fed Newborns

Textbook pp. 14–15.

<h3>Study question and clock</h3><p>Weeks from birth until cessation of breast feeding (weaning).</p><h3>Design and observation</h3><p>First-born children whose mothers breast fed form the analysis sample.</p><p><strong>Observed information.</strong> Completed feeding duration or ongoing breast feeding at observation, which is right-censored.</p><p><strong>Recorded predictors.</strong> Maternal race, poverty, smoking/alcohol status, age, education, prenatal care, and child’s birth year.</p><h3>What to learn from this example</h3><p>Weaning is a nonfatal endpoint. Restriction to mothers who initiated breast feeding defines the target population. A retrospective report can add recall or rounding issues.</p><p>The text uses the example for a cohort life table and regression model building aimed at prediction.</p>

## 1.15 Death Times of Psychiatric Patients

Textbook pp. 15–16.

<h3>Study question and clock</h3><p>Years of follow-up after first psychiatric admission; attained age can instead define a lifetime analysis.</p><h3>Design and observation</h3><p>A psychiatric inpatient sample is compared with population mortality standards.</p><p><strong>Observed information.</strong> Death or right censoring, with age at entry and sex recorded.</p><p><strong>Recorded predictors.</strong> Sex, age at admission, and an external reference mortality schedule.</p><h3>What to learn from this example</h3><p>Time since admission and age as a time scale answer different questions. With age as the clock, survival to admission is an entry condition and produces delayed entry.</p><p>Later methods include relative/excess mortality estimation, one-sample comparison with standard mortality, and Cox analysis accounting for left truncation.</p>

## 1.16 Death Times of Elderly Residents of a Retirement Community

Textbook pp. 16–17.

<h3>Study question and clock</h3><p>Age at death or departure, measured in months, for residents of Channing House.</p><h3>Design and observation</h3><p>Only people who lived long enough to enter the retirement community can be observed.</p><p><strong>Observed information.</strong> Left truncation at entry age and possible right censoring after entry.</p><p><strong>Recorded predictors.</strong> Entry age and sex; exit age and status.</p><h3>What to learn from this example</h3><p>A resident is not at risk in the observed sample before entry. Ignoring the entry requirement selects longer survivors and distorts survival estimation.</p><p>The example motivates delayed-entry risk sets, left-truncated survival estimation, male–female comparison, and proportional hazards analysis.</p>

## 1.17 Time to First Use of Marijuana

Textbook pp. 17–18.

<h3>Study question and clock</h3><p>Age at first marijuana use.</p><h3>Design and observation</h3><p>High-school boys reported exact first-use age, never having used it, or prior use with unknown onset age.</p><p><strong>Observed information.</strong> Exact, right-censored at current age, and left-censored at current age: a doubly censored sample.</p><p><strong>Recorded predictors.</strong> Current age and the response category encode the observation, not just a binary event indicator.</p><h3>What to learn from this example</h3><p>“Used it, onset unknown” means T ≤ interview age; “never used it yet” means T &gt; interview age. The two observations provide information in opposite directions.</p><p>The example leads to estimation under left and right censoring. A standard right-censored KM input format cannot encode all three types.</p>

## 1.18 Time to Cosmetic Deterioration of Breast Cancer Patients

Textbook pp. 18–19.

<h3>Study question and clock</h3><p>Months to the first moderate or severe breast retraction after treatment.</p><h3>Design and observation</h3><p>Radiotherapy alone is compared with radiotherapy plus chemotherapy.</p><p><strong>Observed information.</strong> Event onset between the last unaffected and first affected visits is interval-censored; no deterioration by the last visit is right-censored.</p><p><strong>Recorded predictors.</strong> Treatment group and visit schedule.</p><h3>What to learn from this example</h3><p>Detection time is not onset time. Record (L, R] instead of assigning the event to the first positive visit or the interval midpoint without justification.</p><p>The example leads to interval-censored survival estimation. Unequal visit intervals alter the precision of onset information.</p>

## 1.19 Time to AIDS

Textbook pp. 19–20.

<h3>Study question and clock</h3><p>Time from infection to clinical AIDS; infection dates also place cases on a calendar time scale.</p><h3>Design and observation</h3><p>The registry samples people who had developed AIDS by a fixed date.</p><p><strong>Observed information.</strong> Right truncation: infected people who had not developed AIDS by the cutoff are absent, rather than listed as censored records.</p><p><strong>Recorded predictors.</strong> Adult versus pediatric population, infection timing, and induction duration.</p><h3>What to learn from this example</h3><p>Recent infections have a short available induction window. Long induction times are harder to observe near the cutoff, so the observed durations do not form an ordinary complete sample.</p><p>The example motivates right-truncated likelihoods and estimators. Retain infection date to determine each person’s truncation boundary.</p>

