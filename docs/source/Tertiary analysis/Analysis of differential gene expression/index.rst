** Analysis of differential gene expression **
==============================================

DESeq2 carries out the Differential Gene Expression (DGE) analysis and estimates the biological variance using replicates for each condition and also the significance of expression differences between any two conditions. To be able to estimate the biological variance, it is estimated to have at least 3 replicates with preference of 5 biological replicates per condition. On the other hand, to get the best estimates of expression differences between two conditions, it is important to incorporate all the factors that you think may affect the gene expression levels in your experiment. In this tutorial, we will first go through identifying differentially expressed genes, extract and annotate these genes and then visualize their expression and links to them are below -

.. toctree::

   Identification of differentially expressed genes
   Annotation of DESeq2 results
   Expression and annotation of differentially expressed genes
   Visualization of the expression of differentially expressed genes
