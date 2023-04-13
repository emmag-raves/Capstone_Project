# Taxonomy Assignment Cleanup Pipeline
Repository for OES895 Capstone project

Emma Graves


## Overview of the project:


## Instructions for using the code:
Example data can be found in [this folder](https://github.com/emmag-raves/Capstone_Project/tree/main/Example_Data). The `Example_taxa.csv` file is an example input file, and the other two files in the folder are the expected output files from this example input file.

The [Capstone Environment File](https://github.com/emmag-raves/Capstone_Project/blob/main/Capstone_environment.yml) should be downloaded and activated in the terminal before running any scripts.

To run the Taxonomy_cleanup.py script in the terminal (in Mac), run this command:

`python Taxonomy_cleanup.py Example_taxa.csv`

You may need to make the downloaded python script executable so it will run. This is the terminal command for that:

`chmod +x Taxonomy_cleanup.py`

The [Workflow_Script.ipynb](https://github.com/emmag-raves/Capstone_Project/blob/main/Workflow_Script.ipynb) was used to test all the regular expression searching and for and if loops. It is included in this repository 
for additional background and information on the code. It should be runnable using the Example data if the path is changed in the step to read in the data, but the .py script includes
everything from the Workflow script, plus more, so the Workflow script should only be used as a backup.

## Useful software information:
Version of python: Python 3.9.7
Packages used: 
- re : Regular Expressions Operations
- pandas : Powerful Python Data Analysis Toolkit

Dependencies can be found in the [Capstone Environment File](https://github.com/emmag-raves/Capstone_Project/blob/main/Capstone_environment.yml).
