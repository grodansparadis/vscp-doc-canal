# unsigned long CanalGetLevel( long handle  )

# Params

handle – Handle for open physical/logical interface.


# Returns

Returns the canal level this interface can handle.  An error is indicated by a zero return value. At the moment the following levels are defined

 | CANAL_LEVEL_STANDARD   | A standard CANAL driver as of this specification.  |
 | --------------------   | -------------------------------------------------- |
 | CANAL_LEVEL_USES_TCPIP | This driver does not respond to any of the methods, even if they must be implemented. The driver will instead use the TCP/IP interface of the VSCP daemon for its data transfer. This driver type is called a VSCP Level II driver because it is constructed to work just with VSCP Level II events which does not fit in standard CAN frames. This type of driver does not need any buffers as no data is exchanged through the interface. |

 {% include "./bottom_copyright.md" %}