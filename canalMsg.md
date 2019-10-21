# canalMsg

canalMsg is the CAN(AL) message that is sent/received. It is defined as.

```c
typedef struct structCanalMsg {
    unsigned long flags;                /* CAN message flags */
    unsigned long obid;                 /* Used by driver for channel info etc. */
    unsigned long id;                   /* CAN id (11-bit or 29-bit) */
    unsigned char sizeData;             /* Data size 0-8 */
    unsigned char data[8];              /* CAN Data	 */
    unsigned long timestamp;            /* Relative time stamp for package in microseconds */
} canalMsg;
```

**flags** bits are defined as

```c
#define CANAL_IDFLAG_STANDARD               0x00000000  /* Standard message id (11-bit) */
#define CANAL_IDFLAG_EXTENDED               0x00000001  /* Extended message id (29-bit) */
#define CANAL_IDFLAG_RTR                    0x00000002  /* RTR-Frame */
#define CANAL_IDFLAG_STATUS                 0x00000004  /* This package is a status indication (id holds error code) */
#define CANAL_IDFLAG_SEND                   0x80000000  /* Reserved for use by application software to indicate send */

```
CANAL_IDFLAG_STATUS is used to return error frames.

**obid** is for application use. Can for exampl3e be used to identify a channel among several.

**timestamp** is a relative time in microseconds set by the driver. Set to zero if no timestamp is available.

{% include "./bottom_copyright.md" %}