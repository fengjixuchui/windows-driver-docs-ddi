---
UID: NS:miniport._EMULATOR_ACCESS_ENTRY
title: _EMULATOR_ACCESS_ENTRY (miniport.h)
description: The EMULATOR_ACCESS_ENTRY structure specifies an element in the EmulatorAccessEntries array set up in the VIDEO_PORT_CONFIG_INFO structure by drivers of VGA-compatible (SVGA) adapters on x86-based NT-based operating system platforms.
old-location: display\emulator_access_entry.htm
tech.root: display
ms.assetid: 966922b6-fa83-491e-bf03-848f798ebc69
ms.date: 02/23/2018
keywords: ["_EMULATOR_ACCESS_ENTRY structure"]
ms.keywords: ",  , *, *PEMULATOR_ACCESS_ENTRY, ,, A, C, E, EMULATOR_ACCESS_ENTRY, EMULATOR_ACCESS_ENTRY structure [Display Devices], L, M, N, O, P, PEMULATOR_ACCESS_ENTRY, PEMULATOR_ACCESS_ENTRY structure pointer [Display Devices], R, S, T, U, Video_Structs_8a00f589-ff5c-489b-b49b-abdcf9f42cf2.xml, Y, _, _EMULATOR_ACCESS_ENTRY, display.emulator_access_entry, miniport/EMULATOR_ACCESS_ENTRY, miniport/PEMULATOR_ACCESS_ENTRY"
f1_keywords:
 - "miniport/EMULATOR_ACCESS_ENTRY"
req.header: miniport.h
req.include-header: Miniport.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- miniport.h
api_name:
- EMULATOR_ACCESS_ENTRY
product:
- Windows
targetos: Windows
req.typenames: EMULATOR_ACCESS_ENTRY, *PEMULATOR_ACCESS_ENTRY
---

# _EMULATOR_ACCESS_ENTRY structure


## -description


The EMULATOR_ACCESS_ENTRY structure specifies an element in the <b>EmulatorAccessEntries</b> array set up in the VIDEO_PORT_CONFIG_INFO structure by drivers of VGA-compatible (SVGA) adapters on x86-based NT-based operating system platforms.


## -syntax


```cpp
typedef struct _EMULATOR_ACCESS_ENTRY {
  ULONG                     BasePort;
  ULONG                     NumConsecutivePorts;
  EMULATOR_PORT_ACCESS_TYPE AccessType;
  UCHAR                     AccessMode;
  UCHAR                     StringSupport;
  PVOID                     Routine;
} EMULATOR_ACCESS_ENTRY, *PEMULATOR_ACCESS_ENTRY;
```


## -struct-fields




### -field BasePort

Specifies the bus-relative physical address of the I/O port or ports to be hooked out by the V86 emulator. This value and the range of ports must fall within an access range of I/O ports already claimed in the registry by <b>VideoPortGetAccessRanges</b> or <b>VideoPortVerifyAccessRanges</b>.


### -field NumConsecutivePorts

Specifies the number of consecutive ports to be hooked by the V86 emulator, starting at <b>BasePort</b>. This value is determined by the width of each hooked I/O port. For example, if port addresses 0x3C0 and 0x3C1 are hooked as a single USHORT-addressable port, this value should be 1.


### -field AccessType

Specifies the size of the data transferred through the given I/O port as one of <b>Uchar</b>, <b>Ulong</b>, or <b>Ushort</b>.


### -field AccessMode

Specifies how the given I/O port can be accessed as one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>


The I/O port range must be accessible in at least one of the preceding modes.


### -field StringSupport

Indicates whether the driver-supplied <i>SvgaHwIoPortXxx</i> function supports string accesses in cases where many values of the given <b>AccessType</b> are "pumped" through an I/O port consecutively. If this member is set to <b>TRUE</b>, the <b>Routine</b> member must specify the entry point of a miniport driver-supplied<i> SvgaHwIoPortXxxString</i> function.


### -field Routine

Pointer to the miniport driver's <i>SvgaHwIoPortXxx</i> that handles accesses to the port or ports described in this structure.


## -remarks



VGA-compatible miniport drivers of SVGA video hardware in x86-based machines must define emulator access ranges, which a VGA-compatible miniport driver can set up with <b>VideoPortSetTrappedEmulatorPorts</b> to be accessed directly from full-screen MS-DOS applications for faster I/O. Such a driver must supply a set of <i>SvgaHwIoPortXxx</i> functions to validate any sequence of application-issued <b>IN</b>s, <b>INSB/INSW/INSD</b>s, <b>OUT</b>s, and/or <b>OUTSB/OUTSW/OUTSD</b>s to each such I/O port range.

Data in each EMULATOR_ACCESS_ENTRY-type element is used to determine which I/O ports (memory locations at which adapter registers are accessible) in the miniport driver's access ranges have been taken over (hooked out) by the V86 emulator on x86-based platforms. Values written to these locations by full-screen MS-DOS applications are trapped and forwarded to the miniport driver's corresponding <i>SvgaHwIoPortXxx</i> function for validation before they are written to or read from the video adapter. However, the miniport driver can enable the application to directly access particular I/O port ranges by calling <b>VideoPortSetTrappedEmulatorPorts</b> to improve performance.




## -see-also

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>



<a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>



 

 


