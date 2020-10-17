---
UID: NF:bdasup.BdaPropertyNodeTypes
title: BdaPropertyNodeTypes function (bdasup.h)
description: The BdaPropertyNodeTypes function retrieves a list of node types in a template topology.
old-location: stream\bdapropertynodetypes.htm
tech.root: stream
ms.assetid: 786ced41-7841-4898-93d5-afb4dcf7fa0c
ms.date: 04/23/2018
keywords: ["BdaPropertyNodeTypes function"]
ms.keywords: BdaPropertyNodeTypes, BdaPropertyNodeTypes function [Streaming Media Devices], bdaref_cec37979-eb0c-4914-86fe-6dc613c61ae8.xml, bdasup/BdaPropertyNodeTypes, stream.bdapropertynodetypes
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - BdaPropertyNodeTypes
 - bdasup/BdaPropertyNodeTypes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaPropertyNodeTypes
---

# BdaPropertyNodeTypes function


## -description

The <b>BdaPropertyNodeTypes</b> function retrieves a list of node types in a template topology.

## -parameters

### -param pIrp

### -param pKSProperty 

[in]
Points to a <a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property and request type of the property request.

### -param pulProperty 

[out]
Points to an array that receives the list of node types. 


#### - Irp [in]

Points to the IRP for the request to retrieve the list of node types. The BDA minidriver receives this IRP with the <a href="/windows-hardware/drivers/stream/ksproperty-bda-node-types">KSPROPERTY_BDA_NODE_TYPES</a> request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <b>BdaPropertyNodeTypes</b> function to retrieve the list of node types after the minidriver receives a <a href="/windows-hardware/drivers/stream/ksproperty-bda-node-types">KSPROPERTY_BDA_NODE_TYPES</a> request of the <a href="/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeTypes</b> function directly, without intercepting this request using an internal get-handler (<a href="/previous-versions/ff567177(v=vs.85)">KStrGetPropertyHandler</a>). See <a href="/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="/windows-hardware/drivers/stream/determining-bda-device-topology">Determining BDA Device Topology</a> for more information.

## -see-also

<a href="/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="/windows-hardware/drivers/stream/ksproperty-bda-node-types">KSPROPERTY_BDA_NODE_TYPES</a>



<a href="/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>