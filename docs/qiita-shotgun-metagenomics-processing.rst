Shotgun metagenomics is an alternative approach to amplicon sequencing, and provides information at the genomic level, rather than only for single loci such as 16S, ITS, or 18S. In addition to potentially providing finer resolution with respect to taxonomic classification, metagenomics provides functional data that allows for more comprehensive analyses of microbial communities. We are currently working to make available additional metagenomic tools in Qiita. Below we describe how to use Shogun to produce taxonomic profiles for shotgun metagenomic data, as well as common analyses of alpha- and beta-diversity.

Processing Shotgun Metagenomics Data
------------------------------------

We will start by creating a new study with shotgun metagenomic data for 23 human fecal samples subsetted from the American Gut Project. As above for amplicon data, go to the study drop-down menu and select 'Create Study'. Complete the necessary fields similar as shown below.

.. figure::  images/shotgun-process-create-study.png
   :align:   center
   
Once the study has been created, click on the study name in the green banner to go to the study page. Click on 'Upload Files', and upload the contents of the zip file 'qiita-shotgun-metagenomics-data.zip' found at the link below.

.. figure::  images/shotgun-process-upload.png
   :align:   center

https://github.com/biocore/cmi-workshops/tree/master/docs/example_data

Once the files are uploaded, click on 'Sample Information' on the left side of the screen and select the sample information file '10768_20180418-105647.txt' and click 'Create'.

.. figure::  images/shotgun-process-sample-info.png
   :align:   center

Once complete, click 'Add New Preparation'. Give the preparation a name, select the prep info file that you uploaded, and select 'Metagenomic' in both of the drop-down menus. Click 'Create New Preparation'.

.. figure::  images/shotgun-process-prep-info.png
   :align:   center

This will create a new preparation under 'Data Types'. Click on the new preparation and then the prep ID. Select 'per_sample_FASTQ - None', and give the files a name. Then click 'Add Files'.

.. figure::  images/shotgun-process-add-files.png
   :align:   center
   
Once your files are added, you should see a processing network with an artifact representing the sequence data.

.. figure::  images/shotgun-process-network.png
   :align:   center
   
We will now process the sequence data using Shogun to create taxa-abundance tables at three hierarchical levels: phylum, family, and genus. Shogun is a metagenomic tool for assigning binned sequence reads to metagenomes, and assigning taxonomy using a reference database. In Qiita, Shogun uses either utree or bowtie2 to align to references.

Running Shogun on human-filtered per-sample FASTQ data
------------------------------------------------------
All shotgun metagenomic data is filtered of human reads prior to being uploaded to Qiita. To process the data using Shogun, click on the per-sample FASTQ artifact named 'Shotgun data' and click 'Process'

.. figure::  images/shotgun-process-shogun1.png
   :align:   center
   
From the dropdown menu, select 'Shogun'.

.. figure::  images/shotgun-process-shogun2.png
   :align:   center
   
Change the 'Parameter set' to 'rep82_utree' and click 'Add Command'.

.. figure::  images/shotgun-process-shogun3.png
   :align:   center
   
You should see the command added to the processing network

.. figure::  images/shotgun-process-shogun4.png
   :align:   center
   
Click 'Run' to run the command.

.. figure::  images/shotgun-process-shogun5.png
   :align:   center
   
Once the command has completed, click on the 'Taxonomic Predictions - species' artifact.

.. figure::  images/shotgun-process-shogun6.png
   :align:   center
   
Examine the table summary to see the number of samples that were retained, and how many features were assembled.

.. figure::  images/shotgun-process-taxa-species.png
   :align:   center
   
   
   
