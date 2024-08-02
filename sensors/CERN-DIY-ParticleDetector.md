# The CERN DIY particle detector 


## Description

The [CERN DIY_particle_detector](https://github.com/ozel/DIY_particle_detector)
is rather simple, cheap and easy to operate particle detector based on four silicon 
PIN photo-diodes (PBW34).  Environmental radiation corresponding to a dose
of 0.1 µSv/h leads to signal rates of 2 pulses per minute. 

The analog output of the detector with a two-stage amplification with a 
dual op-amp with high band-width provides a very robust and easy to 
handle design that produces analog output signals in the range of 
several hundred µs with a pulse width of about  100 µs. These signals
can easily be digitized with a standard PC soundcard.  

## Requirements

The detector only needs very minimalistic code to directly read data from the sound card, as 
implemented in the module *phypidaq.soundcardOsci*. The stream from the sound card
is read in small portions, which are analyzed in order to find exceptionally large signals. 
The module also contains an animated waveform display to directly visualize the raw 
recorded signals or only those samplings containing triggered signal pulses. 

An application example is *phypidaq/examples/oscilloscope/soundcardOsci.py*.

A script directly tailored to be used with the CERN DIY particle detector is 
*phypidaq/examples/scGammaDetector.py*. This script uses the module *phypidaq.DisplayPoissonEvent*
to visualize every occurrence of a large signal and also the associated wave form data around the
trigger point. A rate history is also shown. The script also offers the possibility to store the event
times in a file for off-line analysis, or to only visualize a sub-set of triggering pulses if the rate
is very high. 

![Fig.1: Graphical display showing data acquisition with a small sample of pitchblende ore.](PoissonEventDisplay.png)

Data of this kind offer a unique opportunity to study random Poisson processes.  There is a script
*phypidaq/examples/poissonFlash* to generate, visualize and store data of a simulated Poisson process. 

*phypidaq/examples/poissonLED* produces random flashes of a LED. A photodiode exposed to the light
of the LED will produce signals analogous to  a detector for gamma rays.  


## Experience

The CERN DIY particle detector  is a very robust and easy-to-build design. All needed components, including the 
printed-circuit board, can be ordered commercially at a price under 20,-€. Building the detector can be  easily 
accomplished by high-school students or teachers. Signals can be detected with any kind of sound-card oscilloscope.

Using *PhyPiDAQ* modules offers an easy way to discriminate signal from background pulses and to perform an
off-line analysis of the recorded data.



