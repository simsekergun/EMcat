# EMcat

### Description of the Setup Used For Generating the Dataset
In this project, we used the MNIST dataset to create two-dimensional objects. Briefly, the colors of handwritten digits (represented by numbers changing between 0 and 1) are converted into relative permittivity values (changing between 1 and 12). Then each of these objects is excited with electromagnetic waves twice. The first source excites the object from the left and the second source excites the object from the bottom. To guide the electromagnetic waves toward the object, we use waveguides, as shown with purple rectangles in Figure-1(a) below. 11 antennae are placed near the object and are shown with white dashed lines in the same figure. These antennas record the scattered electromagnetic waves, to be more precise, electric field intensity along the $z$-axis and magnetic field intensities along the $x$ and $y$ axes, respectively. The absolute values of these field intensities are shown in Figure-1 (b)-(d) for the setup shown in Figure-1 (a).
<img src="https://github.com/simsekergun/EMcat/blob/main/figures/main_figure.png?raw=true" width="600"/>

### Description of the Dataset
The entire dataset has 10,000 samples. In the training file (X.csv), there are 6 columns: real part and imaginary parts of Ez, Hx, and Hy, respectively. There are 10 different main groups of objects (see Y.csv) obtained by converting handwritten digits (from 0 to 9). The goal is to identify the object category (Y) from X.

### A Sample Implementation
A sample notebook is provided as a sample, where three Dense layers are followed by a softmax activation function. Probably, this approach is not the best because it simply removes the correlation between real and imaginary parts. The validation accuracy of this sample approach is ~65%. We are looking forward to receiving much higher accuracies from you. 

### Important Note
This is an artificial dataset, never used before. Very high validation accuracies might not be possible!
