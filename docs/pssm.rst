Computing PSSM files
=============================

As a prepocessign step one must compute the PSSM files corespondng to the PDB files in the training/testing dataset. Thiscan be acheived with the PisBLast library (https://ncbiinsights.ncbi.nlm.nih.gov/2017/10/27/blast-2-7-1-now-available/). The library BioPython allows ane asy use of these libraries.


iScore contains wrapper that allows to compute the PSSM data, map them to the PDB files and format them for further processing. The only input needed is the PDB file of the decoy. To compute the PSSM file one can simply use :


>>> from iscore.pssm.pssm import PSSM
>>>
>>> gen = PSSM('1AK4')
>>>
>>> # generates the FASTA query
>>> gen.get_fasta()
>>>
>>> # configure the generator
>>> gen.configure(blast=<path to blast binary>, database=<path to the blast db>)
>>>
>>> # generates the PSSM
>>> gen.get_pssm()
>>>
>>> # map the pssm to the pdb
>>> gen.map_pssm()