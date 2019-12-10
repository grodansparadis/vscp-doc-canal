# canalStatus

canalStatus is defined as

```c
typedef struct structCanalStatus {
    unsigned long channel_status;           /* Current state for channel */
    unsigned long lasterrorcode;            /* Last error code */
    unsigned long lasterrorsubcode;         /* Last error sub code */
    char lasterrorstr[80];                  /* Last error string */
} canalStatus;
```

**channel_status** is a bit field with the following defined flags

```c
#define CANAL_STATUS_NONE                   0x00000000
#define CANAL_STATUS_ACTIVE                 0x10000000
#define CANAL_STATUS_PASSIVE                0x40000000
#define CANAL_STATUS_BUS_OFF                0x80000000
#define CANAL_STATUS_BUS_WARN               0x20000000
#define CANAL_STATUS_PHY_FAULT              0x08000000
#define CANAL_STATUS_PHY_H                  0x04000000
#define CANAL_STATUS_PHY_L                  0x02000000
#define CANAL_STATUS_SLEEPING               0x01000000
#define CANAL_STATUS_STOPPED                0x00800000
#define CANAL_STATUS_RECIVE_BUFFER_FULL	    0x00400000  /* Drivers buffer */
#define CANAL_STATUS_TRANSMIT_BUFFER_FULL   0x00200000  /* Drivers buffer */
```

**lasterrorcode** is the last issued CANAL error code. See error codes.

**lasterrorsubcode** is a driver implementation specific error code that describe the issued error code in more detail.

**lasterrorstr** is a null terminated UTF8 string that describe last error in clear text.

[filename](./bottom_copyright.md ':include')