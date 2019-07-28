---
UID: NS:avc._AVC_PIN_DESCRIPTOR
title: _AVC_PIN_DESCRIPTOR (avc.h)
description: The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.
old-location: stream\avc_pin_descriptor.htm
tech.root: stream
ms.assetid: 6d404c47-01ae-496c-8252-32f180cf0fd3
ms.date: 04/23/2018
ms.keywords: "*PAVC_PIN_DESCRIPTOR, AVC_PIN_DESCRIPTOR, AVC_PIN_DESCRIPTOR structure [Streaming Media Devices], PAVC_PIN_DESCRIPTOR, PAVC_PIN_DESCRIPTOR structure pointer [Streaming Media Devices], _AVC_PIN_DESCRIPTOR, avc/AVC_PIN_DESCRIPTOR, avc/PAVC_PIN_DESCRIPTOR, avcref_4207f0d3-ba1e-47ae-abdd-4eebccf094b9.xml, stream.avc_pin_descriptor"
ms.topic: struct
f1_keywords:
 - "avc/AVC_PIN_DESCRIPTOR"
req.header: avc.h
req.include-header: Avc.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- avc.h
api_name:
- AVC_PIN_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: AVC_PIN_DESCRIPTOR, *PAVC_PIN_DESCRIPTOR
---

# _AVC_PIN_DESCRIPTOR structure


## -description


The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device.


## -struct-fields




### -field PinId

Specifies the offset (or ID) of the pin for which information is to be retrieved.


### -field PinDescriptor

Specifies a KSPIN_DESCRIPTOR structure. This structure is allocated in the nonpaged pool. The subunit driver must not free this pointer.


### -field IntersectHandler

An optional output parameter specifying a data range intersect handler associated with the <b>DataRanges</b> member of the <b>PinDescriptor</b> member.


### -field Context

An optional output parameter specifying a value to be passed to the <b>IntersectHandler</b> when it is called during format negotiation. For more information about what an intersect handler is, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/data-range-intersections-in-avstream">DataRange Intersections in AVStream</a>.


## -remarks



This structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avc-function-get-pin-descriptor">AVC_FUNCTION_GET_PIN_DESCRIPTOR</a> function code.

This structure is used only as a member inside the AVC_MULTIFUNC_IRB structure. It is not used by itself.

See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/using-avc-sys">How to Use Avc.sys</a> For information about building and sending an AV/C command.

A description of the members of the <b>KSPIN_DESCRIPTOR</b> structure used in AVC_PIN_DESCRIPTOR follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct {
    ULONG                   InterfacesCount;
    const KSPIN_INTERFACE*  Interfaces;
    ULONG                   MediumsCount;
    const KSPIN_MEDIUM*     Mediums;
    ULONG                   DataRangesCount;
    const PKSDATARANGE*     DataRanges;
    KSPIN_DATAFLOW          DataFlow;
    KSPIN_COMMUNICATION     Communication;
    const GUID*             Category;
    const GUID*             Name;
    union {
        LONGLONG            Reserved;
        struct {
            ULONG           ConstrainedDataRangesCount;
            PKSDATARANGE*   ConstrainedDataRanges;
        };
    };
} KSPIN_DESCRIPTOR, *PKSPIN_DESCRIPTOR;</pre>
</td>
</tr>
</table></span></div>
<h3><a id="Members"></a><a id="members"></a><a id="MEMBERS"></a>Members</h3>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avc/nc-avc-pfnavcintersecthandler">AV/C Intersect Handler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/avc/ns-avc-_avc_multifunc_irb">AVC_MULTIFUNC_IRB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR</a>
 

 


