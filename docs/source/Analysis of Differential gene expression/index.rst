**Analysis of differential gene expression**
============================================

This is the start of the tertiary analysis that can be carried out on your RNA-Seq samples to further explore your data. At this step, quantification has been carried out for all samples at the gene level and differential expression analysis can be carried out. It is important to know what you would like to compare with regard to your samples. One might think that comparing the count values in the files directly will shed light on the extent of differential gene expression. However, it is a little more complicated than that. The number of sequenced reads which map to a gene depends on two factors -

* The sequencing depth of the samples (Samples sequenced with more depth will have more reads mapping to them)

* The length of the gene (Longer genes will have more reads mapping to them)

To make sure that those genes that are more deeply sequenced or longer aren't overrepresented when comparing expression levels, the gene counts need to be normalized. There are several methods that have been developed over the years out of which DESeq2 is able to account for differences in library composition during normalization, along with sequencing depth of the samples. A more in-depth explanation of the different methods along with examples of the same are in the Galaxy  `tutorial <https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html>`_. 

DESeq2 also carries out the Differential Gene Expression (DGE) analysis and estimates the biological variance using replicates for each condition and also the significance of expression differences between any two conditions. To be able to estimate the biological variance, it is estimated to have at least 3 replicates with preference of 5 biological replicates per condition. On the other hand, to get the best estimates of expression differences between two conditions, it is important to incorporate all the factors that you think may affect the gene expression levels in your experiment. In this tutorial, we will first go through identifying differentially expressed genes, extract and annotate these genes and then visualize their expression and links to them are below -

.. toctree::

   Identification of differentially expressed genes
   Annotation of DESeq2 results
   Expression and annotation of differentially expressed genes
   Visualization of the expression of differentially expressed genes
