# p300 Speller Project 

This project has been developed during the Neuroengineering course at Politecnico di Milano. The data comes from the BCI competition III, Dataset II based on two subjects. The data is in .mat format. The aim of the project was to investigate if a subset of electrodes could still have acceptable accuracy in the detection of P300 events. 

## Abstract
In the preprocessing step, we first divided the signal in windows of 667ms, then filtered the signal using an 8th order bandpass Butterworth filter (with cutoff frequencies of 0.1 and 20), and lastly we extracted the average p300 and no p300 epochs, in order to visualize the pattern. 

The model that we implemented for our project recalls the one used by Liu et al., which is a 6-layers CNN (known as batch normalization neural network, BN3). In particular, the batch normalization layers help to reduce the internal covariate shift in neural network training, and the first layer performs the channel dimensionality reduction (from 64 to 16) by means of a 1D convolution.

Beyond Liu’s neural network, we tried to implement also a long short term memory/CNN network, and a CNN, (that although have different approaches wrt Liu), and we observed that the BN3 showed to achieve the best overall performance.  The accuracy of the model reaches 0.77 for subject B and 0.7 for subject A; we also validated what Liu said about the fact that after 6 epochs the model overfits, and we did it by means of early stopping.  
Regarding the character recognition of the speller, that is achieved by accumulating the detection of P300 signals and by taking the intersection of the row and column with most detections as the intent character, we reached an accuracy of 92% for both subjects.

The electrode subset analysis, which was our group specific task, allows to reduce the computational and set-up time. In the spatial activation graph, we can see the difference between p300 and no p300 events, with the p300 event occurring 300-400ms after the intensification of the row/column where the desired letter is present. 
In order to analyze the electrode importance, we used the Leave One Feature Out method, which calculates the importance of a channel based on accuracy by iteratively removing a channel from the set. We were able to confirm, by comparing the data with other papers in the literature, that the parietal zone, and in particular the occipital and parietal electrodes, were the most activated ones. 

## Acknowledgments
The project was developed in a team of 5 MSc students: Veronika Guleva, Elena Puddu, Cristian Drudi, Alessandro Gozzi and I, Stefano Magni. Special thanks goes to the professor Cerveri and Pedrocchi who proposed this very interesting topic and our tutor Davide Marzorati who helped us in the most challenging parts. 

For any issue or curiosity about the code do not hesitate to contact us. 

