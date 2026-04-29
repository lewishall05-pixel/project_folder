# Intensive vs. Extensive: Trends of Lethal Violence by the State and Others in South America, 2018–2024

**POLI3148** · Assignment 1 · **Lewis Sydney Campbell Hall** · University of Hong Kong

---

## About This Project

South America is consistently among the most politically violent regions in the world, yet standards measure of conflict severity, i.e. aggregate fatality counts, only distinguish between the volume of violence, not the character of it. The project uses ACLED event data to ask whether/how state and non-state actors in South America kill differently, exploring the difference between state actors producing fewer but deadlier events (*intensive* violence) and non-state actors producing greater but less deadly events (*extensive* violence). Analysis examines this distinction temporally, spatially, and mechanically across 209,317 recorded events between 2018 and 2024.

The interactive report is available at: **[your-username.github.io/your-repo](https://your-username.github.io/your-repo)**

---

## Data Sources

- **Primary dataset:** Armed Conflict Location & Event Data Project (ACLED), retrieved via the [ACLED Data Export Tool](https://acleddata.com/data-export-tool) on 21/04/2026.
- **Coverage:** South America, January 2018 – April 2025. 2025 data excluded, with year incomplete at time of retrieval.
- **Final dataset:** 209,317 events after excluding strategic developments (non-violent actor movements producing no fatalities) and events with unclassified actor types.
- **Actor classification:** Events tagged as state or non-state based on keyword matching against ACLED actor name fields. State actors include those tagged state, government, military, or police; non-state actors include those tagged rebel, militia, criminal organisation, gang, rioter, protester, or civilian. Events involving both actor types carry both flags.
- **Supplementary sources:** Human Rights Watch Reports, InSight Crime Reports, IMF Departmental Papers etc.

---

## Methodology

- **Lethality ratio** — the primary comparative metric, computed as mean state fatalities per event divided by mean non-state fatalities per event. A ratio above 1.0 indicates state actors are more intensively lethal in given period/place.
- **Distribution analysis** established that per-event fatality counts are heavily right-skewed (top 1% of events account for 13% of total deaths), justifying use of median over mean throughout and motivating robustness checks on key findings.
- **Robustness checks** were run by redoing all principal lethality comparisons on a dataset with top 1% of events by fatality count excluded. The lethality ratio shifts by 0.14 between full and robust datasets, confirming findings aren't driven by extreme outlier events.
- **Statistical significance** confirmed through Mann-Whitney U test given the right-skewed distributions identified in exploratory analysis. The test was run one-tailed (H1: state actor events are more lethal than non-state actor events) on both the full and robust datasets, returning p < 0.05 in both cases, confirming impossibility of chance.
- **Programming language:** Python (Google Colab). Interactive visualisations produced with Plotly; static figures produced with Matplotlib & Seaborn.

---

## Key Findings

- State actors are more than **three times as likely** to produce a fatality in an event than non-state actors — 55.2% of state-based events result in at least one death, compared to 17.2% of non-state-based events.
- The state/non-state lethality ratio remains above 1.0 in every year from 2018 to 2024 without exception, confirming gap is structural and not episodic. It peaks at 3.24 in 2021 and declines to 2.02 by 2024.
- The 2021–2022 ratio intensity spike is driven disproportionately by Guyana and Suriname, where a small number of high-lethality state operations against low non-state baselines elevated it. Battles are exclusively state-driven in spike years; violence against civilians are 2/3 non-state-driven; protests contribute zero recorded fatalities.
- Venezuela records the highest state lethality ratio in the dataset, consistent with documented patterns of government repression. Ecuador inverts pattern entirely as the only country where non-state violence exceeds state (driven by gang warfare/prison violence). Brazil approaches near-parity, reflecting domestic criminality of unusual scale and armament.
- Primary mechanism of state intensity is armed clashes, accounting for approximately two-thirds of all state fatalities. Non-state fatalities are concentrated almost entirely in attacks. The two actors do not conduct the same violence at different intensities, instead engaging in wholly different approaches to conflict.

---

## Limits of Findings

- Actor classification relies on keyword matching against ACLED actor name fields; ambiguously named or hybrid actors (e.g. state-affiliated militias) may be miscategorised, potentially understating the state-linked contribution to attack-type fatalities.
- Fatality figures represent a lower bound, with deaths unreported/ in inaccessible media sources not captured by ACLED's collection methodology - an undercounting bias disproportionately affecting remote and rural areas, where non-state armed groups would be the more active actor.
- Double-counting in mixed-actor events. Events involving both actor types carry both flags and appear in both subsets, with no way to tell which actor may have 'initiated' them. Event counts for state and non-state subsets therefore do not sum to the total dataset size.
- Intended analytical window would have been wider if ACLED data collection was further backdated and/or if 2025 data was complete. Long-run trend claims cannot be made from this data as a result.
- Small country sample sizes - i.e. Suriname, Guyana, French Guiana, Uruguay - carry significantly fewer events than Brazil, Colombia, or Venezuela. Lethality ratios for these countries are consequently more sensitive to individual incidents and should be interpreted as correspondingly less proportionally sound.

---

## Project Structure

```
project_folder/
├── README.md                         # This file
├── data/
│   ├── acled_data.zip                # Raw ACLED export; zipped given large size.
│   └── df_filtered.zip               # Cleaned/wrangled dataset (output of Notebook 01); zipped given large size.
├── code/
│   ├── 01_data_cleaning.ipynb        # Data loading, ACLED methodology documentation,
│   │                                 # actor keyword labelling, cleaning, validation
│   ├── 02_exploration.ipynb          # Exploratory data analysis; fatality distributions,
│   │                                 # actor type breakdowns, country and event type
│   │                                 # comparisons, monthly trends, lethality by actor
│   ├── 03_analysis.ipynb             # Main analysis; lethality ratio over time,
│   │                                 # robustness checks, spike decomposition, spatial
│   │                                 # heatmap, event type mechanisms, Mann-Whitney test,
│   │                                 # interactive Plotly chart export
│   └── Z_generate_report.py          # Assembles figures and Plotly snippets into
│                                     # docs/index.html. Run locally after downloading
│                                     # outputs from Google Drive
├── docs/
│   └── index.html                    # Interactive data-driven analysis report,
│                                     # served publicly via GitHub Pages
└── note_on_ai_use.md                 # Description of AI use in project
```

---
 
 
