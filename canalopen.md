# long CanalOpen( const char *pConfigStr, unsigned long flags )

Opens a CAN(AL) channel.

## Params

###  pConfigStr
Configuration data such as physical device to connect to. This is the place to add device specific parameters and initial filters/masks. This is a text string. It can be a name, some parameters or whatever the interface creator chooses. Normally items are separated with a semicolon (";").

### flags

Device specific flags with a meaning defined by the interface creator.


## Returns

Unsigned long handle for open physical/logic interface or < = 0 on error. The handle is used in subsequent CANAL calls and is valid until [CanalOpen](canalopen,md) is called.

[filename](./bottom_copyright.md ':include')