# canalMsg

canalMsg is the CAN(AL) message that is sent/received. It is defined as.

```c
typedef struct structCanalMsgFD {
    uint32_t flags;                			/* CAN message flags */
    uint32_t obid;                 			/* Used by driver for channel info etc. */
    uint32_t timestamp;            			/* Relative time stamp for frame in microseconds */
    uint32_t id;                   			/* CAN id (11-bit or 29-bit) */
    uint8_t reserved[7];			 	/* for alignment */
    uint8_t sizeData;              			/* Data size 0-8, 12, 16, 20, 24, 32, 48, 64) */
    unsigned char data[64] __attribute__((aligned(8))); /* CAN Data	 */
} canalMsgFD;
```

**flags** bits are defined as

```c
#define CANAL_IDFLAG_STANDARD               0x00000000  /* Standard message id (11-bit) */
#define CANAL_IDFLAG_EXTENDED               0x00000001  /* Extended message id (29-bit) */
#define CANAL_IDFLAG_RTR                    0x00000002  /* RTR-Frame */
#define CANAL_IDFLAG_STATUS                 0x00000004  /* This package is a status indication (id holds error code) */
#define CANAL_IDFLAG_FD                     0x00000008  /* This is a FD frame is set */
#define CANAL_IDFLAG_SEND                   0x80000000  /* Reserved for use by application software to indicate send */


```
CANAL_IDFLAG_STATUS is used to return error frames.

**obid** is for application use. Can for example be used to identify a channel among several.

**timestamp** is a relative time in microseconds set by the driver. Set to zero if no timestamp is available.

[filename](./bottom_copyright.md ':include')
