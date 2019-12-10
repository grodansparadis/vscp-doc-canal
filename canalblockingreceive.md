# int CanalBlockingReceive( long handle,  PCANALMSG pCanMsg, unsigned long timeout  )

Blocking receive a message on a CANAL channel.

The instruction should block if not instructed not to do so when the interface was opened.

**Note** If bit 2 (CANAL_IDFLAG_STATUS) in flags of the CANAL message is set in the returned message an error status message is returned from the adapter and not a CAN message. For error frames id can have the following values

```c
/* Status message codes ( in received message ) */
#define CANAL_STATUSMSG_OK                  0x00        /* Normal condition. */
#define CANAL_STATUSMSG_OVERRUN             0x01        /* Overrun occurred when sending data to CAN bus. */
#define CANAL_STATUSMSG_BUSLIGHT            0x02        /* Error counter has reached 96. */
#define CANAL_STATUSMSG_BUSHEAVY            0x03        /* Error counter has reached 128. */
#define CANAL_STATUSMSG_BUSOFF              0x04        /* Device is in BUSOFF. CANAL_STATUS_OK is */
                                                        /*      sent when returning to operational mode. */
#define CANAL_STATUSMSG_STUFF               0x20        /* Stuff Error. */
#define CANAL_STATUSMSG_FORM                0x21        /* Form Error. */
#define CANAL_STATUSMSG_ACK                 0x23        /* Ack Error. */
#define CANAL_STATUSMSG_BIT1                0x24        /* Bit1 Error. */
#define CANAL_STATUSMSG_BIT0                0x25        /* Bit0 Error. */
#define CANAL_STATUSMSG_CRC                 0x27        /* CRC Error. */
```

# Params

*  handle – Handle for open physical/logical interface.
*  pCanMsg – Received message.
*  timout - Timeout in milliseconds. 0 to wait forever.


# Returns

CANAL_ERROR_SUCCESS on success, CANAL_ERROR_TIMEOUT on timeout or an error code on failure.


[filename](./bottom_copyright.md ':include')