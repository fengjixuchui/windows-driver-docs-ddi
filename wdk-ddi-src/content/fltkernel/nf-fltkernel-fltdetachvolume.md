---
UID: NF:fltkernel.FltDetachVolume
title: FltDetachVolume function (fltkernel.h)
description: FltDetachVolume detaches a minifilter driver instance from a volume.
old-location: ifsk\fltdetachvolume.htm
tech.root: ifsk
ms.assetid: 889750fc-69a9-4fe6-8905-6a7edc5c04fb
ms.date: 04/16/2018
keywords: ["FltDetachVolume function"]
ms.keywords: FltApiRef_a_to_d_2f7a4638-6f6d-4ac6-97b6-d547d64b56b6.xml, FltDetachVolume, FltDetachVolume function [Installable File System Drivers], fltkernel/FltDetachVolume, ifsk.fltdetachvolume
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDetachVolume
 - fltkernel/FltDetachVolume
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDetachVolume
---

# FltDetachVolume function


## -description

<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume.

## -parameters

### -param Filter 

[in, out]
Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param Volume 

[in, out]
Opaque volume pointer for the volume where the instance is attached. This parameter is required and cannot be <b>NULL</b>.

### -param InstanceName 

[in, optional]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure containing the instance name for the instance to be removed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the highest matching instance is removed.

## -returns

<b>FltDetachVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
<b>FltDetachVolume</b> found a matching instance, but the instance is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching instance was found. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume and tears down the instance. 

To attach a minifilter driver instance to a volume, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltattachvolume">FltAttachVolume</a> or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltattachvolumeataltitude">FltAttachVolumeAtAltitude</a>. 

To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompareinstancealtitudes">FltCompareInstanceAltitudes</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltattachvolume">FltAttachVolume</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltattachvolumeataltitude">FltAttachVolumeAtAltitude</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcompareinstancealtitudes">FltCompareInstanceAltitudes</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumeinstancefromname">FltGetVolumeInstanceFromName</a>