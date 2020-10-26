# ![](/assets/logo_100.png)

# CANAL - CAN Abstraction Layer

Author 2000-2020 Åke Hedman, [Grodans Paradis AB](http://www.grodansparadis.com), &lt;[akhe@grodansparadis.com](mailto:akhe@grodansparadis.com)&gt;

Document created: *${/var/creation-time}*  
Specification version: ${/var/document-version} 

CANAL (CAN Abstraction Layer) is a very simple approach to interfacing a (logical) CAN module/card or some other (logical) CAN hardware. It is simple and consists mostly of open, close, read, write and filter/mask handling.

CANAL is used as Level I API for drivers used by [VSCP & Friends](https://www,vscp.org) project software tools. There is a lot of drivers implemented in that project along with source code that can be used as starting points.

The CANAL interface does not need to connect physical hardware. It can be used as an interface to logical items also. This makes it possible to get a common interface to both very diverse hardware and soft interfaces. All which can benefit from a source of common software tools.

CANAL has been constructed from a need to use CAN in the form of control networks in the SOHO (Small Office/Home) environment. This kind of environment is totally different to the very tough automotive or industry control world where Canal probably would not be the best solution. The goal has not been to construct something that will take over the world just something that does solve a problem at hand.

CANAL is tightly coupled with the Very Simple Control Protocol, VSCP and the VSCP daemon. This is a protocol constructed for SOHO control situations. The model has been constructed as a two-layer model so that the VSCP Daemon can also be useful for people that are just  interested in CAN and not in VSCP. You can find more information about vscp at https://www.vscp.org.

CANAL is open and free to use with no restrictions, as is the above software, which is released under MIT license.

Current information about CANAL, the VSCP Daemon and VSCP (Very Simple Control Protocol) can be found at https://www.vscp.org.

The library is licensed under [the  MIT License](https://opensource.org/licenses/MIT) so it can be used freely in opne and closed project.

Viewable/downloadable documentation is [here](https://docs.vscp.org/#canal)

[filename](./bottom_copyright.md ':include')
