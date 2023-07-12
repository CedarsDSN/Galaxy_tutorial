**Using example data**
=======================

Example data can be used to run this workflow. The original tutorial has provided some example data that can be easily downloaded from `here <https://zenodo.org/record/4541751>`_ and used in Galaxy. For this workflow, since it uses only paired-end data, we will be using only the paired end samples from the example data. 

* On the homepage of Galaxy, on the left-handside, click on "Upload data"

* Click on "Paste/Fetch data" button on the textbox that appears

* Paste the below lines and then click "Start"

.. code-block:: RST

  https://zenodo.org/record/4541751/files/GSM461177_1.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461177_2.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461178_1.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461178_1.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461180_1.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461180_2.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461181_1.fastqsanger
  https://zenodo.org/record/4541751/files/GSM461181_2.fastqsanger

* The files should start uploading. One more way is to download the files to your computer from the site and upload them to Filezilla and use FTP to transfer these files (Please use these `instructions <https://galaxy-tutorial.readthedocs.io/en/latest/Primary%20analysis/Importing%20large%20data/>`_)
                                                                                                                                                                          
* Once these files have uploaded, they have to be renamed appropriately to be used in the workflow. When successfully uploaded, the files should appear in a green background in the current history
                                                                                                                                                                           
* Here, samples GSM461177 and GSM461178 are untreated while GSM461180 and GSM461181 are treated
                                                                                                                                                                           
* For renaming, click on the pencil icon next to each sample name. This will open a new window in Galaxy with "Edit Dataset attributes"
                                                                                                                                                                           
* Under name, change the first sample GSM461177_1.fastqsanger to GSM461177_1_untreat and GSM461177_2.fastqsanger to GSM461177_2_untreat. Repeat this for each sample in turn
                                                                                                                                                                           
* For treated samples, change the sample name from GSM461180_1.fastqsanger to GSM461180_1_treat and GSM461180_2.fastqsanger to GSM461180_2_treat
                                                                                                                                                                           
* You are now ready to use your fastq files. The next step so as to make it workflow ready is to create a collection of fastq files. Please refer to these instructions <https://galaxy-tutorial.readthedocs.io/en/latest/Primary%20analysis/Importing%20data/>`_ to create a collection of your files                                                                                                                                                                            
                                                                                                                                                                          
