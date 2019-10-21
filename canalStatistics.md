# canalStatistics

canalStatistics är defined as

```c
typedef struct structCanalStatistics {
    unsigned long cntReceiveFrames;             /* # of receive frames */
    unsigned long cntTransmitFrames;            /* # of transmitted frames */
    unsigned long cntReceiveData;               /* # of received data bytes */
    unsigned long cntTransmitData;              /* # of transmitted data bytes */
    unsigned long cntOverruns;                  /* # of overruns */
    unsigned long cntBusWarnings;               /* # of bys warnings */
    unsigned long cntBusOff;                    /* # of bus off's */
} canalStatistics;
```

and should not need any extra comments.

{% include "./bottom_copyright.md" %}