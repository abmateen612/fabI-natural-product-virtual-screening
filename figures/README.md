# Figures

Plots for the post-docking selection step. Both use the 128 compounds that
scored <= -8 kcal/mol in AutoDock Vina.

## pca_chemical_space.png

PCA of Morgan fingerprints (radius 2, 1024 bits). Each point is one compound,
coloured by KMeans cluster (k = 4). It shows how the docked hits spread across
chemical space and which cluster each belongs to. The top 4 compounds per
cluster, by docking score, were taken for the next step.

## kmeans_elbow_silhouette.png

Elbow plot and silhouette plot used to choose the number of clusters. The value
k = 4 was selected from these two plots.
