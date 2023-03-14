# **New Zealand Predator Free 2050 Predator Control Data Standard - trap records short form**

## Overview

The data standards are designed to facilate the sharing of predator control data between systems. XML and JSON hierarchical formats are recommended as they are self describing and can be validated against data standard schemas.  

These formats work well for system-to-system integration and exchange, however, in practise very few organisations have the capability to make use of them currently.

Requests for data from Trap.NZ are almost exclusively asked for as either a map feed, or in CSV format.

Unfortunately neither of these formats lends itself well to a hierarchical structure - it would require multiple rows for each record and redundant, repeated data resulting in files unsuable for those wanting to import or analyse records, and increasing the file sizes significantly. 

For trapping records this is an example format that follows the Data Standards as closely as possible while providing a simple practical format for data exchange.   

Notes:  

* As with most systems currently, Trap.NZ does not yet record what bait is in the trap when you visit it ("bait on arrival") -  it records the bait that you load the trap with ("bait on departure").  You can extrapolate the bait on arrival from the bait in the previous record for that particular trap - but as that is an assumption we have left it up to the consumer to make it if they want to. If your system is capturing the bait at arrival you can add this as a field.
* Because there can be multiple baits and lures ("substances"), this field is formated as JSON.  This allows the inclusion of UUIDs etc, without needing to have repeated fields or rows.  Spreadsheet programs like Excel can parse JSON text.
* We've included the names of device models, species, etc. Having the names inline makes it easier to process as tabular data.

## Field descriptions

| Field | Notes |
|---|---|
| project_uuid | A unique ID for the trapping project |
| report_uuid | A unique ID for the report |
| report_type | The type of the report |
| date_start | The start date of the record |
| date_end | The end date of the record |
| device.device_uuid | A unique ID for the device (i.e. trap) |
| device.x_device_model_name | The name of the device model (e.g. DOC200). |
| device.device_status.arrival | The device status on arrival at the trap |
| device.device_status.condition | The device condition reported for the visit |
| device.device_status.strikes | The number of strikes reported for the visit |
| location.location_uuid | A unique ID for the device location |
| location.location_wkt | Location in WKT format WGS 84 projection (decimal lat/long) |
| substance | A JSON structure describing lures |
| species.species_uuid | A unique ID for the species caught |
| species.x_species_name | The name of the species caught |
| species.species_sex | The sex of the species caught (if recorded) |
| species.species_age | The age of the species caught (if recorded) |
| person_uuid | The UUID of the person who recorded this record |


