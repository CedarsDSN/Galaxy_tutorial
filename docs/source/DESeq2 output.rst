DESeq2 output
==============

DESeq2 generates three outputs:

1. A table with the normalized counts for each gene (rows) in the samples (columns)

2. A graphical summary of the results, helpful to validate the quality

  a. A plot of the first two dimensions from a Principal Component Analysis (PCA), from the normalized counts of the samples
  
  b. A heatmap of the sample-to-sample distance matrix (with clustering) based on the normalized counts (This gives an overview of how similar and dissimilar the samples are with darker shade showing shorter distance while lighter shade showing more dissimilar samples)
  
  c. Dispersion estimates (It gives a overview of the amount of dispersion in the count data. For a more detailed understanding, see the `paper <https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8>`_)
  
  d. A histogram plot of p-values for the genes which are differentially expressed between the two levels of the first factor provided by the user
  
  e. A MA plot, which is an appliction of a Bland-Altman plot, for representing the count data (A MA plot shows whether your count data shows the distribution that count data normally should with lower expressed genes having higher variability and highly expressed genes showing lower variability)
  
3. A summary tabular file with the following columns -

  a. Gene / feature identifiers
  
  b. Mean normalized counts, averaged over all samples from both conditions 
  
  c. Fold change in log2
  
  d. Standard error estimate for the log2 fold change estimate
  
  e. Wald statistic
  
  f. p-value for the statistical significance of the change
  
  g. p-value adjusted for multiple testing with the Benjamini-Hochberg procedure, which controls for false discovery rate


.. figure:: /docs/deseq2_pca.png
   :scale: 50 %
   :alt: map to buried treasure

   Fig 1: A PCA plot showing the varition between the samples
   
 .. figure:: /docs/deseq2_sample_sample_distance_heatmap.png
   :scale: 50 %
   :alt: map to buried treasure

   Fig 1: Figure showing the heatmap of the sample-to-sample distances
