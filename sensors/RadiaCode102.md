# Radiacode 102 Radiation Detectector and Spectrometer

## Description

The [Radiation Detector and Spectrometer RadiaCode 102](https://radiacode.com) 
uses a 1cm³ CsJ(Tl) crystal with a SiPM sensor with temperature correction to measure the deposited 
energies of gamma rays from radioactive decays.
Data is exported from the device via USB and Bluetooth. An Android App as well as a windows program
exist in addition to a [python library](https://github.com/cdump/radiacode) to display and analyze the sensor data.  

Rates up to several kHz of indident gamma rates are supported and and allow laboratroy-quality energy spectra to be recorded. The sensor directly exports the frequencies recorded in each 
one of the 1024 channels of the pulse-height analyzer. 

The PhyPiDAQ  implementaion only uses the full spectrum read out from the
device to calculate the gamma rate and the energy deposit in the crystal, in units of Hz and
 µGy/h, respectively. 

**module:**  phypidaq/RC10xConfig.py  
**sensor config:**  config/RC10x.yaml  
**examples**:  examples/config_files/RC102_GammaDose.daq, RC102_GammaSpectrum.daq


## Requirements

The sensor needs the library *radiacode*; only the USB connection has been tested so far. 

## Experience

The quality of the spectra provided by the sensor is comparable to that obtained with typical
equipment  in a students' lab, i.e. a NaJ(Tl) crystal with photo-multiplier readout.
However, the RadiaCode 102 is much smaller, does not need any high-voltage and runs for
several days on the built-in Li-Ion battery.  Rate and dose histories as well as the accumulated
spectrum are stored independently of any external readout in the 32 MB internal  memory. 

Usage and handling of the device are very easy also for high-school students and undergraduates.  The small size and the independent operation on battery open the opportunity
for experiments not easily possible with classical equipment, e.g. long-term  measurements of 
environmental radioactivity.

All of the typical physics lab measurements like the analysis of the energy spectra of radioactive
probes, energy calibration and resolution measurements are also possible with this device.

The most convincing argument, however, is the price:  approx. 300,-€ for the RadiaCode 102
compared to several thousand euro for a NaJ(Tl)-Crystal, a photo-multiplier with high-voltage
supply and a Multi-Channel Pulseheight Analyser (MCPA) plus a computer for its readout.  
