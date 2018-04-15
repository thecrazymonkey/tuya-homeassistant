# tuya-homeassistant

**THIS WILL ONLY WORK FOR SWITCHES. WILL NOT WORK WITH DIMMERS.**

This is a simple platform to control **SOME** switch devices that use the Tuya cloud for control.

It uses the pytuya library (https://github.com/clach04/python-tuya) to directly control the switch device. (No need to install as Home Assistant automatically installs it.)

Most switch devices that use the Tuya cloud should work. If port 6668 is open on the switch device then it will work.

switch id is if the switch device has multiple switches, the switch number.

See here for how to find localKey and devId: http://seandev.org/tuyainst

To use, copy tuya.py to "<home assistant config dir>/custom_components/switch" and add config below to configuration.yaml

Config Fields:
```
switch:
  - platform: tuya
    name: //switch name
    host: //ip of device
    local_key: //localKey
    device_id: //devId
    id: //switch id. Remove line if only one switch
```

Example:
```
switch:
  - platform: tuya
    name: Switch
    host: xxx.xxx.xxx.xxx
    local_key: xxxxxxxxxxxxxxxx
    device_id: xxxxxxxxxxxxxxxxxxxx
    id: 3
```

Multiple switches on a single device:
```
switch:
  - platform: tuya
    host: xxx.xxx.xxx.xxx
    local_key: xxxxxxxxxxxxxxxx
    device_id: xxxxxxxxxxxxxxxxxxxx
    switches:
      switch1:
        friendly_name: Switch 1
        id: 1
      switch2:
        friendly_name: Switch 2
        id: 2
      switch3:
        friendly_name: Switch 3
        id: 3
      switch4:
        friendly_name: Switch 4
        id: 4
```
