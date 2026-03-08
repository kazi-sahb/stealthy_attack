# stealthy_attack
Authors: Qazi Mairaj ud din (email: mairajuddin.1@osu.edu), Sidra Ghayour Bhatti, and Qadeer Ahmed

A model-free, context-aware Generative Adversarial Framework for Vehicle Systems - simultaneously achieving distributional realism, stealth, and closed-loop impact.

Modern vehicular Cyber-Physical Systems (CPS) rely on tightly coupled sensing–estimation–control loops that are vulnerable to False Data Injection Attacks (FDIAs). While AI-based Intrusion Detection Systems (IDSs) achieve high detection rates against conventional attacks, their resilience against stealthy FDIAs that preserve nominal residual statistics remains largely unexplored. This paper proposes a model-free, context-aware generative adversarial framework that integrates a Conditional Wasserstein GAN (cWGAN) with an AutoEncoder-based observer surrogate to synthesize multivariate sensor measurements that remain statistically consistent with nominal operation. The generator is trained with a multi-objective stealth–impact loss to induce closed-loop performance degradation while maintaining realism and stealth, without requiring prior knowledge of the physical plant or estimator parameters. Evaluation on two real-world vehicle datasets and a high-fidelity Scania truck benchmark model demonstrates that the proposed attacks remain statistically indistinguishable from nominal operation, achieving residual detection exceedance rates as low as 0.77% under a strict 99th-percentile detector (below the 1% false-alarm baseline). Furthermore, the generated attacks successfully evade five State-Of-The-Art (SOTA) automotive IDSs, reducing detection rates to near-baseline false-alarm levels. Dynamic evaluation shows that the stealthy attacks induce persistent undetected velocity-tracking deviations of 12 km/h in closed-loop operation. These results highlight a critical vulnerability of current detection frameworks
and establish the need for offense-informed defense strategies for next-generation intelligent transportation systems.

<img width="859" height="464" alt="intel_stealth_attack_ver3" src="https://github.com/user-attachments/assets/98ad0fef-7e79-4cc3-9b80-a811d9958641" />
<img width="970" height="436" alt="architecture1" src="https://github.com/user-attachments/assets/8c0bb2ba-03cb-4a2f-a2f1-4a95e3829865" />

## Repository Navigation (Where to Find What)

This repository is organized by dataset / evaluation track. The top-level directories correspond to the three benchmarks used in the paper:

- **`Dataset_1/`** — Heavy vehicle (Kenworth) dataset from the Colorado State University Systems Security group [19].  
- **`Dataset_2/`** — Passenger vehicle (KIA Soul) dataset from the Hacking and Countermeasure Research Lab [20].  
- **`Truck_Model/`** — High-fidelity Scania benchmark validated by [21], used for closed-loop dynamic evaluation (see Sec. V-D of the paper).

Each of the above directories follows the same internal structure:

- **Main notebook (entry point):** a Jupyter notebook in the directory (the primary script used to run experiments and reproduce plots/results).
- **`ablation_loss_terms/`** — Ablation study results for different objective/loss-term combinations.
- **`IDS_Eval/`** — Evaluation of state-of-the-art (SOTA) IDS baselines and comparison results.
- **`lambda_grid_search/`** — Hyperparameter sweep results for the \(\lambda\) terms (grid search).
- **`Results/`** — Consolidated figures, plots, and exported result artifacts for the corresponding benchmark.

**Tip:** If you want the fastest starting point, open the notebook inside the benchmark folder you care about (`Dataset_1/`, `Dataset_2/`, or `Truck_Model/`) and follow the cells in order.
