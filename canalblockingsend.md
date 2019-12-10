# int CanalBlockingSend( long handle, const PCANALMSG pCanMsg, unsigned long timeout  )

Send a blocking message on a CANAL channel.

The instruction should block if not instructed not to do so when the interface was opened.

## Params

*  handle – Handle for open physical/logical interface.
*  pCanMsg – Message to send.
*  timeout - Timeout in milliseconds. 0 to wait forever.


## Returns

CANAL_ERROR_SUCCESS, CANAL_ERROR_TIMEOUT on timeout on success or an error code on failure.


[filename](./bottom_copyright.md ':include')