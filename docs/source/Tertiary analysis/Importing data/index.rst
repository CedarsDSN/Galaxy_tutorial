**Importing data**
==================

For the tertiary analysis, we can use the counts from the Primary analysis workflow (specifically from the FeatureCounts tool). Most of the RNA-seq experiments have a single factor that they want to compare, for example, treated vs. untreated. 

Before carrying out the Tertiary analysis workflow, remember to make a new history and name it "RNA-seq tertiary analysis"

If you have run the Primary analysis workflow and would like to import the counts file from the Primary analysis workflow and use it to conduct differential expression analysis and pathway analysis, use the steps below -

.. note::

  1. From your Primary analysis history, you will notice one of the results collection from featureCounts named as "featureCounts on collection N: Counts"
  2. This is the folder containing the counts for each of your samples. If you used the example dataset, the files should appear as GSM461177_untreat, GSM461178_untreat, GSM461180_treat, and GSM461181_treat
  3. Scroll to the top of the history, and select the settings button
  4. Under Dataset options, Click on the option "Copy Datasets"
  5. This will open a new page where you can check the box next to the dataset you want to copy to a new history
  6. Select the "featureCounts on collection N: Counts" folder and select the "Destination history" as the history you created earlier - "RNA-seq tertiary analysis"
  7. You will need three more files - "KEGG pathways" to provide pathways to goseq, "header" file to create a header file to attach to DESeq2, and the Drosophila gene annotation file to run this workflow.
  8. For the Drosophila gene annotation file, download the `file <https://zenodo.org/record/1185122>`_ "Drosophila_melanogaster.BDGP6.87.gtf" and upload it to the history
  9. For the header file, follow the instructions in the note on `this page <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Analysis%20of%20differential%20gene%20expression/Expression%20and%20annotation%20of%20differentially%20expressed%20genes/>`_
  10. For the KEGG pathway file, follow the instructions in the note on `this page <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Functional%20enrichment%20analysis%20of%20differentially%20expressed%20genes/KEGG%20pathway%20analysis/>`_
  11. You can now ready to run the Tertiary analysis workflow and go through the next pages to improve your understanding of each step


If you haven't run the Primary analysis and would rather download the example counts file to run the Tertiary analysis workflow, please follow the steps below - 

.. note::

  1. Import the seven count files from Zenodo or the Shared Data library:
.. code-block:: RST

  https://zenodo.org/record/6457007/files/GSM461177_untreat_paired_featureCounts.counts
  https://zenodo.org/record/6457007/files/GSM461178_untreat_paired_featureCounts.counts
  https://zenodo.org/record/6457007/files/GSM461180_treat_paired_featureCounts.counts
  https://zenodo.org/record/6457007/files/GSM461181_treat_paired_featureCounts.counts

2. Rename each item so that it has the sample name, and the treatment - so for example - GSM461177_untreat_paired_featureCounts.counts becomes GSM461177_untreat


If you haven't run the Primary analysis and would like to run the Tertiary analysis workflow on your own data, please follow the steps below -

