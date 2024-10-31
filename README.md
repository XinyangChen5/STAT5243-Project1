frog’s source of regenerative power


Abstract:
In this analysis, the Leiden and Louvain clustering methods were used to group similar cells within single-cell data, based on principal component analysis (PCA) to reduce dimensions. Leiden clustering, with a resolution of 0.5, created clear and distinct groups, which was confirmed by a high silhouette score, showing good cluster separation. Louvain clustering produced a similar number of groups, and these clusters aligned well with the Leiden results, as shown by a strong adjusted Rand index (ARI). K-means clustering was also used as a comparison, and using the optimal number of clusters based on the Elbow Method, which supported the chosen settings for Leiden and Louvain. To identify specific gene markers for each cluster, using logistic regression and Wilcoxon tests. I looked at the top 20 markers from each method, finding only a small overlap, meaning each method identified slightly different genes. When comparing the identified markers with genes in Supplementary Table 3, I found only one overlapping gene (pcna.S).

Introduction:
Clustering is critical in single-cell data analysis because it groups cells based on gene expression profiles to reveal cell types or states in complex tissues. Identifying these clusters helps to understand the diversity and function of cells in a sample. The Leiden and Louvain algorithms and K-means clustering were chosen to capture meaningful clusters, and each method offers unique advantages in cluster detection and ensures robust results. Identifying marker genes for each cluster is equally important, as these genes define the characteristics of each cell cluster and help provide insight into the biology. By comparing the identified marker genes with established lists (such as those in Supplementary Table 3), it is possible to validate the findings and explore potential new marker genes, adding value to existing knowledge and potentially uncovering unique cellular states.

Methods:
Data Processing
   The dataset was filtered to include only samples from time point zero, resulting in 5,302 cells and 31,535 genes. Log-normalization was applied to standardize gene expression values, ensuring comparability across cells. The analysis focused on the top 2,000 highly variable genes, identified to capture significant expression variations across cells. Low-variance genes, which add noise, were excluded to enhance clustering quality and reduce computational complexity.

Clustering
   Three clustering methods—Leiden, Louvain, and K-means—were employed to capture cell groupings. Leiden and Louvain clustering were applied with a resolution of 0.5. The K-means clustering algorithm determined five clusters using the Elbow Method, where five clusters were chosen based on a point of diminishing returns in within-cluster sum of squares (WCSS). This clustering approach ensured that the grouping structure was both biologically meaningful and computationally efficient.


Dimensionality Reduction
   Principal component analysis (PCA), t-SNE, and UMAP were used for dimensionality reduction and visualization. PCA identified six principal components that explained at least 90% of the variance in the data. These components were then used to compute t-SNE and UMAP embeddings, which showed clear separations of clusters. This visualization confirmed the effectiveness of clustering in identifying distinct cell groups.

Evaluation of Clustering
   Clustering performance was evaluated using the silhouette score and adjusted Rand index (ARI). The silhouette score for Leiden clusters was 0.55, while Louvain clusters achieved a higher score of 0.70, indicating better separation. The ARI between Leiden and Louvain clusters was exceptionally high, at 0.999, showing strong consistency between the two methods and validating the robustness of the clustering results.

Marker Gene Identification
   Marker genes were identified using logistic regression and the Wilcoxon test. The top 20 marker genes from each method were compared, with a high overlap of 222 genes, indicating consistent marker detection. To further assess biological relevance, these marker genes were compared with those in Supplementary Table 3, revealing only one overlapping gene, *pcna.S*. This limited overlap suggests that the analysis may have identified novel cell-type-specific markers not previously documented, potentially revealing new insights into the dataset's unique cellular landscape.

Code Availability
The code and data used for this analysis are publicly available on GitHub at the following link:https://github.com/XinyangChen5/STAT5243-Project1/tree/main. The data at the following link: https://drive.google.com/file/d/1ZU4QHRdZnWpiuiD43bB-Ug8Y2hNl4fxA/view?usp=sharing
Colab: https://colab.research.google.com/drive/1hli0B0fnU6tpPBJ70Xu43mO6DOFSoXKC
Results
Clustering Analysis
The clustering analysis utilized three algorithms—Leiden, Louvain, and K-means—to capture meaningful groupings within the single-cell data. Leiden and Louvain algorithms were applied with a resolution of 0.5, resulting in well-defined clusters. The Elbow Method determined five clusters for K-means by finding the point where additional clusters no longer significantly reduced the within-cluster sum of squares (WCSS). To visualize the clustering structure, t-SNE and UMAP projections were used, revealing clear separations and supporting the effectiveness of the clustering.

To evaluate clustering performance, silhouette scores and adjusted Rand index (ARI) were calculated. Leiden clustering achieved a silhouette score of 0.55, indicating moderate separation among clusters, while Louvain clustering obtained a higher silhouette score of 0.70, suggesting better-defined clusters. The ARI between Leiden and Louvain clustering was 0.999, demonstrating almost complete alignment between the two methods. This high ARI score validates the robustness of the clustering, showing that both Leiden and Louvain algorithms captured similar underlying structures in the dataset. These metrics confirm that the chosen clustering methods provided reliable, biologically relevant groupings.

Marker Selection and Gene Analysis
Marker genes for each cluster were identified using logistic regression and the Wilcoxon test, which rank genes by their expression levels within clusters. Each method generated a list of the top 20 marker genes per cluster, highlighting the genes that most strongly define the clusters. An overlap analysis between the two methods showed a high degree of agreement, with 222 genes identified by both logistic regression and Wilcoxon, indicating that these markers consistently represent the unique characteristics of each cluster.

Conclusion:

The clustering and marker selection analysis provided several valuable insights into the single-cell data structure. Leiden and Louvain clustering proved highly effective, with a nearly perfect adjusted Rand index (ARI) of 0.999, demonstrating strong alignment between the two methods. Louvain clustering achieved a slightly higher silhouette score (0.70) than Leiden (0.55), indicating better-defined clusters, though both methods showed consistent and reliable groupings. The K-means clustering, optimized at five clusters using the Elbow Method, served as a useful baseline and supported the stability of the Leiden and Louvain results.

The marker gene analysis identified highly distinct genes for each cluster using logistic regression and the Wilcoxon test, with 222 overlapping genes, reflecting consistency across methods. However, some limitations are worth noting. The low overlap with Supplementary Table 3 could indicate dataset-specific variations or methodological differences that may affect generalizability. 
