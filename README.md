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
Newest jupyter notebook is somwhere higher than 7. and that does not work with nbesxtension, so one approach to follow so the installation works, is to downgrade jupyter notebook to a version below 7.

```
pip install escher
pip install "notebook<7"
```


```
pip install escher   
jupyter nbextension install --py escher --sys-prefix
jupyter nbextension enable --py escher --sys-prefix
```

Then we can start a Jupyter Notebook and test Escher:
```
from escher import Builder
builder = Builder()
builder
```

We need a map and a model to make escher work. I created the model in a jupyter notebook but the map is a bit more tricky

## To create the map with sbml2escher
```curl -O https://raw.githubusercontent.com/opencobra/escher/master/py/io/sbml2escher.py```

That helps convert an .xml file to a .json file and obtain the map.


## To create the map from scratch
Anyways the approach I followed because I did not have any node positions nor pathway connections --> manually create a patwya layout in the Escher Web Tool (the escher maps that are already created do not contain relevant or the information for the reactions I need).


We need to validate the map before following to the visualization step with Builder. (RUN IN TERMINAL, not in jupyter notebook)

```python -m escher.validate new_map.json```


## TO CONECT THE SERVER WITH JUPYTER NOTEBOOK
```jupyter notebook --no-browser --port=8888```

and copy the link provided in the terminal



