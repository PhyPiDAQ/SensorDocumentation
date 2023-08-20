# Picoscpe series of USB oscilloscopes 

## Description

 USB  oscilloscopes not only provide visual representations of input data, but are also very useful as front-end devices for data acquisition. 
 
By analyzing full waveform, an average over a large number of measurements reduces
signal noise; by choosing a sampling interval of 20 ms, noise induced by the 50 Hz 
frequency of the power grid can completely averaged out. 
A second useful application is the determination of the true effective voltage of an alternating signal - at true RMS voltmeter. 

The interface to *PhyPiDAQ* is provided by the code in the package 
[picoDAQ](https://github.com/GuenterQuast/picoDAQ).


As an example, the the configuration file *NoiseMeter.daq*  to measure the effective 
voltage of a sound signal, i. e. a signal proportional to the recorded  acoustic noise or 
sound level, is shown here: 

```
# configuration of a Picoscope USB oscilloscope for PhyPiDAQ 
#    display RMS of sound signal

# device configuration files 
DeviceFile: PSConfig_sound.yaml         
#DeviceFile: PSConfig2000A_sound.yaml         

DisplayModule: DataLogger
Title: Noisemeter

Interval: 0.05                       # logging interval         
ChanLabels: [Volt]             # names an units for channels 

# overwrite Channel Limits of Device 
ChanLimits: 
- [0., 2.5]  # scope at 5V, eff. Voltage is smaller
```

The oscilloscope also needs a configuration file to specify the number of channels, 
channel ranges, trigger conditions, sampling interval and number of samples, 
as illustrated here (configuration file *PSConfig.yaml)*:
```
# example of a configuration file for PicoScope 2000 Series

DAQModule: PSConfig         
#PSmodel: '2000'      # PS model 220xA
PSmodel: '2000a'     # PS model 2x0xB

# channel configuration 
picoChannels: [A]
ChanRanges: [5.]  # for microphone with amplifier
ChanModes: [AC]
##ChanOffsets: [-0.049] # !!! not wanted here, and not possible for A series

# sampling
sampleTime: 2.0E-02
Nsamples: 200

# trigger
trgActive: false  # set to true to activate
trgChan: A
trgThr: 0.
trgTyp: Rising
#trgTO: 4  # set short time-out for A series
pretrig: 0.05  # !!! not possible for A series

# signal generator 
# frqSG: 100.E+3 # put 0. do disable
frqSG: 0. 

# special flags for PhyPiDAQ
ChanAverages: ['rms']  # ['mean'] or ['rms']
```

The *Python* script *runOsci.py* provides provides a simple waveform display. 

**module**:   phypidaq/PSConfig.py  
**sensor config**: config/PSConfig.yaml  
**examples**: examples/config_files/NoiseMeter.daq, examples/osilloscope/runOsci.py

## Requirements

Picotech USB oscilloscopes are supported by the package [picoDAQ](https://github.com/GuenterQuast/picoDAQ).


## Experience

With the software provided as part of the *PhyPiDAQ* package USB oscilloscopes can be used as multi-channel voltmeters. 

By choosing appropriate trigger conditions, not only periodic signals, but also signals from  
singular events over a large range of time scales can be detected and quantified.  For such applications, however, it is advisable to directly use the scripts provided by the package  
*picoDAQ*.
