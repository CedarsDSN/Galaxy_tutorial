**Importing count data from Primary Analysis**
==============================================

**If you have run the Primary analysis workflow and would like to import the counts file from the Primary analysis workflow** and use it to conduct differential expression analysis and pathway analysis, use the steps below -

.. note::

  1. From your Primary analysis history, you will notice one of the results collection from featureCounts named as "featureCounts on collection N: Counts"
  2. This is the folder containing the counts for each of your samples. If you used the example dataset, the files should appear as GSM461177_untreat, GSM461178_untreat, GSM461180_treat, and GSM461181_treat
  3. Scroll to the top of the history, and select the settings button
  4. Under Dataset options, Click on the option "Copy Datasets"
  5. This will open a new page where you can check the box next to the dataset you want to copy to a new history. See the screenshot below.
  6. Select the "featureCounts on collection N: Counts" folder and select the "Destination history" as the history you created earlier - "RNA-seq tertiary analysis"
  7. You will need three more files - "KEGG pathways" to provide pathways to goseq, "header" file to create a header file to attach to DESeq2, and the Drosophila gene annotation file to run this workflow.
  8. For your organism, download the GTF file using the steps from "Primary Analysis" into this history. For the Drosophila gene annotation file, download the `file <https://zenodo.org/record/1185122>`_ "Drosophila_melanogaster.BDGP6.87.gtf" and upload it to the history
  9. For the header file, follow the instructions in the note on `this page <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Analysis%20of%20differential%20gene%20expression/Expression%20and%20annotation%20of%20differentially%20expressed%20genes/>`_
  10. For the KEGG pathway file, follow the instructions in the note on `this page <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Functional%20enrichment%20analysis%20of%20differentially%20expressed%20genes/KEGG%20pathway%20analysis/>`_
  11. You can now ready to run the Tertiary analysis workflow and go through the next pages to improve your understanding of each step
  12. Go to workflows > "RNA-seq Tertiary Analysis single factor final version" and click on the run button
  13. Under "Input Dataset Collection", select your collection of counts files
  14. Under gtf file, select your gene annotation file from your history
  15. Under "KEGG pathways to plot", select the KEGG pathway file from your history
  16. Under "header", select the header file from your history
  17. Before you run the workflow, please review the changes you have to make to the DESeq2 tool `instructions <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Analysis%20of%20differential%20gene%20expression/Identification%20of%20differentially%20expressed%20genes/>`_ in order to run it with your dataset
  18. Scroll to the top and select "Yes" to send the results to a new history in order to send your workflow results to a new history and rename it so it's intuitive to you
  19. Click on "Run Workflow"

.. figure:: /images/copying_datasets_option.png
   :width: 900
   :height: 250
   :alt: Copying datasets
   
   The screenshot shows where to find the "Copy Datasets" option in the history

.. figure:: /images/copying_datasets.png
   :width: 900
   :height: 250
   :alt: Copying datasets
   
   The screenshot shows how to copy datasets between two histories (copying featureCounts folder from the previous history to the new history)


