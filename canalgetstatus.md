# int CanalGetStatus( long handle,  PCANALSTATUS pCanStatus  )

Get status for a CANAL channel

Returns a structure (CANALSTATUS) that gives some information about the state of the channel.  How the information is interpreted is up to the interface designer. Typical use is for extended error information.

# Params

*  handle – Handle for open physical/logical interface.
*  pCanStatus – Status.

# Returns

CANAL_ERROR_SUCCESS on success or an error code on failure.

[filename](./bottom_copyright.md ':include')