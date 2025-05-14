The test dataset is a stacked data from WiRE Raman spectroscopy mapping data collection using 785/633 grating. 
This will generate an output with the length of 1015 per Raman spectrum in txt file.
In the txt file, spectrum is stacked in the 4th column. (You can still use the code with the input of single measurement).
input the intensity column as data and run linearbaseline.m;
Alternatively, read the spectrum data and x data in the txt file:

txt = importdata('test dataset.txt');
data = txt.data(:,4);
xx = txt.data(1:1015,3);

