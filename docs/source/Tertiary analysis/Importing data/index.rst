**Importing data**
==================

For the tertiary analysis, we can use the counts from the Primary analysis workflow (specifically from the FeatureCounts tool). Most of the RNA-seq experiments have a single factor that they want to compare, for example, treated vs. untreated. 

Before carrying out the Tertiary analysis workflow, remember to make a new history and name it "RNA-seq tertiary analysis"
If you have run the Primary analysis workflow and would like to import the counts file from the Primary analysis workflow and use it to conduct differential expression analysis and pathway analysis, use the steps below -

.. note::

  1. From your Primary analysis history, you will notice one of the results collection from featureCounts named as "featureCounts on collection N: Counts"
  2. This is the folder containing the counts for each of your sample. If you used the example dataset, the files should be appear as GSM461177_untreat, GSM461178_untreat, GSM461180_treat and GSM461181_treat
  3. Scroll to the top of the history, and select the settings button
  4. Under Dataset options, Click on the option "Copy Datasets"
  5. This will open a new page where you can check the box next to the dataset you want to copy to a new history
  6. Select the "featureCounts on collection N: Counts" folder and select the "Destination history" as the history you created earlier - "RNA-seq tertiary analysis"
  7. You will need three more files - "KEGG pathways" to provide pathways to goseq, "header" file to create a header file to attach to DESeq2 and the Drosophila gene annotation file to run this workflow.


If you haven't run the Primary analysis and would rather download the example counts file to run the Tertiary analysis workflow, please follow the steps below - 

If you haven't run the Primary analysis and would like to run the Tertiary analysis workflow on your own data, please follow the steps below -

