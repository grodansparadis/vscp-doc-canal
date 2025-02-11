# long CanalOpen( const char *pConfigStr, unsigned long flags )

Opens a CANAL channel.

## Params

###  pConfigStr
Configuration data such as physical device to connect to. This is the place to add device specific parameters and initial filters/masks. This is a text string. It can be a name, some parameters or whatever the interface creator chooses. 

Normally items are separated with a semicolon (";") but if the string starts with a ´{´ character it should be interpreted as a JSON configuration string. If the string starts with a '<' character it should be intepreted as a XML string.

### flags

Device specific flags with a meaning defined by the interface creator. Bit 32 is reserved for debug information.


## Returns

Unsigned long handle for open physical/logic interface or < = 0 on error. The handle is used in subsequent CANAL calls and is valid until [CanalOpen](canalopen,md) is called.

[filename](./bottom_copyright.md ':include')
