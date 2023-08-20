# toy data: simulated data to test configuaration files

## Description

This is not a real sensor, but a data source providing simulated data to test, debug and
develop modules for the *PhyPiDAQ* package. 
The code in the module *phypidaq.ToyDataConfig* provides artificial data. As of now, 
the only configuration foreseen is the number of channels, as shown in the *yaml* configuration below:
```
# "device" config for ToyDataConfig.py 
DAQModule: ToyDataConfig
NChannels: 2
```

Based on these input data, it easy to try out different display and storage options.
The complete example of options is shown in the *.daq* file below. 
This configuration can be used from the graphical interface, or started from the
command line via

  > run_phypi.py ToaData.daq

```
# Configuration Options for PhyPiDAQ 

# -- device configuration files 
DeviceFile: ToyData.yaml

# -- channel-specific information
ChanLabels: ['Rnd', 'Rnd']             # names for channels 
ChanUnits: ['', '']                              # units for channels 
ChanColors: [darkblue, sienna]   # channel colours in display

# calibration of channel values
#  - null    or  - <factor> or  - [ [ <true values> ], [ <raw values> ] ]
ChanCalib: 
  - 1.                           # chan0: simple calibration factor
  - [ [0.,1.], [0., 1.] ]   # chan1: interpolation: [true]([<raw>] )

# -- apply formulae to calibrated channel values
ChanFormula:
  - sqrt(c0*c1)        # chan0 formula
  - 0.5*c0/c1          # chan1 formula
  - c0                 # chan2 reassign chan0
  - c1                 # chan3 reassign chan1

# -- set channel limits
ChanLimits: 
 - [0., 1.]   # chan 0
 - [0., 1.]   # chan 1
 - [0., 1.]   # chan 2
 - [0., 1.]   # chan 3
  
# -- define and configure display module 
# DisplayModule: DataLogger
DisplayModule: DataGraphs  # text, bar-graph, history and xy-view
Title: Demo
NHistoryPoints: 100
Interval: 0.1                    # logging interval         
XYmode:     true              # enable/disable XY-display
xyPlots:
  - [0,1]
  - [0,3]
  - [2,0]
  - [2,1]
  - [3,1]
  - [3,2]

# name of output file
#DataFile:   testfile.csv  # file name for output file,  default is null 
#CSVseparator: ';'

#bufferData: null    # file name to track latest data
                                   #  default PhyPiData.dat, null to switch off 
```

This *.daq* file demonstrates all of the features presently foreseen.
The key *ChanCalib* can be used to define simple calibrations for some or all
defined channels (in this case they are all different versions of 1, i. e. no effect).

From the two raw input channels, four channels are are created by applying formulae,
defined  in *Python* syntax via the key *ChanFormula*.  
For these channels, names, units and channel ranges are 
defined with the keys *ChanLabels*, *ChanUnits* and *ChanLimits*.

The key *xyPlots* is used to determine which 2d-graphs are shown in the
xy-display. 

Use this example to try out different options to process raw input data by applying 
calibrations and formula, and how to display them. 
 
**module**:   phypidaq/ToyDataConfig.py  
**sensor config**: config/ToyData.yaml  
**examples**:  examples/ToyData.daq


## Requirements

none 
