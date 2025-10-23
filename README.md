# Balancing Policy Objectives in Social Security Reform: A Decision-Analytic Approach
A stochastic, multi-criteria optimization framework (Hierarchical Weighted Multi-voting + Mixed-Integer Goal Programming) that evaluates 142 reform proposals across six policy dimensions: Individual Cost Burden (ICB), Trust (T), Equity (E), Sustainability (S), Administrative Feasibility (AF), and Political Viability (PV). The model integrates LLM-based evaluations with Dirichlet-sampled weights and enforces a 3.5% actuarial balance constraint.

.
├── paper/
│   ├── paper.tex                 # main LaTeX file (apa7, biblatex/biber)
│   ├── references.bib            # bibliography
│   ├── figures/                  # figures (PDF/PNG)
│   ├── tables/                   # tables exported as TeX/CSV
│   ├── appendices/               # A: math, B: data/sim, C: robustness, D: extended tables
│   │   ├── appendixA_math.tex
│   │   ├── appendixB_data_sim.tex
│   │   ├── appendixC_robustness.tex
│   │   └── appendixD_extended.tex
│   ├── sty/                      # optional custom macros
│   └── build/                    # compiled artifacts (PDFs, aux files)
│
├── data/
│   ├── raw/                      # original inputs (SSA-derived, metadata only if restricted)
│   ├── interim/                  # cleaned/transformed
│   └── processed/                # analysis-ready datasets
│
├── scripts/
│   ├── 00_setup.R                # env check, packages, paths
│   ├── 01_prepare_data.R         # ingest/clean SSA COAs, map categories, validate fields
│   ├── 02_evaluate_llms.R        # collate LLM scores, harmonize scales
│   ├── 03_simulate_weights.R     # Dirichlet sampling (construct/model weights)
│   ├── 04_optimize_portfolios.R  # lpSolveAPI MILP; enforce 3.5% balance; export selections
│   ├── 05_sensitivity.R          # stability, Jaccard, kappas, scenarios
│   └── 06_export_tables_figs.R   # write TeX tables and figures used in the paper
│
├── results/
│   ├── selections/               # per-run portfolios, frequencies, diagnostics
│   ├── diagnostics/              # Jaccard matrices, kappa, sensitivity outputs
│   └── exports/                  # final tables/plots for LaTeX include
│
├── LICENSE
└── README.md
