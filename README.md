### PV Production Tracker for Homey  

**Warning:** This update will remove your current graph data. The data in Insights is now pushed using device capabilities. Homey doesn't support custom capabilities yet, and the existing capabilities do not really suit inverters. Therefore, energy will be shown as 'power usage' and is shown in kWh. When custom capabilities are supported, I will create suitable Insights titles and revert production to Wh (which creates nicer graphs).

Let Homey monitor your solar panels. This app allows you to view production statistics using Insights, and lets you create triggers based on the current power output. For example, enable your car charger when your panels are producing!

#### Supported data sources
* PVOutput
* SolarEdge
* Enphase

#### Release notes
* 1.2.0 - Added support for SolarEdge inverters and fixed bugs
* 1.1.0 - Added experimental support for Enphase inverters
* 1.0.0 - First release

#### To do
* Screensavers showing daily production
* Speech input/output
* Improve inverter support

---
#### Adding an inverter
##### PVOutput
Get your System ID and read only API key from PVOutput. Add the inverter as a device in the Homey devices panel, and give the inverter a name (this will be used as the name for the device).

![](http://i.imgur.com/REJxrUg.png)

##### SolarEdge
Get your System ID and API key from SolarEdge. Add the inverter as a device in the Homey devices panel, and give the inverter a name (this will be used as the name for the device).

##### Enphase
Create an account at https://developer.enphase.com/. Authorize your API account to access your system (instructions after logging in). Please let me know if everything works for you, Enphase support has only been tested on a demo system.

---
#### Current production data

Homey shows your inverter as a sensor. This app currently supports two metrics: current power and current energy production (reset daily). It uses Homey's built-in capabilities because custom capabilities are not fully working yet. Therefore, it reports current energy production as power usage. This will be solved in a later version.

![](http://i.imgur.com/Ozscz9k.png)

---
#### Flow 

Your inverter acts as a sensor for Homey. This allows you to use logic on your production data. Here is an example:

![](http://i.imgur.com/HyLuawu.png)

---
#### Insights 

![](http://i.imgur.com/7VZiddt.png)

Homey retrieves data from PVOutput every minute, but only logs new data. You can add more than one inverter, and every inverter will be logged in a separate graph.
