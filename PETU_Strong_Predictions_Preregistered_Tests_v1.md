

# PETU Strong Predictions and Preregistered Tests\\[0.4em]
**Formal prediction classes, null models, thresholds and domain templates**\\[0.7em]
Héctor Eugenio Álvarez García\\
Independent researcher, Spain\\
Version 1.0.0 --- \today


## Claim status and scope

This document is a preregistration-oriented companion to the PETU mathematical formalism and empirical atlas.
It converts triadic structural closure into explicit empirical predictions with frozen definitions, baseline models, null models, thresholds and failure conditions.
It is not a claim that the framework has already become a universal law.

**Public records.** Preprint DOI: https://doi.org/10.5281/zenodo.20821557.
Data/code DOI: https://doi.org/10.5281/zenodo.20820252.
Repository: https://github.com/hector-eag85/petu-triadic-structural-closure-atlas.

## Abstract

This document defines strong predictions and preregistered test families for triadic structural closure.
The framework predicts that coherent natural systems can often be represented by the integrated relation of support $(H)$, structure $(S)$ and linkage $(L)$, with system-level closure denoted by $\Phi$.
The document specifies prediction classes, model hierarchies, null models, baseline comparisons, threshold rules, reporting metrics, falsification criteria and domain-specific preregistration templates.
It distinguishes internal closure reconstruction from external endpoint prediction and requires separation of raw support $\Hraw$ from structured support $\Hstr$ wherever support may already contain structural information.


## General preregistration principle

For each domain $X$, the following must be specified before analysis:
\begin{enumerate}
\item dataset, version, access date and inclusion/exclusion rules;
\item natural observational units $\Omega_X$;
\item perturbative or null units;
\item definitions of $H,S,L,\Phi$;
\item whether $H=\Hraw$ or $H=\Hstr$;
\item primary endpoint and secondary endpoints;
\item monadic, dyadic and triadic baselines;
\item null models;
\item validation strategy;
\item statistical thresholds;
\item failure criteria;
\item interpretation rules.
\end{enumerate}
No domain should be counted as strong confirmatory evidence unless these definitions are frozen before analysis.

## Required model hierarchy

Every preregistered test should evaluate:
\[
M_H:\Phi\sim H,\qquad
M_S:\Phi\sim S,\qquad
M_L:\Phi\sim L,
\]
\[
M_{HS}:\Phi\sim H+S,\qquad
M_{HL}:\Phi\sim H+L,\qquad
M_{SL}:\Phi\sim S+L,
\]
\[
M_{HSL}:\Phi\sim H+S+L,
\]
and, where justified,
\[
M_{int}:\Phi\sim H+S+L+HS+HL+SL+HSL.
\]
The triadic claim is strongest when $M_{HSL}$ or $M_{int}$ outperforms monadic and dyadic baselines while remaining interpretable and resistant to null models.

## Performance metrics

Each test should declare its primary performance functional $P$.
Acceptable metrics include cross-validated $R^2$, Spearman correlation, AUC, mean absolute error reduction, permutation $p$-values, null $z$-scores or domain-specific predictive loss.
Every report should include:
\begin{itemize}
\item sample size and group structure;
\item number of natural and perturbed/null observations;
\item number of scales;
\item $H$-only performance;
\item best dyadic baseline;
\item $HSL$ performance;
\item triadic gain $G_3^{diff}$;
\item null performance;
\item evidence grade;
\item failure modes.
\end{itemize}

## Prediction classes

### P1. Coherence reconstruction

Prediction:
\[
\Phi_X\approx\mathcal{F}_X(H_X,S_X,L_X).
\]
Primary test:
\[
\Phi_X\sim H_X+S_X+L_X.
\]
Initial success threshold:
\[
R^2_{CV}>0.25
\quad\text{or}\quad
\rho_{\mathrm{Spearman}}>0.50.
\]
Failure occurs if $P(HSL\rightarrow\Phi)\leq\tau_\Phi$ under frozen definitions.

### P2. Unity reconstruction

When an external unity endpoint $U_X^{external}$ exists:
\[
U_X^{external}\approx\mathcal{U}_X(H_X,S_X,L_X).
\]
If no external endpoint exists, report
\[
U_X=(H_XS_XL_X)^{1/3}
\]
as a derived PETU index, not as an independent endpoint.

### P3. Irreducible triadic gain

Define
\[
\mathcal{B}=\{H,S,L,H+S,H+L,S+L\}.
\]
Prediction:
\[
G_3^{diff}=P(H+S+L\rightarrow\Phi)-\max_{\mathcal{B}}P(\mathcal{B})>\tau_G.
\]
Recommended initial thresholds:
\[
\Delta R^2_{CV}>0.05,\qquad \Delta AUC>0.03,\qquad \Delta MAE>5\%.
\]

### P4. Linkage emergence from structured support

The clean emergence prediction is
\[
P(\Hraw+S\rightarrow L)-P(\Hraw\rightarrow L)>\tau_L.
\]
If only $\Hstr$ is available, apparent $H\rightarrow L$ must be labelled as structured-support prediction, not pure support prediction.

### P5. Perturbative coherence loss

For a relevant disruptive perturbation $\pi_i$:
\[
\Phi_X>\Phi_{\pi_i(X)}
\quad\text{or}\quad
F_{\pi_i(X)}>F_X.
\]
Define
\[
\Delta_\Phi^i=\operatorname{median}(\Phi_X)-\operatorname{median}(\Phi_{\pi_i(X)}).
\]
Recommended threshold:
\[
\Delta_\Phi^i>0.05
\quad\text{or}\quad
\text{relative coherence loss}>5\%.
\]

### P6. Fragility from disproportion

Prediction:
\[
F_X=\alpha(1-U_X)+\beta(1-B_X)+\gamma D_X+\delta R_X.
\]
Primary test:
\[
F_X\sim 1-U_X+1-B_X+D_X+R_X.
\]
Initial success threshold:
\[
R^2_{CV}>0.25
\quad\text{or}\quad
AUC>0.70
\]
for binary stable/fragile classification.

### P7. Natural-versus-perturbed discrimination

Let $Y=1$ for natural observations and $Y=0$ for perturbative/null observations.
Prediction:
\[
AUC(HSL)>AUC(H)
\]
with
\[
\Delta AUC>0.03.
\]
Stronger support is
\[
AUC(HSL)>0.75.
\]

### P8. Multi-scale stability

For scales $r\in\mathcal{R}_X$:
\[
\Phi_X(r)\approx\mathcal{F}_{X,r}(H_X(r),S_X(r),L_X(r)).
\]
Closure is scale-stable if
\[
\frac{\#\{r:P_r>\tau_\Phi\}}{|\mathcal{R}_X|}\geq0.70.
\]
Failure occurs if closure appears only at a post hoc selected scale.

### P9. External endpoint validity

If an independent endpoint $Y_X$ exists:
\[
Y_X\approx\mathcal{E}_X(H_X,S_X,L_X).
\]
Success requires:
\[
P(HSL\rightarrow Y)>P(H\rightarrow Y)
\]
and $P(HSL\rightarrow Y)>\tau_Y$.
Recommended thresholds:
\[
AUC>0.75
\quad\text{or}\quad
\rho_{\mathrm{Spearman}}>0.40
\]
for noisy external regression.

### P10. Alternative operationalization robustness

Let $(H^{(a)},S^{(a)},L^{(a)})$ and $(H^{(b)},S^{(b)},L^{(b)})$ be two frozen operationalizations.
The directional pattern should hold under at least two preregistered operationalizations.
Failure occurs if the effect appears only under one post hoc feature choice.

### P11. Adversarial null resistance

Nulls may include label shuffling, feature shuffling, within-group permutation, block shuffling, degree-preserving graph randomization, time-phase randomization, spatial nulls and matched-complexity random features.
Success requires:
\[
P_{observed}>P_{null}+\tau_N.
\]
Recommended rule:
\[
z_{null}>2
\quad\text{or}\quad
p_{perm}<0.05,
\]
with correction where applicable.

### P12. Dynamic change prediction

For time-resolved systems:
\[
\Delta\Phi_t\sim\Delta H_t+\Delta S_t+\Delta L_t.
\]
Recommended threshold:
\[
R^2_{CV}>0.20
\quad\text{or}\quad
\rho_{\mathrm{Spearman}}>0.40.
\]

## Domain preregistration template

For each domain, record:
\begin{longtable}{p{0.27\linewidth}p{0.65\linewidth}}
\toprule
**Field** & **Required content**\\
\midrule
Domain & Name and scale class: micro, meso or macro.\\
Dataset & Source, accession, version and access date.\\
Natural units & Definition of $\Omega_X$.\\
$H$ definition & Operational formula and whether $H=\Hraw$ or $H=\Hstr$.\\
$S$ definition & Operational formula.\\
$L$ definition & Operational formula.\\
$\Phi$ definition & Internal, external or derived endpoint; anti-circularity statement.\\
Primary prediction & Choose from P1--P12.\\
Baselines & $H$, $S$, $L$, $H+S$, $H+L$, $S+L$, $H+S+L$.\\
Nulls & Declared null models.\\
Cross-validation & Grouping variable and leakage controls.\\
Success criteria & Exact threshold values.\\
Failure criteria & Exact refutation or weakening conditions.\\
\bottomrule
\end{longtable}

## Domain-specific prediction map

\begin{longtable}{p{0.18\linewidth}p{0.72\linewidth}}
\toprule
**Domain** & **Preregistered prediction focus**\\
\midrule
Microphysics & $HSL\rightarrow\Phi_{micro}$ beyond mass/energy-only baselines and matched-size nulls.\\
Proteins & Folding coherence from energetic support, structural compactness and residue-contact linkage; sequence and contact-map nulls.\\
Genomics & Genomic coherence from sequence support, organization and regulatory/compositional linkage; composition-preserving shuffles.\\
Metabolism & Network coherence from reaction support, topology and flux/connectivity linkage; structured-support exception expected.\\
Neurodynamics & State coherence from signal support, spectral/temporal structure and functional coupling; phase and channel nulls.\\
Cardiorespiratory & Physiological coherence from signal support, rhythm structure and cardiorespiratory coupling; subject-aware validation.\\
Embryogenesis & Developmental coherence from cellular support, transcriptional structure and lineage/signaling linkage.\\
Immune system & Immune-state coherence and external labels from expression support, cell-state structure and immune linkage.\\
Ecosystems & Resilience/stability from species/resource support, network structure and trophic linkage.\\
Hydrology & Regime coherence from flow support, temporal structure and linkage; clean $\Hraw+S\rightarrow L$ test.\\
Climate & Regional coherence from thermal support, spatiotemporal structure and teleconnection linkage; block and phase nulls.\\
Cosmology & Cosmic-web coherence from density support, large-scale structure and filamentary linkage; density-matched nulls.\\
\bottomrule
\end{longtable}

## Cross-domain convergence test

Let $D=\{D_1,\ldots,D_n\}$ be the set of domains and let $P_d$ be the declared domain performance.
Define
\[
C_{atlas}=\frac{1}{n}\sum_{d=1}^n P_d.
\]
Leave-one-domain-out convergence is
\[
C_{atlas}^{(-d)}=
\frac{1}{n-1}\sum_{j\neq d}P_j.
\]
Cross-domain success requires
\[
C_{atlas}>\tau_C
\quad\text{and}\quad
C_{atlas}^{(-d)}>\tau_C
\]
for every domain $d$.
The cross-domain claim fails if convergence depends entirely on one or two domains.

## Evidence grading

\begin{longtable}{p{0.16\linewidth}p{0.74\linewidth}}
\toprule
**Grade** & **Meaning**\\
\midrule
C & Internal $HSL\rightarrow\Phi$ positive, but limited sample and no perturbation or validation.\\
B & Internal reconstruction plus either perturbative contrast or classifier support.\\
A & Strong $HSL\rightarrow\Phi$ and $HSL\rightarrow U$, with null comparisons or cross-validation.\\
A+ & Strong reconstruction, perturbative support and group-aware validation.\\
A++ & Strong internal reconstruction, perturbative support, H-only controls, independent validation and external endpoint or robust cross-domain replication.\\
\bottomrule
\end{longtable}
Evidence grades are descriptive labels and do not replace quantitative reporting.

## Falsification matrix

The theory is weakened or falsified if:
\begin{itemize}
\item $HSL\rightarrow\Phi$ fails under frozen definitions;
\item $HSL$ does not beat $H$-only when $H$ is genuinely raw;
\item $\Hraw+S$ does not improve linkage prediction;
\item perturbations do not reduce $\Phi$ or increase $F$;
\item fragility is unrelated to unity, balance, dominance or rupture;
\item external endpoints fail under anti-leakage validation;
\item alternative operationalizations erase the effect;
\item group-aware cross-validation fails;
\item leave-one-domain-out convergence fails.
\end{itemize}

## Minimal valid preregistered test

A minimal test requires:
\begin{enumerate}
\item one natural dataset;
\item frozen definitions of $H,S,L,\Phi$;
\item one H-only baseline;
\item one dyadic baseline;
\item one HSL model;
\item one null model;
\item one cross-validation strategy;
\item one success threshold;
\item one failure threshold;
\item a statement on whether $H$ is raw or structured.
\end{enumerate}

## Strong preregistered test

A strong test includes all minimal requirements plus:
\begin{itemize}
\item group-aware validation;
\item multiple null models;
\item perturbative contrast;
\item fragility prediction;
\item external endpoint if available;
\item alternative operationalization;
\item leave-one-scale-out validation;
\item public code and public derived outputs.
\end{itemize}

## Master prediction set

\[
P_1:HSL\rightarrow\Phi
\]
\[
P_2:HSL\rightarrow U
\]
\[
P_3:G_3^{diff}>\tau_G
\]
\[
P_4:\Hraw+S\rightarrow L \quad > \quad \Hraw\rightarrow L
\]
\[
P_5:\pi(H,S,L)\rightarrow \downarrow\Phi
\]
\[
P_6:(1-U,1-B,D,R)\rightarrow F
\]
\[
P_7:HSL\rightarrow Y_{natural/perturbed}
\]
\[
P_8:HSL\rightarrow\Phi\text{ across scales}
\]
\[
P_9:HSL\rightarrow Y_{external}
\]
\[
P_{10}:HSL>\text{adversarial nulls}
\]
\[
P_{11}:HSL\text{ robust under alternative operationalizations}
\]
\[
P_{12}:\Delta H,\Delta S,\Delta L\rightarrow\Delta\Phi
\]

## Final statement

PETU strong predictions convert triadic structural closure from a mathematical framework into a concrete empirical research program.
The prediction set is designed to make the framework falsifiable through independent validation, adversarial nulls, alternative operationalizations and preregistered replication.
