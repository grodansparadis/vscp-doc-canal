# int CanalSetMask ( long handle, unsigned long filter  )

Set the mask for a CANAL channel. There is only one mask available.

The CanalOpen configuration string can be used to set multiple masks using the configuration string.

Enable mask settings in the open call if possible. If available in the open method this method can be left unimplemented returning CANAL_ERROR_NOT_SUPPORTED.

### Params

* handle – Handle for open physical/logical interface.
* filter – filter for the interface.

### Returns

CANAL_ERROR_SUCCESS on success or if not implemented CANAL_ERROR_NOT_SUPPORTED should always be returned.

[filename](./bottom_copyright.md ':include')