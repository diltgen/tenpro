# tenpro

An extension for L. Lewark's program "khoca" (available [here](https://github.com/LLewark/khoca)) for computing the tensor product of two reduced Z[G]-complexes. It takes as input two plain-text files containing the output of khoca when run with the parameters "0 e2 0" and "calcred0" (i.e. the reduced Z[G]-complex) and computes the corresponding tensor product. In order to simplify the result, tenpro contains a copy of the "khoca" extension "homca" (available [here](https://github.com/dilt1337homca)) which in this case tries to decompose the tensor product into direct summands that are as simple as possible (in terms of rank).

# Installation

tenpro is written in Sage with Python and comes packed as a Jupyter Notebook (hence the .ipynb file extension). In order to run it, you need to have:

1. [khoca](https://github.com/LLewark/khoca);
2. [SageMath](https://www.sagemath.org/) (v.9.2.0 or higher);
3. [Jupyter (Notebook)](https://jupyter.org/install).

To run tenpro, simply open a terminal and type "jupyter notebook" to start Jupyter Notebook and open the file "tenpro.ipynb". You should now see the input cell with the source code. Below the big "Setup"-box, specify the path to containing your khoca output files and directly below the name of the files (if you already have them). This completes installation.

# How to use

1. If you don't already have khoca output files for which you would like to compute the tensor product, run khoca as follows: "./khoca.py 0 e2 0 KNOT calcred0 > /path/to/save/output/output.txt", where KNOT is your knot encoded in one of khoca's supported options (e.g. braid or PD), and "/path/to/save/output/output.txt" is the path where you would like to save the output-file (the name of the file may be changed).
2. In tenpro, specify the path containing your khoca output files and directly below the name of the files.
3. Set printing options (see below).
4. Hit "Shift+Enter".

# Printing options

tenpro features various options for printing the output. These include:

1. printing the matrices of the differentials of the tensor product ("prnttpmatrices");
2. printing the simplified matrices of the differentials of the tensor product ("prntmatrices");
3. printing the direct summands obtained from the simplified matrices of each differential ("prntpieces");
4. printing summands that are supported in more than two homological degrees ("prntchains");
5. printing the (unique) direct summand of odd rank ("prntoddpiece").

Parameters for the printing options are stored as python lists; check tenpro to see the options.

# IMPORTANT

Currently tenpro can only compute the tensor product of two Z[G]-complexes at a time; for the tensor product of more than two Z[G]-complexes one has to do the computations one after another. However, there is currently no method implemented that produces a khoca output file of the tensor product computed by tenpro, hence one has to create the file manually in order to use it again tenpro. Moreover, tenpro currently only accepts Z[G]-complexes that do not contain any trivial differentilas (i.e. no empty matrices "[]" are allowed in the khoca output). For important information regarding the reduction algorithm implemented by homca, please check the readme at https://github.com/dilt1337homca.

# To be implemented

1. Computation of the tensor product of more than two Z[G]-complexes at a time.
2. Allow Z[G]-complexes that contain trivial differentials.

# Note

While working on this program, the author Damian Iltgen was supported by the Emmy Noether Programme of the DFG, project number 412851057.
