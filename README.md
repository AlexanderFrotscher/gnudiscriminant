# gnudiscriminant

This program is a scientific library using the GSL and is build for calculating two variants of the linear discriminant analysis. By applying the -r flag when executing the main, one does use a LDA algorithm similar to the LDA algorithm, which can be found in the MASS package of the statistical software R. The author recommends using the -l flag since this version of the LDA is able to calculate the exact solution to the Fisher’s criterion in the high-dimensional case in a short period of time. This variant of the LDA was first proposed by Hua Yu and Jie Yang in 2001.

## Data Preparation

This program needs two input files in order to work. Each file has to be a tab-separated .txt file. One of the files needs to be a training data set and the other one has to be a validation data set. The algorithms work if the columns of the datasets represent the samples. Make sure to list all samples of one class in the training data set behind each other and each label should be a numeric value. Furthermore, the samples in the training data set have to be equally distributed over the classes. Note that the validation data set has to have the same number of features. Then the first class in the file will be denoted as class one in the output files.

## Steps to recreate the small working example

Two files that can be used to recreate a small working example can be found in the bin directory. The “codtestwithlabel.mat” file represents 30 labeled samples of the iris dataset from the statistical software R. Files like this should be used as the training data set. The file “codtest.mat” represents the same samples without labeling. This file can be used as the validation data set if the algorithm was trained with “codtestwithlabel.mat”.

- install zlib from madler and the gnu mp bignum library
- clone the repository of “gnudiscriminant”
- use make in the “gnudiscriminant” directory to build the executable main file
- navigate to the bin directory
- use one of the following bash commands
- ./main -l codtestwithlabel.mat codtest.mat
- ./main -r codtestwithlabel.mat codtest.mat

The solution to the LDA can be found in two files. The classification can be found in the “class.txt” file. The probabilities for each sample to be in one of the classes can be found in “posterior.txt”. Make sure to save the desired file in a different place since the two output files will be overwritten by using the program.

## Appendix

“gnudiscriminant” further uses source code from the library gnupca written by Prof. Steve Hoffmann. Therefore, you have to install the libraries zlib from madler and the gnu mp bignum library.

The source code was part of a bachelor thesis at the Comp Biol AG of the Fritz Lipmann Institut.


