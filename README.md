# ESCHER_RECON3D
The project is being carried out in a JupyterLab using Python and its corresponding tools/libraries/packages.

## INPUT DATA from GEO database

https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE286488

"Single-cell multiomics study of cell-type-specific neuron activation unravels context-dependent gene regulation of brain disorders"
--> GSE286488_RAW.tar

1. Download the *.tar* file
2. Unpack the data
   
   ``tar -xvf GSE286488_RAW.tar``

4. Check data
5. Process data

   ``tar -xvzf GSM8728344_libraries_2_0.tar.gz``

After these steps we obtain 6 different libraries/sample groups which we will process again and obtain directories in which we will find different files, among which: MATRIX file for scRNA-seq analysis (we can see its contents with R: Seurat, or Python: Scanpy). 

The matrix is stored in the HDF5 format (as a *.h5* file), which allows for large datasets.


## INSTALL RECON3D from BiGG database
http://bigg.ucsd.edu/models/Recon3D/

- sbml format
- json format

Use sbml format for working with COBRApy
BUT ESCHER works with json

## INSTALL ESCHER
 ``pip install "escher[notebook]"`` in the conda enviornment that we want

Instead of working this out in a jupyter notebook we will do it in Visual Studio Code. 

1. In the VS Code terminal, activate the Conda environment with Escher
2. Press Cmd + Shift + P (Mac) to open the VS Code Command Palette --> "Python: Select Interpreter" and click on it.
3. Find and select your Conda environment (Jupyter).

THE PROBLEM WAS THAT jupyter notebook v7 did not work with nbesxtensions, so i had to downgrade jupyter notebook to a version below 7.
