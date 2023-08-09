# VL53L0X Time-of-Floght Distance Sensor

## Description

This sensor measures distances of objects from the sensor by means of the time-of-flight of the a 940 nm class-1 infrared laser reflected from the object's surface (LIDAR technology). The measurement range is up to 2 m for the VL53L0x and up to 4 m for the VL53L1x. The sensors provide an I²C interface with 3.3 V compatibility.  The sensor has one single channel providing the measured distance in mm. The VL53L1x supports a repetition rate of up to 50 measurements per second in short-range mode up to 1.3 m. Repeatability errors are  below 1 mm at medium distances and and a measurement time of 0.2 s. 

This sensor is well sited for position measurements in experiments of classical mechanics.
Owing to the high repetition rate, velocities can be determined numerically.  Successful
applications have been demonstrated for measurements of  motion in one dimension, to demonstrate  Newton’s second law and for studies of oscillations 
( see [link](https://mint.hw-schule.de/index.php/mint-projekte/phypidaq-international?view=article&id=54) ).

**module**:   phypidaq/VL53LxConfig.py  
**sensor config**: config/VL53LxConfig.yaml  
**examples**:  modified version of  *default.daq*


## Requirements

The VL53L0/1x sensors are supported by the Adafruit-libraries   *adafruit_vl53l0x*
and *adafruit_vl53l1x*.
