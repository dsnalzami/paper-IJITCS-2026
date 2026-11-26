# Mouth Opening Ratio Carries Most of the Discriminative Information for Lightweight Yawning Detection on YawDD: A Subject-Wise Nested Cross-Validation Study
 
This repository holds the result tables, the extracted features, the cross-validation folds, the logged library versions, and the figures of the study above. The source code is available from the corresponding author on reasonable request: [INSERT: name and email].
 
## Data source
 
The study uses the YawDD dataset (Abtahi, Omidyeganeh, Shirmohammadi, and Hariri; ACM Multimedia Systems 2014, DOI 10.1145/2557642.2563678), distributed as an open-access dataset at IEEE DataPort (DOI 10.21227/e1qm-hb90). The raw videos are not part of this repository and are available from the dataset distributor.
 
## Permissions and privacy
 
This repository contains no video files. Face images appear only in `fig_landmark_overlay.png` and `fig_prediction_examples.png` (Fig. 4 and Fig. 11 of the paper), and only from videos for which the participant table of the dataset marks public sharing of pictures as allowed. The tables contain numerical features derived from facial landmarks, the subject codes and file names of the dataset, and no images.
 
## Contents
 
| Files | Content |
|---|---|
| `fig_*.png` | The 11 figures of the paper (Fig. 1 to Fig. 11) |
| `step08_*` | Metadata validation and the eyewear signal analysis on the Mirror subset (within-subject and between-subject tests, per-video signal summary) |
| `dash_*`, `step09_*` | Features extracted from the 29 unlabeled Dash videos (windows of 5, 6, and 10 s) and the windowing summary |
| `step10_*` | Nested cross-validation of the tabular models: outer folds, fold results, hyperparameter trials, window selection, summaries, out-of-fold predictions, and the fixed-split analysis |
| `step10b_*` | Chebyshev versus Euclidean Mouth Opening Ratio: window features, fold results, tests, and the landmark reproducibility self-test |
| `step11_*` | Sequence models (one-dimensional convolutional network, gated recurrent unit, Transformer): fold results, trials, summaries, out-of-fold predictions |
| `step12a_*`, `step12b_*`, `step12c_*` | Image baseline: face-crop index, frozen backbone with recurrent head, and fine-tuned variant |
| `step13_*` | Statistical tests, equivalence tests, Friedman test, tuning effect, eyewear generalized estimating equations, minimum detectable difference |
| `step14_*` | Cross-view analysis on the Dash subset: domain classifier, subject shift, class presence |
| `step15_*`, `step15b_*` | Latency of each pipeline stage, end-to-end load, Pareto analysis, and the frame-rate sensitivity analysis |
| `step16_*`, `tbl_*`, `supp_config_summary_25.csv` | Source tables of the figures and tables of the paper and the data of Supplementary Tables S1 to S6 |
| `*_environment.csv` | Hardware and library versions recorded at run time for each analysis step |
 
Files with the suffix `.csv.gz` are compressed CSV files. The `step*_fig_*.png` files are earlier diagnostic figures; the figures of the paper are the `fig_*.png` files. The figure `step08_fig_config_val_vs_test.png` shows the first, fixed-split analysis (mean of 10 seeds) that the nested protocol replaced.
 
## Reproducibility notes
 
- The outer folds are stored in `step10_outer_folds.csv` and reused by all models. The seeds are logged in the fold result files.
- Landmark extraction is deterministic within a software environment but not across environments: a second extraction in a later environment (MediaPipe 0.10.35, OpenCV 4.14.0) differed from the stored values in 1.04 percent of the frames (9 of 301 videos), which changed the mean macro F1 by at most 0.001 and single folds by at most 0.017 (`step10b_selftest*.csv`). The versions of the original extraction were not recorded. The extracted features in this repository are the ones used for all reported scores.
## License and citation
 
[INSERT: license of the derived data and figures, chosen by the authors]. When using the contents, cite the paper and the YawDD dataset.
 
