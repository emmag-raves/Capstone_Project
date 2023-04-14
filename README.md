# Taxonomy Assignment Cleanup Pipeline
Repository for OES895 Capstone project

Emma Graves


## Overview of the project:

For DNA metabarcoding, 16S or 18S (small subunit) ribosomal DNA is sequenced for each sample, resulting in
a large list of short DNA sequences that is then matched to taxonomy using various different databases. 
Since taxonomy for many organisms, specifically phytoplankton, is ever changing, many databases have 
a different number of classifications for each organism. 

For example, some organisms are only have a kingdom, phylum, 
family, genus, and species listed, whereas others have a kingdom, clade, phylum, subphylum, class, subclass, 
order, suborder, family, subfamily, genus, and species listed. 

This means that when my sequences are matched with the 
database, the resulting taxonomy file has various levels of classification and each rank does not line up in the same
column or item number within that line.


The goal of my capstone project was to create a python script that would clean up taxonomy assignment files
so that each rank was placed in the correct column for all the sequences, as well as remove some of the extra classification
levels that are unnecessary for further analysis. 

## Data

This code is designed to work for **eukaryotic phytoplankton** taxonomy. It includes general rank suffixes (ie. -phyta for phylum),
as well as specific phytoplankton taxonomy assignments that do not follow the normal taxonomic conventions. This script
should be edited before using it on taxonomy from any other group of organisms, in order to include taxonomy assignments
for that group that do not follow the normal suffix conventions. 

A small subset of metabarcoding data from Southern Ocean Phytoplankton communities has been included in this respository
for testing the script. It can be found [here](https://github.com/emmag-raves/Capstone_Project/blob/main/Example_Data/Example_taxa.csv).
This data is a subset of the larger dataset that was used to construct this specific script, which was the result
of matching sequences with the [SILVA database](https://www.arb-silva.de).

## Instructions for using the code:
Example data can be found in [this folder](https://github.com/emmag-raves/Capstone_Project/tree/main/Example_Data). The `Example_taxa.csv` file is an example input file, and the other two files in the folder are the expected output files from this example input file.

The [Capstone Environment File](https://github.com/emmag-raves/Capstone_Project/blob/main/Capstone_environment.yml) should be downloaded and activated in the terminal before running any scripts.

---
To run the Taxonomy_cleanup.py script in the terminal (in Mac), run this command:

`python Taxonomy_cleanup.py Example_taxa.csv`

You may need to make the downloaded python script executable so it will run. This is the terminal command for that:

`chmod +x Taxonomy_cleanup.py`

---
When you run the above code, two additional files will generate in your current working directory. The `Goodtaxa.csv` 
file will contain all the correctly cleaned up taxa. The `Flagtaxa.csv` file will contain any taxa that failed
at the class, order, family, genus, or species level. 


The [Workflow_Script.ipynb](https://github.com/emmag-raves/Capstone_Project/blob/main/Workflow_Script.ipynb) was used to test all the regular expression searching and for and if loops. It is included in this repository 
for additional background and information on the code. It should be runnable using the Example data if the path is changed in the step to read in the data, but the .py script includes
everything from the Workflow script, plus more, so the Workflow script should only be used as a backup.

## Useful software information:
Version of python: Python 3.9.7

Packages used: 
- re : Regular Expressions Operations
- pandas : Powerful Python Data Analysis Toolkit
- sys: System-Specific Parameters and Functions (included in python)

Dependencies can be found in the [Capstone Environment File](https://github.com/emmag-raves/Capstone_Project/blob/main/Capstone_environment.yml).
