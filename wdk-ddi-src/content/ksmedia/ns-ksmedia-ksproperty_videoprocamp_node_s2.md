---
UID: NS:ksmedia.__unnamed_struct_93
title: KSPROPERTY_VIDEOPROCAMP_NODE_S2 (ksmedia.h)
description: The KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure describes node-based property settings in the PROPSETID_VIDCAP_VIDEOPROCAMP property set that use two values at the same time.
old-location: stream\ksproperty_videoprocamp_node_s2.htm
tech.root: stream
ms.assetid: 767ea5d2-4c11-4ba8-bb1f-c5f6038244f5
ms.date: 04/30/2019
keywords: ["KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure"]
ms.keywords: "*PKSPROPERTY_VIDEOPROCAMP_NODE_S2, KSPROPERTY_VIDEOPROCAMP_NODE_S2, KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure [Streaming Media Devices], PKSPROPERTY_VIDEOPROCAMP_NODE_S2, PKSPROPERTY_VIDEOPROCAMP_NODE_S2 structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S2, ksmedia/PKSPROPERTY_VIDEOPROCAMP_NODE_S2, stream.ksproperty_videoprocamp_node_s2, vidcapstruct_1876d4f4-15ae-4bcb-9f57-ed08ddf15411.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_VIDEOPROCAMP_NODE_S2"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- ksmedia.h
api_name:
- KSPROPERTY_VIDEOPROCAMP_NODE_S2
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_VIDEOPROCAMP_NODE_S2, *PKSPROPERTY_VIDEOPROCAMP_NODE_S2
---

# KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure


## -description


The KSPROPERTY_VIDEOPROCAMP_NODE_S2 structure describes node-based property settings in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-videoprocamp">PROPSETID_VIDCAP_VIDEOPROCAMP</a> property set that use two values at the same time.


## -struct-fields




### -field NodeProperty

Specifies an initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a> structure that describes the node, property set, property ID, and request type.


### -field Value1

Specifies the first value of a request. For set requests, the minidriver should set the property specified in <b>Property</b> to this value. For get requests, the minidriver should return the value of the property specified in <b>Property</b>.


### -field Flags

Specifies the flags of a request. For set requests, this value indicates the desired setting. For get requests, this value contains the current setting. This member can be set to one of the values that are defined in <i>ksmedia.h</i>:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
Indicates that the property is to be adjusted manually

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
Indicates that the property is to be adjusted automatically

</td>
</tr>
</table>
 


### -field Capabilities

Specifies the capabilities of a property. This member has meaning only for get requests. The minidriver should return the capabilities of the video processing amplifier with respect to the property specified in <b>Property</b>. This member should be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_MANUAL

</td>
<td>
The device supports manual setting of the specified property

</td>
</tr>
<tr>
<td>
KSPROPERTY_VIDEOPROCAMP_FLAGS_AUTO

</td>
<td>
The device supports automatic setting of the specified property

</td>
</tr>
</table>
 


### -field Value2

Specifies the second value of a request. For set requests, the minidriver should set the property specified in <b>Property</b> to this value. For get requests, the minidriver should return the value of the property specified in <b>Property</b>.


## -remarks



This structure is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-videoprocamp-whitebalance-component">KSPROPERTY_VIDEOPROCAMP_WHITEBALANCE_COMPONENT</a>.



