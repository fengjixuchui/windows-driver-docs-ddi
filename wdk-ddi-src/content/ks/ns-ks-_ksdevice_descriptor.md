---
UID: NS:ks._KSDEVICE_DESCRIPTOR
title: _KSDEVICE_DESCRIPTOR (ks.h)
description: The KSDEVICE_DESCRIPTOR structure describes the characteristics of a particular device.
old-location: stream\ksdevice_descriptor.htm
tech.root: stream
ms.assetid: dc68f6d8-a2d5-4940-a708-fe761c3a8a0d
ms.date: 04/23/2018
ms.keywords: "*PKSDEVICE_DESCRIPTOR, KSDEVICE_DESCRIPTOR, KSDEVICE_DESCRIPTOR structure [Streaming Media Devices], PKSDEVICE_DESCRIPTOR, PKSDEVICE_DESCRIPTOR structure pointer [Streaming Media Devices], _KSDEVICE_DESCRIPTOR, avstruct_b51d9c2c-278f-4357-b84a-da6959ea9959.xml, ks/KSDEVICE_DESCRIPTOR, ks/PKSDEVICE_DESCRIPTOR, stream.ksdevice_descriptor"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSDEVICE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: KSDEVICE_DESCRIPTOR, *PKSDEVICE_DESCRIPTOR
---

# _KSDEVICE_DESCRIPTOR structure


## -description


The KSDEVICE_DESCRIPTOR structure describes the characteristics of a particular device.


## -struct-fields




### -field Dispatch

A pointer to the client dispatch table for this device. This dispatch table contains client dispatch functions for PNP messages such as <b>Add</b>, <b>Start</b>, <b>Stop</b>, <b>Remove</b>. Clients are not required to supply a dispatch table unless they want to receive callbacks for the PNP messages described in the dispatch table. Any member of the dispatch table can be <b>NULL</b> to indicate that the client does not want to receive notification for that particular message. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>.


### -field FilterDescriptorsCount

This member contains the number of filter descriptors for this device that will be provided in the <b>FilterDescriptors</b> member. Zero is a legal value for this member; clients can create filter factories dynamically with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatefilterfactory">KsCreateFilterFactory</a> function instead of statically describing them in the device descriptor.


### -field FilterDescriptors

A pointer to an array of filter descriptors that describe filters that can be created by this device. This member may be <b>NULL</b> if <b>FilterDescriptorsCount</b> is zero. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>.


### -field Version

A value of type ULONG. This should be one and only one of the values in the following table, or set to zero if writing a pre-version 0x100 driver.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSDEVICE_DESCRIPTOR_VERSION

</td>
<td>
Indicates support of the <a href="https://docs.microsoft.com/previous-versions/ff554290(v=vs.85)">AVStrMiniDeviceQueryInterface</a> dispatch of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>.

</td>
</tr>
<tr>
<td>
KSDEVICE_DESCRIPTOR_VERSION_2

</td>
<td>
Indicates support of the <b>Flags</b> member of KSDEVICE_DESCRIPTOR.

</td>
</tr>
</table>
 


### -field Flags

A value of type ULONG. There is only one flag currently defined.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
KSDEVICE_FLAG_ENABLE_REMOTE_WAKEUP

</td>
<td>
Indicates that the device supports remote wakeup.

</td>
</tr>
</table>
 


### -field Alignment

 




## -remarks



Most often, this structure is used in conjunction with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksinitializedriver">KsInitializeDriver</a> in the client's <b>DriverEntry</b> function to initialize the device. This structure is also used to manually initialize or create devices with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksinitializedevice">KsInitializeDevice</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatedevice">KsCreateDevice</a> functions.

If you set <b>Version</b> to KSDEVICE_DESCRIPTOR_VERSION_2 and run your driver on an early version of AVStream that does not support <b>Flags</b>, all flags will be considered to be zero.

Similarly, using an earlier version descriptor on later versions of AVStream causes no flags to be specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscreatedevice">KsCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksinitializedevice">KsInitializeDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksinitializedriver">KsInitializeDriver</a>
 

 

