# Convolutional Neural Networks for X-Ray Crystallography
Series of notebooks used to create a large dataset of 10000+ crystals, as well as training and testing a complicated model with the dataset.

When recording diffraction data for crystallography, one only obtains the amplitude of the reciprocal space of a given object on the detector. However, in order to obtain all of the information of the object, one needs the amplitude and phase. Phase retrieval, an ubiquitious problem in several fields, is the process of post-processing data to estimate the phase of each pixel in an image. Recently, there have been many efforts to employ machine learning methodlogies to phase retrieval problems. In this presentation, convolutional neural networks will be employed on this complex problem for use in X-ray diffraction experiments.

## The Data

The dataset was made by using Crystallographic Information Files (.cifs) and calculating all of the complex structure factors associated with it for a 10 keV X-ray source.  The conversion from the crystallographic file to X-ray diffrac-tion structure factors was done using a python library named Dan’s Diffraction. We did this for 16 crystals where we shifted the crystals by a random amount given by a normal distribution with a mean of zero and a standard deviation of one twentieth the lattice constant on the a-axis to act as a distortion to the structure factors. 

![Unet loss](./images/reciprocal_space_structure_factor_example.png)

Figure 1: Structure factors for a Ni crystal plotted in 3D based on HKL space.

![structure factors plotted](./images/Shifted_Nickel_Structure_Factors.JPG)

Figure 2: Structure factors for a Ni Crystal tiled in 2D before perturbing the crystal (a) and after perturbing the crystal (b).

## Modeling and Analysis

### Loss Function

The primary numerical metric is the loss over a given dataset because it reveals how close the phases are for a given output. The reconstruction of the charge density in the crystal was used as a qualitative metric.

![Unet loss](./images/loss_function.png)

Figure 3: Loss function that was used to evaluate baseline methdos as well as U-net model.

### Baseline Methods

Since applying neural networks to the phase retrieval problem in this particular way is novel, three baseline methods were analyzed. These three are linear regression, a three layer fully connected neural network, and a three layer 3D convolutional neural network. 


![Unet loss](./images/Unet_loss_methods_section_v2.png)
testing change

testing another change
