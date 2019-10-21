# History

* 2919-10-21 AKHE - Moved CANAL specification to it's own document.
* 2018-05-28 - Moved document too Markdown
*  2015-10-19 - Added some more info to CanalGetDriverInfo
*  2008-10-28 - Fixed error in status flags. Clarified error status return.
*  2008-04-15 - Added Message ID flags description. CANAL_IDFLAG_ERROR changed to CANAL_IDFLAG_STATUS
*  2008-04-04 - Driver description format final.
*  2007-12-08 - CanalGetDriverInfo does not need a handle.
*  2007-11-22 - CANAL_ERROR_INTERNAL and CANAL_ERROR_COMMUNICATION added.
*  2007-11-13 - getDriverConfigInfo added.
*  2007-11-12 - added const in front of send messages.
*  2007-11-01 - CANAL_LEVEL_USES_TCPIP CANAL driver Level introduced for use with the VSCP Daemon.
*  2007-10-30 - CanalGetDriverInfo call added.
*  2007-05-13 - CanalOpen device set to const char * instead of incorrect char *
*  2007-03-06 - CANALSTATUS table was wrong. Corrected.
*  2007-01-14 - Handle changed from int to long.
*  2005-07-26 - CanalBlockingOpen call removed. CanalBlockingSend and CanalBlockingReceive added. Fixed returned values that where wrong.
*  2005-03-17 - CanalBlockingOpen call added.
*  2004-07-08 – Bit 31 of the canmsg flag defined as direction bit for application software use.
*  2004-07-01 – Added some clarifications on the CanalSetMask, CanalSetFilter and 	CanalSetBaudrate methods
*  2004-06-07 – CANALASTATUS had a typo and was called CANALSTATE. Fixed.
*  2004-06-07 – Recovery from version lost in hard disk crash and realest as version 1.00
*  2003-02-18 – Initial version.

{% include "./bottom_copyright.md" %}