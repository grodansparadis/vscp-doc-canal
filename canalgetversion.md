# unsigned long CanalGetVersion ( void  )

Get the Canal version. This is the version derived from the document that has been used to implement the interface.  Version is located on the front page of the document.

# Returns

CANAL protocol version expressed as an unsigned long with MAJOR_VERSION in first byte, MINOR_VERSION in second byte, RELEASE_VERSION in third byte and BUILD_VERSION in fourth byte. All stored on big endian.

[filename](./bottom_copyright.md ':include')