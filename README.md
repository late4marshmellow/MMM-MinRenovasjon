# MMM-MinRenovasjon (in development) a fork from MMM-TRV-WastePlan 
A MagicMirror2 module for showing the waste plan for your destination from Min Renovasjon.


##### Inspired by:
* https://github.com/VHamar/HomeyPro/blob/5d81fa00e7170302470b28be17f46f8b3a8303b1/Scripts/rest-getaddressinfo.js
* https://github.com/VHamar/HomeyPro/blob/5d81fa00e7170302470b28be17f46f8b3a8303b1/Scripts/rest-mrendatoer.js


## Dependencies
  * A [MagicMirror<sup>2</sup>](https://github.com/MichMich/MagicMirror) installation

## Installation

In your terminal, go to your MagicMirror's Module folder:
````
cd ~/MagicMirror/modules
````

Clone this repository and install the dependencies:
````
git clone https://github.com/late4marshmellow/MMM-TRV-WastePlan.git
````

Add the module to the modules array in the `config/config.js` file
and insert your own id. 

```
 {
    module: 'MMM-TRV-WastePlan',
    position: 'top_left',
    config: {
        id: 2694
    }
 },
```
**Note:** 
The id can be found at https://trv.no/wp-json/wasteplan/v1/bins/?s=Your+street+name

Example: https://trv.no/wp-json/wasteplan/v1/bins/?s=Lokes+veg

Returns:
```
[{"name":"Lokes veg","type":"BINS","plan":"P6","calendar":null,"deviations":null,"plans_by_year":{"2020":"P6","2021":"P6"},"id":2694}]
```
Use the number 2694

## Optional config
| **Option** | **Description** |
| --- | --- |
| `header` | Alternative header. Set as empty string to remove. Default: "Tømmeplan" |
| `numberOfWeeks` | Number of weeks to display. Default: 5 |
| `weekDay` | The number of the day in the week when the trash usually get picked up. Monday = 0, Tuesday = 1, Wednesday = 2, Thursday = 3, Friday = 4. Default: 3 |
| `blnNumberOfDays` | Display number of days until pickup. Default: true |
| `blnDate` | Display date for next pickup. Default: false |
| `dateFormat` | If blnDate is true, this date format will be used. Default: DD. MMM |
| `blnWeekNumber` | Display week number. Default: false |
| `blnLabel` | Display label. Default: false |
| `blnIcon` | Display the same icons as your trash bin uses. Default: true |
| `minWidth` | Minimum width on container in pixels. Default: 160 |
| `updateInterval` | Interval to update the next pickup dates, in milliseconds. Default: 6 hours |
| `hideNoPickup` | Hide no pickup entry. Default: false |


## Sample screenshot

Default:

![MMM-TRV-WastePlan module for MagicMirror](screenshots/default.png "MMM-TRV-WastePlan module for MagicMirror")


With label and date:
```
blnLabel: true,
blnNumberOfDays: false,
blnDate: true,
```
![MMM-TRV-WastePlan module for MagicMirror](screenshots/label_date.png "MMM-TRV-WastePlan module for MagicMirror")


Compact view (this week):
```
header: '',
numberOfWeeks: 1,
blnLabel: true,
blnNumberOfDays: false,
``` 
![MMM-TRV-WastePlan module for MagicMirror](screenshots/compact.png "MMM-TRV-WastePlan module for MagicMirror")
               
