# Creating the GRS simulation

We must start with data with higher resolution than the one JWST will have. This is a hard task. Or the spatial resolution is high, or the spectral resolution is good enough to be better than the one MIRI or NIRspec will have. Because of that, I decided to start with an image from GEMINI:

https://noirlab.edu/public/images/noirlab2116a/

After that I divide the brightness in 5 regions, and create for every region a synthetic spectra with different temperature and abundance profiles. After that we give the extra spectral dimension to our 5 region-image. For every region one of the 5 spectra. By that we create a 3D cube which can be used as aun input for MIRIsim. We must save it as a fits file and give it the structure specified by the sTSCI (if you have questions, please ask).

After creating the detImage file, we must make it go through the pipeline process as shown here:

https://jwst-docs.stsci.edu/jwst-science-calibration-pipeline-overview

We get then a image with the SNR expected (more or less), the spatial resolution of the MRS and the spectral resolution for the MRS mode. In our case, our spectra will be saturated around 11-12 microns, which means that we will only need the channels 1 and 2.
