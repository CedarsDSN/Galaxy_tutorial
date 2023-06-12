**Tertiary Analysis**
============================================

This is the start of the tertiary analysis that can be carried out on your RNA-Seq samples to further explore your data. At this step, quantification has been carried out for all samples at the gene level and differential expression analysis can be carried out. It is important to know what you would like to compare with regard to your samples. One might think that comparing the count values in the files directly will shed light on the extent of differential gene expression. However, it is a little more complicated than that. The number of sequenced reads which map to a gene depends on two factors -

* The sequencing depth of the samples (Samples sequenced with more depth will have more reads mapping to them)

* The length of the gene (Longer genes will have more reads mapping to them)

To make sure that those genes that are more deeply sequenced or longer aren't overrepresented when comparing expression levels, the gene counts need to be normalized. There are several methods that have been developed over the years out of which DESeq2 is able to account for differences in library composition during normalization, along with sequencing depth of the samples. A more in-depth explanation of the different methods along with examples of the same are in the Galaxy  `tutorial <https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html>`_. In this tutorial, we will first go through analysis of differential gene expression, and further conduct functional enrichment analysis using these links below-

.. toctree::

   Tertiary analysis/Analysis of differential gene expression/index.rst
   Tertiary analysis/Functional enrichment analysis of differentially expressed genes/index.rst
