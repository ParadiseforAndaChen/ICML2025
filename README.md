# ICML2025

![Two analytic neural networks without hidden layer.](identifiability.png)

**Figure 1.** Two analytic neural networks without hidden layer.

**Table 1.** Mean test performance (± standard deviation) of CORAL-MoE, sparse MoE, CORAL-MLP, and sparse MLP across four large-scale tabular datasets. Accuracy (`↑`) and RMSE (`↓`) are used as surrogate metrics for evaluating model performance over three independent runs.

| Dataset             | Performance | Sparse MoE           | CORAL-MoE           | Sparse MLP           | CORAL-MLP           |
|---------------------|-------------|-----------------------|----------------------|-----------------------|---------------------|
| Helena              | Accuracy `↑`  | 0.28 (1.02×10⁻³)      | 0.29 (5.99×10⁻⁴)     | 0.27 (4.71×10⁻³)      | 0.29 (5.56×10⁻⁴)    |
| Jannis              | Accuracy `↑`  | 0.68 (1.80×10⁻³)      | 0.68 (1.45×10⁻³)     | 0.65 (4.02×10⁻³)      | 0.67 (1.91×10⁻³)    |
| ALOI                | Accuracy `↑`  | 0.75 (2.54×10⁻³)      | 0.85 (1.83×10⁻³)     | 0.73 (3.67×10⁻³)      | 0.78 (2.48×10⁻³)    |
| California Housing  | RMSE `↓`      | 0.62 (1.71×10⁻³)      | 0.61 (1.50×10⁻³)     | 0.63 (2.97×10⁻³)      | 0.61 (1.61×10⁻³)    |


**Table 2.** Runtime (in seconds) of CORAL-Net on four large-scale tabular datasets.

| Data                        | CORAL-Net Runtime |
|-----------------------------|-------------------|
| California Housing (20640×8) | 264.57 s          |
| Helena (65196×27)           | 326.89 s          |
| Janis (83733×54)            | 407.71 s          |
| ALOI (108000×128)           | 774.99 s          |

**Table 3.** Basic statistics of the four tabular datasets used in our experiments, including number of features, number of samples, and task type.

| Dataset            | Features | Sample Size | Type                     |
|--------------------|----------|-------------|--------------------------|
| California Housing | 8        | 20,640      | Tabular / Regression     |
| Helena             | 27       | 65,196      | Tabular / Classification |
| Jannis             | 54       | 83,733      | Tabular / Classification |
| ALOI               | 128      | 108,000     | Tabular / Classification |

**Table 4.** RMSE comparison between the original CORAL-Net with linear activation and the modified version using LeakyReLU. Lower values indicate better performance.

|Performance|$x^\top \beta + h(x \circ \beta)$|$\text{LeakyReLU(x)}^\top \beta + h(x \circ \beta)$|
|--|--|--|
|RMSE`↓`|0.49 (4.06×10⁻³)|0.41 (2.16×10⁻³)|
|Precision`↑`|0.78 (0.16)|1.00 (0.00)|
|Recall`↑`|0.78 (0.16)|1.00 (0.00)|

**Table 5.** Test accuracy of CORAL-Net, LassoNet, DFS, Knockoff, and GCRNet on four large-scale datasets from the Deep Tabular Learning benchmark. Approximately half of the features were selected for each model. All models used identical MLP architectures (hidden dim = 12), trained for 1,000 epochs with Adam optimizer and a learning rate of 0.001. Results are averaged over three independent runs on fixed train/test splits.

| Data | Performance | CORAL               | LassoNet            | DFS                 | Knockoff            | GCRNet              |
|------|-------------|---------------------|---------------------|---------------------|---------------------|---------------------|
| Helena (65196*27)   | Accuracy  `↑`      | **0.29 (5.56 × 10⁻⁴)**  | 0.18 (1.15 × 10⁻²)  | *0.27 (3.29 × 10⁻³)*  | 0.17 (1.89 × 10⁻²)  | 0.15 (1.41 × 10⁻³)  |
| Janis (83733*54)   | Accuracy     `↑`    | *0.67 (1.91 × 10⁻³)*  | 0.64 (3.10 × 10⁻³)  | **0.68 (2.22 × 10⁻³)**  | 0.57 (2.00 × 10⁻²)  | 0.34 (1.77 × 10⁻³)  |
| ALOI (108000*128) | Accuracy      `↑`   | **0.78 (2.48 × 10⁻³)**  | 0.24 (4.14 × 10⁻³)  | *0.67 (2.03 × 10⁻³)*  | 0.18 (1.12 × 10⁻²)  | 0.24 (4.98 × 10⁻³)  |
| California Housing (20640*8)   | RMSE  `↓`      | **0.61 (1.61 × 10⁻³)**  | 0.63 (1.24 × 10⁻²)  | 0.87 (6.38 × 10⁻²)  | *0.62 (8.94 × 10⁻³)*  | 0.65 (1.48 × 10⁻²)  |
