# Data

Output tables from the post-docking selection step. Both use the 128 compounds
that scored <= -8 kcal/mol in AutoDock Vina.

| File | Contents |
|---|---|
| `Kmeans_cluster_results.csv` | KMeans cluster (k = 4) assigned to each compound, with its docking score |
| `Top_6_per_cluster.csv` | The top 4 compounds per cluster by docking score (16 compounds) |

The 16 compounds in the second file were then ranked by ligand efficiency (top 9)
and by 2D interaction analysis (final 4). See `interaction_analysis/`.
