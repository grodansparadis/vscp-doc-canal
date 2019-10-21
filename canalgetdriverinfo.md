# const char *  CanalGetDriverInfo( void )

This call returns a documentation object in XML form of the configuration string for the driver. This string describes configuration settings and flags setting and can be used to guide users to enter the configuration data in an application which allows for this.

The returnd XML string have the following format

```xml
<?xml version = "1.0" encoding = "UTF-8" ?>

<!-- Version 2.0   2015-10-13   -->

<!-- Configuration strings are given as a semicolon separated list          -->
<!-- This list is described with and item tag for each configuration option -->
<!-- Items can be of different types, string, number                        -->
<config>
    <description format="text|html">`Description of the driver`<description>
	<level>1|2</level>   <!-- Is 1 for a level I driver and 2 for a level II driver -->
	<blocking>yes|no</blocking>
	<infourl>path to url with info about this item</infourl>
	<!-- pos is the position on the configuration line i.e.
	     item0;item1;item2;item3;item4.....
	-->
	<items>
	    <item pos="nn"  optional="true|false" type="string" description="Description about this item" infourl=path to url with info about this item"/>
	    <item pos="nn"  optional="true|false" type="number" min="min-value" max="max-value" infourl=path to url with info about this item" />
	    <item pos="nn"  optional="true|false" type="choice" infourl=path to url with info about this item" >
	        <choice value="0" description = "First choice" />
	        <choice value="0" description = "Second choice" />
	        <choice value="0" description = ".............." />
	        <choice value="0" description = "Last choice" />
	    </item>
	</items>

	<flags>
	    <bit pos="0" width="2" type="choice" description="" infourl="" >
	        <choice value="0" description="First choice." />
	        <choice value="1" description="Second choice." />
	        <choice value="2" description="Third choice." />
	        <choice value="3" description="Fourth choice." />
	    <bit>
	    <bit pos="2" width="1" type="bool" description="" infourl="" >
	    <bit pos="3" width="3" type="number" description="" infourl="" >
	</flags>
</config>
```

The configuration string locks like

>    pos0;pos1;pos2;pos3;pos4;....

that is items separated with semicolons. The **pos** attribute for the `<item>` tag is the ordinal for these. Always starting with base zero.

All items are sub strings when they are part of the configuration string but can be typed withing the `<item>` tag with the **type** attribute. Valid types are

 | Type | Description |
 | :----:  | ----------- |
 | **string**  | The should be interpreted as a sting                                                     |
 | **boolean** | The item should be interpreted as a boolean. Valid values are TRUE, FALSE, 0, 1          |
 | **int32**   | A signed integer. The attributes **max** and **min** can be used to specify limits       |
 | **uint32**  | An unsigned integer. The attributes **max** and **min** can be used to specify limits    |
 | **float**   | A floating point value. The attributes **max** and **min** can be used to specify limits |
 | **choice**  | Specify a list with choices that can be set                                              |

The **optional** attribute tells if an item is optional. If set on a pos all items on positions after it must also be optional.

The `<flags>` tag describe the bits in the flags value. It should have a `<bit>` tag for each bit in the flags that have a meaning. The **width** attribute can be used to tell the width for a configurable item and in that case the bits affected are the bits from the value in **pos** to **pos+width**. Width defaults to one as expected.

A real world example (the [can4vscp driver](./level1_driver_can4vscp.md) looks like this.

```xml
<?xml version = "1.0" encoding = "UTF-8" ?>
<config>
    <description>`CAN4VSCP standard serial driver</description>
    <level>1</level>
    <blocking>`yes`</blocking>
    <infourl>`https://www.grodansparadis.com/frankfurt/rs232/manual/doku.php?id=the_can4vscp_mode</infourl>
    <items>
        <item pos="0"
                type="string"
                description="Serial port (COM1, COM2...)"
                infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#parameter_string" />
        <item pos="1"
                type="choice"
                optional="true"
                description="Baudrate to use for communication with the adapter.Default is 115200 baud. "
                infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#parameter_string" >
            <choice value="0" description = "115200 baud" />
            <choice value="1" description = "128000 baud" />
            <choice value="3" description = "230400 baud" />
            <choice value="4" description = "256000 baud" />
            <choice value="5" description = "460800 baud" />
            <choice value="6" description = "500000 baud" />
            <choice value="7" description = "625000 baud" />
            <choice value="8" description = "921600 baud" />
            <choice value="9" description = "1000000 baud" />
            <choice value="0" description = "9600 baud" />
            <choice value="10" description = "19200 baud" />
            <choice value="11" description = "38400 baud" />
            <choice value="12" description = "57600 baud" />
        </item>
    </items>

    <flags>
        <bit pos="0" width="2" type="choice" description="Select the mode the device should be opened in. The normal mode opens the interface for receive and transmit. The listen mode only listen on traffic on the bus. Loopback just connect the receive and transmit lines without sending anything on the bus. The manual describes the modes in detail." infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#flags" >
            <choice value="0" description="Open CAN4VSCP interface in normal mode." />
            <choice value="1" description="Open CAN4VSCP interface in listen mode." />
            <choice value="2" description="Open CAN4VSCP interface in loopback mode." />
        </bit>
        <bit pos="2" width="1" type="bool" description="If this flag is set the driver will not switch to VSCP mode. This means it already must be in VSCP mode. The advantage is that the open operation will be faster." infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#flags" />
        <bit pos="3" width="1" type="bool" description="If this flag is set the driver will wait for an ACK from the physical device for every sent frame. This will slow down sending but make transmission very secure." infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#flags" />
        <bit pos="4" width="1" type="bool" description="If this flag is set it enable timestamps in hardware meaning the timestamp will be written by the hardware instead of by the driver. The disadvantage is that it consumes bandwidth." infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#flags" />
        <bit pos="5" width="1" type="bool" description="If this flag is set enable hardware handshake. Recommended for lower baudrates to prevent buffer overflows." infourl="http://www.vscp.org/docs/vscpd/doku.php?id=level1_driver_can4vscp#flags" />
    </flags>
</config>
```

## Returns

Pointer to a configuration string or NULL if no configuration string is available.


{% include "./bottom_copyright.md" %}