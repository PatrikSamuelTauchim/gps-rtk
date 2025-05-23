# gps-rtk

Mostly personal experiences and lessons learned on using LC29H(DA) and LC29H(BS) modules from Waveshare

## Lessons learned

##LC29H(BS)
* Default baudrate was 921600 and NOT 115200 - wasted whole day on dealing with gibberish in terminal and failing communication with QGNNS tool.
* IPEX 1 to SMA cable was faulty and had no continuity - another day wasted on dealing with "no signal" when module was moved to its final location
* RTKBase was not detecting its actual location from NMEA messages, showing only fixed position from the initial Survey-in.
  * It helps to enable additonal NMEA messages as described in https://github.com/Stefal/rtkbase/issues/425#issuecomment-2335137795
* Configuration of additional NMEA messages wont survive power-cycle and has to be repeated.
  * Turns out that parameters have to base save with $PAIR513*3D command and not $PQTMSAVEPAR*5A
 Chrony works with PPS

##LC29H(DA)
* Got to around +/-7cm accuracy with RTK base station 100km away, thats nice.
* I am unable to get Chrony to get time from PPS, same confing as BS
* GPSd wont use baud rate higher than 460800 - it just stisk 



