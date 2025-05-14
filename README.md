The test dataset is a stacked dataset from WiRE Raman spectroscopy mapping data collection using 1200l/mm (780/633) grating. 
This will generate an output with the length of 1015 per Raman spectrum in a .txt file.
In the .txt file, the spectrum is stacked in the 4th column(You can still use this code for a single spectrum acquisition).
Input the intensity column as data and run linearbaseline.m. Alternatively, read the spectrum data and x data in the .txt file by

txt = importdata('test dataset.txt');
data = txt.data(:,4);
xx = txt.data(1:1015,3);

Then run linearbaseline.m. The code is specific to the data length. You will need to change parameters in the code if applying to other lengths. The code can process multiple spectra at once. The processed data are stored in result1.mat. Here is an example of computing the least squares solution for decomposition by linearfit.m. Before that, you should ensure the CVX function is downloaded and installed in your MATLAB (https://cvxr.com/cvx/doc/install.html). Run linearfit.m, and the fitting results are stored in params.mat as column per spectrum.  
