# Development resources

## The parameter string
You can define this string and let it use any format as long as it is a list of values separated by semicolon ';'. See [CanalGetDriverInfo](./canalgetdriverinfo.md) for the abstract description of the variable types.

## Flags
This is a 32-bit unsigned bit. Each bit is a flag with a meaning (bit's can also be grouped together). A developer can define the bits freely except for bit 32 (0x80000000) which is reserved for **debug mode**. In this mode the driver should output diagnostic output to syslog or some other output source. See [CanalGetDriverInfo](./canalgetdriverinfo.md) for the abstract description of the flag integer.

## Examples

For projects that implement CANAL check 
* [the VSCP daemon](https://github.com/grodansparadis/vscp)
* [vscpworks](https://github.com/grodansparadis/vscpworks) Deprecated
* [vscpworks+](https://github.com/grodansparadis/vscp-works-qt)
* [canalview](https://github.com/rusoku/CANAL-View)
 

## C
  * canal.h is [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/canal.h). This file contains general CANAL defines.
  * canal_macro.h is [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/canal_macro.h). This file contains macros used bye CANAL.
  * canaldlldef.h is [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/canaldlldef.h) This file contains interface definitions for a CANAL driver for windows and linux.

## C++
  * **VscpCanalDeviceIf** A class that implements a CANAL host interface is [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/vscpcanaldeviceif.h) and [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/vscpcanaldeviceif.cpp)
  * **vscpClientCanal** Pluggable VSCP interface for CANAL is [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/vscp_client_canal.h) and [here](https://github.com/grodansparadis/vscp/blob/master/src/vscp/common/vscp_client_canal.cpp).
  * **canal_config** XML configuration parsing. [here](https://github.com/grodansparadis/vscp/tree/master/src/vscp/common) 
  * **canalconfigwizard** for QT based configuration wizard [here](https://github.com/grodansparadis/vscp-works-qt/tree/master/src)

## Python
* **canal-python** is [here](https://pypi.org/project/canal-python/).

## node.js
* **node-canal** is [here](https://www.npmjs.com/package/node-canal).

## node-red
* **node-red-contrib-canal** is [here](https://flows.nodered.org/node/node-red-contrib-canal)



[filename](./bottom_copyright.md ':include')