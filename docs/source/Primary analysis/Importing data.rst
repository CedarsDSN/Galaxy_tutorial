**Importing data**
==================

.. note::

  For users conducting the "Quick-start", please refer to the steps below to create a collection of your input FASTQ files

* Upload all your fastq files using the "Upload data" on the left upper hand corner on the Galaxy homepage (If your file is above 10GB, please use these `instructions <https://galaxy-tutorial.readthedocs.io/en/latest/Primary%20analysis/Importing%20large%20data/>`_)

* Click on "Operations on multiple datasets" at the top of the history panel which is on the right-hand side

* These files should appear in your history on the right-hand side. Check all those that you would like to include in your analysis like below

.. image:: /images/Naming_datasets.png
   :width: 200
   :height: 275
   :alt: Choosing datasets

* Click "For all selected" and choose "Build List of Dataset Pairs"

* In the new panel that appears, rename the text of unpaired forward to a common selector for forward reads and do the same for reverse reads (For example, if your forward reads have _R1 and reverse reads have _R2, use _R1 for selecting forward reads and _R2 for reverse reads)

* Click "Pair these datasets" for each valid forward and reverse pair

* Enter a name for the collection and click "Create List" to build the collection

* To lock the changes, click on the checkmark icon at the top of the history

* Your collection of fastq files is ready to be used in the workflow
