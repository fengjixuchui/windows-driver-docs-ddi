---
UID: NS:ndis._NDIS_PD_FILTER_PARAMETERS
title: _NDIS_PD_FILTER_PARAMETERS (ndis.h)
description: This structure holds metadata for a packet filter.
old-location: netvista\ndis_pd_filter_parameters.htm
tech.root: netvista
ms.assetid: AE220435-C8EC-408E-8177-A88FC858FA5A
ms.date: 05/02/2018
ms.keywords: NDIS_PD_FILTER_PARAMETERS, NDIS_PD_FILTER_PARAMETERS structure [Network Drivers Starting with Windows Vista], _NDIS_PD_FILTER_PARAMETERS, ndis/NDIS_PD_FILTER_PARAMETERS, netvista.ndis_pd_filter_parameters
ms.topic: struct
f1_keywords:
 - "ndis/NDIS_PD_FILTER_PARAMETERS"
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- Ndis.h
api_name:
- NDIS_PD_FILTER_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_FILTER_PARAMETERS
---

# _NDIS_PD_FILTER_PARAMETERS structure


## -description


This structure holds metadata for a packet filter.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_FILTER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_FILTER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_FILTER_PARAMETERS_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0 by the client. It is ignored by the provider.


### -field MatchProfileId

This value is used to determine if the HeaderGroupMatchArray members describe an NDIS_GFP_HEADER_GROUP_EXACT_MATCH array or a NDIS_GFP_HEADER_GROUP_WILDCARD_MATCH array.


### -field Priority

The priority of this filter.


### -field CounterHandle

A handle to a counter.


### -field TargetReceiveQueue

The target receive queue to filter.


### -field RxFilterContext

The context for the receive filter.


### -field HeaderGroupMatchArray

An array of either NDIS_GFP_HEADER_GROUP_EXACT_MATCH or NDIS_GFP_HEADER_GROUP_WILDCARD_MATCH elements as determined by the MatchProfileId member.


### -field HeaderGroupMatchArrayNumElements

The number of elements for the HeaderGroupMatchArray.


### -field HeaderGroupMatchArrayElementSize

The size of each element for the HeaderGroupMatchArray.


### -field HeaderGroupMatchArrayTotalSize

The total size of the HeaderGroupMatchArray.


## -remarks



This structure must be aligned on an 8-byte boundary.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 

