---
UID: NC:ks.PFNKSPINSETDATAFORMAT
title: PFNKSPINSETDATAFORMAT (ks.h)
description: An AVStream minidriver's AVStrMiniPinSetDataFormat routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this KSPIN structure and a match for this KSDATARANGE structure.
old-location: stream\avstrminipinsetdataformat.htm
tech.root: stream
ms.assetid: f38222e8-f432-4a28-ba2f-2e4f60edd762
ms.date: 04/23/2018
keywords: ["PFNKSPINSETDATAFORMAT callback function"]
ms.keywords: AVStrMiniPinSetDataFormat, AVStrMiniPinSetDataFormat routine [Streaming Media Devices], PFNKSPINSETDATAFORMAT, avstclbk_c72cee40-d3d3-45df-8ece-2eb0a8b52e38.xml, ks/AVStrMiniPinSetDataFormat, stream.avstrminipinsetdataformat
f1_keywords:
 - "ks/AVStrMiniPinSetDataFormat"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniPinSetDataFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSPINSETDATAFORMAT callback function


## -description


An AVStream minidriver's <i>AVStrMiniPinSetDataFormat</i> routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure and a match for this <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structure. This routine is also called due to certain types of dynamic format changes, for example the acceptance of a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-connection-proposedataformat">KSPROPERTY_CONNECTION_PROPOSEDATAFORMAT</a> property request.


## -parameters




### -param Pin [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which the data format is changing.


### -param OldFormat [in, optional]

Optional. Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure. Minidrivers can use this field to determine the data format that the pin was using before this call. If <b>NULL</b>, indicates that no data format has been set for the pin and that <i>Pin's</i> create dispatch has not yet been made. A <b>NULL</b> value here indicates that this routine was called at initialization time for format verification.


### -param OldAttributeList [in, optional]

Optional. Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> structure that stores attributes for the previous format.


### -param DataRange [in]

Pointer to a <a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a> structure. The data range for the new format.


### -param AttributeRange [in, optional]

Optional. The attribute range for the new format.


## -returns



Return STATUS_SUCCESS if <i>Pin</i>'s <b>ConnectionFormat</b> member matches the range that was passed to this routine. Return STATUS_NO_MATCH if <b>ConnectionFormat</b> does not match the passed range and the minidriver would like to continue to attempt to find a match with another range. Return an error code of choice if <b>ConnectionFormat</b> does not match the passed range and the minidriver does not want to continue to try to find a match with another range. Do not return STATUS_PENDING.




## -remarks



In a ring 3 graph, the Kernel Streaming Proxy module (KsProxy) sets the data format based on the agreed upon connection format or a dynamic format change. KsProxy issues a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-connection-dataformat">KSPROPERTY_CONNECTION_DATAFORMAT</a> request which, after some initial validation, is translated into this dispatch call to the minidriver. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_stream/index">Kernel Streaming Proxy</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-data-formats-and-data-ranges">KS Data Formats and Data Ranges</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/data-range-intersections-in-avstream">DataRange Intersections in AVStream</a>.

The minidriver specifies the address for <i>AVStrMiniPinSetDataFormat</i> in the <b>SetDataFormat</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

This routine can be called before the pin receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>, and minidrivers should be prepared to deal with this situation.

<i>OldFormat</i>, <i>OldAttributeList</i>, and <i>AttributeRange</i> are all optional parameters and can be <b>NULL</b>. 

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat">KSDATAFORMAT</a>



<a href="https://docs.microsoft.com/previous-versions/ff561658(v=vs.85)">KSDATARANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>
 

 

