WeeWX driver for Wario ME11/12/13/15 station
Copyright 2014-2020 Frantisek Muller
For WeeWX version 4.x and higer (Python 3 support only)

Wanet driver for ME11/12/13/15 weather station by WANET
download data from a ME11/12/13/15 for use in weewx version 4 and higher
Web site for stations Wanet http://www.meteo-pocasi.cz/
 
  This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or any later version.
 
  This program is distributed in the hope that it will be useful, but WITHOUT  ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS  FOR A PARTICULAR PURPOSE.
 
  See http://www.gnu.org/licenses/
  

  
  To use this driver:
 
  1) copy this file to the weewx user directory
 
     cp wanet3.py /home/weewx/bin/user
     or, for .deb/.rpm installs:
     cp wanet3.py /usr/share/weewx/user

  2) configure weewx.conf
[Station]
     ...
     station_type = wanet4
 [Wanet4]
     driver = user.wanet4
     model = ME13
     binding = archive
     address = ADDRESS
     username = USERNAME
     password = PASSWORD
     page_cur = xml.xml
     page_arch = data.xml
     start = YYYY-MM-DD HH:MM
     resume = YYYY-MM-DD HH:MM

#    Remaping example
#    Can be added as an option instead internal driver map is used.
#     [[vid_map]]
#       temperature = outTemp

#  OWFS cooperated driver config settings example
#
# [OWFS]
#    interface = aaa.bbb.ccc.ddd:4304
#    driver = user.owfs
#    binding = archive
#    # deviation parameter is extra feature for managing data latency and deviation 
#    # betwen wanet and OWFS drivers
#    deviation = 180
#    [[sensor_type]]
#        outTemp = gauge
#    [[sensor_map]]
#        outTemp = /28.FF6284801603/temperature

  3) Manage extra value apparent temp.
    Because of apparent temperature in ME11/12/13/15, it is added as extra value.
    It would be add to units.py to the obs_group_dict or via users folder. 
