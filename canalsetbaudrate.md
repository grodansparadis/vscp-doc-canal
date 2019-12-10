# int CanalSetBaudrate ( long handle, unsigned long baudrate  )

Set the bus speed for a channel.

Using the CanalOpen configurations string may be a better place to implement this.

Enable baudrate settings in the open call if possible. If available in the open method this method can be left unimplemented returning CANAL_ERROR_NOT_SUPPORTED.

# Params

* handle – Handle for open physical/logical interface.
* baudrate – The bus speed for the interface.

# Returns

CANAL_ERROR_SUCCESS on success or if not implemented CANAL_ERROR_NOT_SUPPORTED should always be returned.

[filename](./bottom_copyright.md ':include')