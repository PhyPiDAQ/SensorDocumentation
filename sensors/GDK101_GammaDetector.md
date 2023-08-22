# GDK101 Gamma Radiation Sensor Module

## Description


The [GDK101 Gamma Radiation Sensor Module](http://allsmartlab.com/eng/294-2)
is a solid-state detector based on 10 PIN photodiodes as detection medium.
A metal shield suppresses α and β radiation. The detection efficiency of
the thin active layer in the photodiodes is small, but still sufficient
to reliably detect 𝛾 rays, albeit with a detection efficiency of only a few %. 
The device output consists of an analogue output after the pre-amplifier stage, 
and UART  and 3.3 V-compatible I²C interfaces controlled by a MCU, which converts 
the rate of detected pulses above a fixed threshold to dose rates in the range 
of 0.01 µSv/h  - 200  µSv/h. A dose of 1 µSv/h corresponds to 12 counts per minute. 

The sensor delivers updated data every minute. A second output channel provides 
a sliding average over 10 minutes, which is an adequate measurement time to
obtain meaningful results. Note that at a typical dose of environmental radioactivity
of 0.1 µSv/h corresponds to only 12 counts in 10 minutes, which implies a statistical
precision of about 30 %.

**module:**  phypidaq/GDK101Config.py  
**sensor config:**  config/GDK101.yaml   
**examples**:  examples/config_files/GDK101_GammaDose.daq, GDK101_GammaRate.daq


## Requirements

The sensor only needs very minimalistic code to directly read data from the I²C bus and is implemented in the module *phypidaq.GDK101Config*. The example configuration *GDK101_GammaRate.daq* can be used to convert the sensor outputs back to count rate
by means of the *PhyPiDAQ* formula feature. 

## Experience

The GDK101 is a very robust and easy-to-use device. Rather long measurement times of
multiples of 10 min are necessary to obtain acceptable precision. A measurement of Radon
decay products collected on the surface of a charged balloon is easily possible, and the
decrease as a function of time of the count rate can be convincingly demonstrated.  


