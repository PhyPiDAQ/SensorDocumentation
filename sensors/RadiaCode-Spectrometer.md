# Radiacode Radiation Detector and Spectrometer

## Description

The [RadiaCode Radiation Detector and Spectrometer](https://radiacode.com) class of devices use scintillating crystals with a SiPM sensor with temperature correction to measure the deposited  energies of gamma rays from radioactive decays. Data is exported via USB and Bluetooth. An Android App as well as a windows program exist in addition to a [python library](https://github.com/cdump/radiacode) to read-out, display and analyze the sensor data.  
The RadiaCode RC-101, 102 and 103, and 110  are equipped with CsJ(Tl) scintillating crystals, while the 103G uses a GAGG(Ce) crystal of higher density. The crystal volume
is 1cm³ for the RC-10x types, while the RC-110 is equipped with a more sensitive 2.74cm³ large detection crystal. 
 
Rates up to several kHz of incident gamma rates are supported and allow laboratory-quality energy spectra to be recorded. The device directly exports the recorded frequencies in each one of the 1024 channels of the pulse-height analyzer. 

The PhyPiDAQ  implementation only uses the full spectrum read out from the
device to calculate the gamma rate and the energy deposit in the crystal, 
in units of Hz and µGy/h, respectively. 

**module:**  phypidaq/RC10xConfig.py  
**sensor config:**  config/RC10x.yaml  
**examples**:  examples/config_files/RC102_GammaDose.daq, RC102_GammaSpectrum.daq


## Requirements

The sensor needs the library *radiacode*, which supports read-out via USB and bluetooth.  

## Experience

The quality of the spectra provided by the sensor is comparable to that obtained with
typical equipment in a students' lab, i.e. a NaJ(Tl) crystal with photo-multiplier readout. However, the RadiaCode devices are much smaller, do not need any external high-voltage and run for several days on the built-in Li-Ion battery. Rate and dose histories as well as the accumulated spectrum are stored independently of any external readout in the 32 MB internal  memory. 

Usage and handling of the devices are very easy also for high-school students and undergraduates. The small size and the independent operation on battery open the
opportunity for experiments not easily possible with classical equipment, e.g. long-term  measurements of environmental radioactivity.

All of the typical physics lab measurements like the analysis of the energy spectra of radioactive probes, energy calibration and resolution measurements are also possible with this device.

The most convincing argument, however, is the price:  approx. 200,-€ for the RC-102 or 300,-€ for the RC-110 compared to several thousand euro for a NaJ(Tl)-Crystal, a photo-multiplier with high-voltage supply and a Multi-Channel Pulseheight Analyser (MCPA) plus a computer for its readout.  
