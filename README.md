# homebridge-switcheroo-webos
[homebridge-switcheroo](https://badge.fury.io/js/homebridge-switcheroo) adapted for WebOS TVs


### HDMI input switcher (radio buttons)
Works like a switcher - only one input can ever be on at one time.

Define your `multiswitch` with whatever `name` you want to appear as the input title on Homekit controls. Then, the appropriate endpoint `path` to call. WebOS supports the following: HDMI_1, HDMI_2, HDMI_3, HDMI_4, COMP_1, AV_1...
The host is the local ip address of your TV. Mac is the mac address of your TV. To avoid issues here, it is recommended you assign the mac address of your TV to a static IP in your router configuration. 
```
{
  "accessory": "Switcheroo",
  "type": "multiswitch",
  "name": "HDMI Switcher",
  "host": "192.168.2.15",
  "mac": "48:8d:37:4d:a3:a9",
  "multiswitch": [
     { "name" : "Fibe TV"     , "path" : "HDMI_1" },
     { "name" : "Amazon Fire" , "path" : "HDMI_2" },
     { "name" : "Chromecast"  , "path" : "HDMI_3" },
     { "name" : "PS4"         , "path" : "HDMI_4" }
  ]
}
```


## Configuration Params

|        Parameter       |                                     Description                                     | Required |
| -----------------------| ----------------------------------------------------------------------------------- |:--------:|
| `name`                 | name of the accessory                                                               |     ✓    |
| `type`                 | `multiswitch`                                                                       |     ✓    |
| `host`                 | local ip of your WebOS Tv                                                           |     ✓    |
| `multiswitch`          | list of inputs for the multiswitch - `name` and WebOS input as `path`               |     ✓    |
| `manufacturer`         | will show in Home app description of this Homekit accessory, ex. 'LG'               |           |
| `model`                | will show in Home app description of this Homekit accessory, ex. 'HD 2000'          |           |



## Debug logging

Running `homebridge` manually will allow you to see the WebOS Switcheroo console logs.

![Switcheroo logging](https://github.com/chriszelazo/homebridge-switcheroo/raw/master/logging.png) 


## Tips

  - Run Homebridge on startup and have it restart if crashed, [read my notes](https://github.com/chriszelazo/Apartment-Homebridge-Setup#auto-restart-homebridge-after-a-crash)

