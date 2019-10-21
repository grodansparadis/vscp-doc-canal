# int CanalSend( long handle, const PCANALMSG pCanMsg  )

Send a non-blocking  message on a CANAL channel.

The instruction should NOT block and instead return an error if unable to directly send  the CAN message.

# Params

*  handle – Handle for open physical/logical interface.
*  pCanMsg – Message to send.

# Returns

CANAL_ERROR_SUCCESS on success or an error code on failure.

{% include "./bottom_copyright.md" %}