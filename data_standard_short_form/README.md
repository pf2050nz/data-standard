# **New Zealand Predator Free 2050 Predator Control Data Standard - trap.nz short form**

## Overview

The data standards are designed to facilate the sharing of predator control data between systems. XML and JSON hierarchical formats are recommended as they are self describing and can be validated against data standard schemas.  

These formats work well for system-to-system integration and exchange, however, in practise very few organisations have the capability to make use of them yet.

Requests for data from Trap.NZ are almost exclusively asked for as either a map feed, or in CSV format.

Unfortunately neither of these formats lends itself well to a hierarchical structure - it would require multiple rows for each record and redundant, repeated data resulting in files unsuable for those wanting to import or analyse records, and increasing the file sizes significantly. 

For trapping records this is a suggested format that follows the Data Standards as closely as possible as well as providing a simple practical format for data exchange.   

Some notes:  

* As with most systems currently, Trap.NZ does not record what bait is in the trap when you visit it ("bait on arrival") -  just the bait that you load the trap with ("bait on departure").  You can extrapolate the bait on arrival from the bait in the previous record for that particular trap - but as that is an assumption we have left it up to the consumer to make it if they want to. If your system is capturing the bait at arrival you can add this as a field.
* Because there can be multiple baits and lures ("substances"), this field is formated as JSON.  This allows the inclusion of UUIDs etc, without needing to have repeated fields or rows.  Spreadsheet programs like Excel can parse JSON text.


## Field descriptions

|   |   |   |   |   |
|---|---|---|---|---|
|   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |

