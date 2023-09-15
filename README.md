# Bioinformatics 101 -- PPGBiotec

*Summary:*

*This repository contains the scripts for the discipline of Bioinformatics applied in the postgrad course in Biotechnology.*

---

Author: Célio Dias Santos Jr.

Email: celio.diasjunior@gmail.com

Date: 7th September 2023

Location: São Carlos, SP/Brazil

---

## Install to run on Windows

To run this script, you can follow the instructions for the VSCode and Python installation available in the youtube:

[Instructions for installation](https://www.youtube.com/watch?v=qcPIqEVUARE&t=316s)

## Script: 2nd_class_script.py

To run this script you will only need the numpy package. Alternatively you may want to plot the profiles generated by using either Excel or 
dedicated packages in python, such as Seaborn and Matplotlib.

To install numpy, you only need to:

```
$ pip install numpy
```

To run it locally, you will only need:

```
$ python3 2nd_class_script.py
```

And it will generate the results in the screen along with several profiles as `txt` files.

You alternatively can use the functions to calculate your own features of interest separately for sequences
you judge important, like this:

```
from 2nd_class_script import solubility

sequence = 'AKAKAKAKAKAAK'

solubility(sequence, verbose=True)
```

I recommend you explore the functions available, defined in the script with the term `def` in the beginning of the line.

Summarized here, follow the functions that you can use as in the above mentioned example:

| **Function name** | **Description** | **Inputs** |
| :---: | :---: | :---: |
| calc_aafreq | Calculates the frequencies of amino acids and test their fold-change against the average composition of water soluble proteins | calc_aafreq(seq) |
| mw | Calculates the molecular weight of proteins in kDa | mw(seq, verbose=True) |
| prot_charge | Calculates the protein charge in a given pH | prot_charge(seq, pH=7.0, verbose=True) |
| pI | Calculates the isoelectric point of a protein | pI(seq, verbose=True) |
| mol_extinc | Calculates the molecular extinction coefficient of a protein in the two states redox | mol_extinc(seq, verbose=True) |
| profile | Generates a profile of a protein according to the values of a selected scale [See note] | profile(seq, scale, output=f'profile_{scale_name}.tsv', window=5) |
| antigenicity | Calculates the segments potentially antigenic from a sequence with the Kolaskar method | antigenicity(seq, verbose=True) |
| hydrophobicity | Calculates the average hydrophobicity of a protein using a given scale | hydrophobicity(seq, scale='KD', verbose=True) |
| solubility | Estimates the solubility of a given protein by using hydrophobicity inferences | solubility(seq, verbose=True) |
| radius | Calculates the radius for globular and linear (gyration) proteins | radius(seq, verbose=True) |
| sp_vol | Calculates the specific volume of a protein in mL/g | sp_vol(seq, verbose=True) |
| pckg_vol | Calculates the packed volume of a protein in A^3 | pckg_vol(seq, verbose=True) |
| instability_index | Calculates the estability of a protein using instability index (stable if < 40) | instability_index(seq, verbose=True) |
| aliphatic_index | Calculates the aliphatic index, which gives insights about thermostability | aliphatic_index(seq, verbose=True) |
| boman_index | Calculates Boman index, which gives insights about the protein-protein or membrane-protein interaction | boman_index(seq, verbose=True) |
| hmoment | Calculates hydrophobic moment, which gives insights about structural organization | hmoment(seq, angle=100, window=11, verbose=True) |   
| motif_finder | Searches for a motif sequence inside a protein, returning their start/stop and match | motif_finder(motif, seq, output=False, verbose=True) | 

**Note**

You can adopt several scales for the calculations, previously available in the system, such as:

| **Measurement** | **Scale name** |
| :---: | :---: |
| flexibility | bfactors | 
| antigenicity | parker |
| antigenicity | kolaskar |
| hydrophobicity | kyte_doolitle |
| hydrophobicity | hopp_woods |
| hydrophobicity | cornette |
| hydrophobicity | eisenberg |
| hydrophobicity | rose |
| hydrophobicity | janin |
| hydrophobicity | engelman |
