**Importing count data from Primary Analysis**
==============================================

**If you have run the Primary analysis workflow and would like to import the counts file from the Primary analysis workflow** and use it to conduct differential expression analysis and pathway analysis, use the steps below -

.. note::

  1. From your Primary analysis history, you will notice one of the results collection from featureCounts named as "featureCounts on collection N: Counts"
  2. This is the folder containing the counts for each of your samples. If you used the example dataset, the files should appear as GSM461177_untreat, GSM461178_untreat, GSM461180_treat, and GSM461181_treat
  3. Scroll to the top of the history, and select the settings button
  4. Under Dataset options, Click on the option "Copy Datasets"
  5. This will open a new page where you can check the box next to the dataset you want to copy to a new history. Refer to the screenshot 1 and 2 below.
  6. Select the "featureCounts on collection N: Counts" folder and select the "Destination history" as the history you created earlier - "RNA-seq tertiary analysis"
  7. You will need three more files - "KEGG pathways" to provide pathways to goseq, "header" file to create a header file to attach to DESeq2, and the Drosophila gene annotation file to run this workflow.
  8. For your organism, download the GTF file using the steps from "Primary Analysis" into this history. For the Drosophila gene annotation file, download the `file <https://zenodo.org/record/1185122>`_ "Drosophila_melanogaster.BDGP6.87.gtf" and upload it to the history
  9. For the header file, download the file (Above “History”, click on the three dots and download the file) from `this page <https://github.com/CedarsDSN/Galaxy_tutorial/blob/main/docs/source/header.txt>`_ and upload the file to Galaxy using instructions from `here <https://galaxy-tutorial.readthedocs.io/en/latest/Supplementary%20files/Creating%20a%20data%20file/>`_ 
  10. For the KEGG pathway file, download the file from `this page <https://github.com/CedarsDSN/Galaxy_tutorial/blob/main/docs/source/KEGG_pathways_to_plot.txt>`_ and upload the file to Galaxy using instructions from `here <https://galaxy-tutorial.readthedocs.io/en/latest/Supplementary%20files/Creating%20a%20data%20file/>`_
  11. You can now ready to run the Tertiary analysis workflow and go through the next pages to improve your understanding of each step
  12. Go to workflows > "RNA-seq Tertiary Analysis single factor final version" and click on the run button
  13. Under "Input Dataset Collection", select your collection of counts files
  14. Under GTF file - gene annotation, select your gene annotation file from your history
  15. Under "KEGG pathways to plot", select the KEGG pathway file from your history
  16. Under "header", select the header file from your history
  17. Another important note is for the "goseq" tool and "Pathview" tool. Depending on the gene ID format in your GTF file, scroll down to the two goseq tools in the workflow, expand each, and check the format under "Select Gene ID format". Use the button next to it to select your gene ID format from the dropdown list. Repeat this for the "Pathview" tool as well
  18. Before you run the workflow, please review the changes you have to make to the DESeq2 tool `instructions <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Analysis%20of%20differential%20gene%20expression/Identification%20of%20differentially%20expressed%20genes/>`_ in order to run it with your dataset. Refer to screenshot 3 below if you have treated vs untreated samples.
  19. Scroll to the top and select "Yes" to send the results to a new history in order to send your workflow results to a new history and rename it so it's intuitive to you. Screenshot 4 shows how your workflow should look like before you submit.
  20. Click on "Run Workflow"

.. figure:: /images/copying_datasets_option.png
   :alt: Copying datasets option
   
   Screenshot 1 - The screenshot shows where to find the "Copy Datasets" option in the history

.. figure:: /images/copying_datasets.png
   :width: 900
   :height: 250
   :alt: Copying datasets
   
   Screenshot 2 - The screenshot shows how to copy datasets between two histories (copying featureCounts folder from the previous history to the new history)

.. figure:: /images/DESeq2_changes.png
   :alt: DESeq2 changes
   
   Screenshot 3 - The screenshot shows how to change the DESeq2 options

.. figure:: /images/tertiary_workflow_options.png
   :alt: Tertiary workflow options
   
   Screenshot 4 - The screenshot shows how your Tertiary workflow should look with the files selected
