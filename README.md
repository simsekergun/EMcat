# Classification with Electromagnetic Waves

## 2023 UMBC MPS Classification Competition
This dataset is created for UMBC MPS Data Science Students. 

Students can work in teams or individually. The deadline for the initial step is November 15, 23:59 pm. The participants are expected to email [Dr. Simsek](mailto:simsek@umbc.edu) only the validation accuracy of their implementation (that was evaluated using the testing dataset only, which was not used in the training). The 3 students/teams with the highest validation accuracy scores will be invited to discuss their implementation. 

### Description of the Setup Used For Generating the Dataset
In this project, we used the MNIST dataset to create two-dimensional objects. Briefly, the colors of handwritten digits (represented by numbers changing between 0 and 1) are converted into relative permittivity values (changing between 1 and 12). Then each of these objects is excited with electromagnetic waves twice. The first source excites the object from the left and the second source excites the object from the bottom. To guide the electromagnetic waves toward the object, we use waveguides, as shown with purple rectangles in Figure-1(a) below. 11 antennae are placed near the object and are shown with white dashed lines in the same figure. These antennas record the scattered electromagnetic waves, to be more precise, electric field intensity along the $z$-axis and magnetic field intensities along the $x$ and $y$ axes, respectively. The absolute values of these field intensities are shown in Figure-1 (b)-(d) for the setup shown in Figure-1 (a).
<img src="https://github.com/simsekergun/EMcat/blob/main/figures/main_figure.png?raw=true" width="600"/>

### Description of the Dataset
The entire dataset has 60,000 samples. In the input file (X.csv, which was divided into 6 csv files to reduce the size of each csv file to 25 MB or less, see the sample notebook to understand how X_Part1.csv, X_Part2.csv, etc. are merged to create the X), there are 6 columns: real part and imaginary parts of Ez, Hx, and Hy, respectively. There are 10 different main groups of objects (see Y.csv) obtained by converting handwritten digits (from 0 to 9). The goal is to identify the object category (Y) from X.

### A Sample Implementation
A sample notebook (example.ipynb) is provided as a sample, where two Dense layers (with sigmoid activation function) are followed by another Dense layer that uses a softmax activation function. Probably, this approach is not the best because it simply removes the correlation between real and imaginary parts. The validation accuracy of this sample approach is ~75%. Please see the figures below. We are looking forward to receiving much higher accuracies from you. 
<img src="https://github.com/simsekergun/EMcat/blob/main/figures/Acc_Loss.png?raw=true" width="600"/>
The confusion matrix of this implementation is as follows:

[2555,    8,   60,   38,   75,   45,   72,   21,   56,   26],
       [   2, 3168,   15,    8,   53,    9,   14,   10,   39,   11],
       [ 120,   20, 1844,  275,  250,   46,   70,  106,  147,   42],
       [  59,   17,  277, 2072,   86,  188,   16,   59,  218,   85],
       [  34,   26,  100,   29, 2201,   65,  177,   57,   35,  206],
       [  37,   17,   61,  216,   71, 2031,   76,   56,  137,   65],
       [  55,   22,   47,    3,  166,   94, 2570,    5,   53,    7],
       [  19,   28,   49,   26,  117,   27,   10, 2582,   63,  237],
       [  97,   56,  155,  146,  142,  136,  113,   95, 1658,  258],
       [  52,   12,   93,   74,  314,   48,   41,  228,  115, 2008]

### Important Note
This is an artificial dataset, never used before. Very high validation accuracies might not be possible!

### Rules
 -  You need to use 50% of the data for testing. Please use the following line to create the training and testing datasets
   
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.5, random_state=42)
 -  You can use any machine learning algorithm (neural networks, decision trees, random forests, etc.) but in the end, the precision can't be lower than 0.5 for any of the labels.
