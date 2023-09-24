# EMcat

![(a) Permittivity map of the setup. Absolute value of (a) electric field intensity along the z-axis, (b) and (c) magnetic field intensity along the x and y-axes, respectively.](https://github.com/simsekergun/EMcat/blob/main/figures/main_figure.png?raw=true)

<img src="https://github.com/simsekergun/EMcat/blob/main/figures/main_figure.png?raw=true" width="400"/>

### Description of the Dataset
The entire dataset has 10,000 samples. Half of them is reserved for training and the other half is reserved for testing. 
Since the input (X) is complex, it is saved in two separate CSV files. XTrainReal.csv and XTrainImag.csv have the real and imaginary parts of the X values, i.e., X = XTrainReal + j*XTrainImag, where j is sqrt of -1. These are the electric field intensities measured at 300 locations by tiny antennas placed uniformly far enough from the object, where XTrainReal is the real part of the electric field intensity and XTrainImag is the imaginary part. 

There are 10 different main groups of objects (see YTrain.csv). In each group, we have objects that are very similar to each other but not the same (you can think that X represents the electromagnetic waves scattered from 10 different animals).

The goal is to identify the object category (Y) from X.

### A Sample Implementation
A sample notebook is provided as a sample, where X is simply the concatenated version of the real and imaginary parts, since size(XTrain) is 5000 by 600, i.e. there are 5000 rows (samples) and 600 columns (features). This approach is definitely not the best approach because it simply removes the correlation between XTrainReal[,i] and XTrainImag[,i], where i = 1, 2, ...,5000. Also note that these antennas are placed uniformly on a straight line, so measurements taken at neighboring antennas could be close to each other and this continuity might be helpful to improve accuracy (hint hint). The validation accuracy of this sample approach is ~30%. We are looking forward to receiving much higher accuracies from you. 

### Important Note
This is an artificial dataset, never used before. Very high validation accuracies might not be possible!
