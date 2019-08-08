---
UID: NF:sdplib.SdpCreateNodeSequence
title: SdpCreateNodeSequence function (sdplib.h)
description: The Bluetooth SdpCreateNodeSequence function is used to create an empty sequence SDP node.
old-location: bltooth\sdpcreatenodesequence.htm
tech.root: bltooth
ms.assetid: 9e02f32b-cd39-4953-9698-a1800bedf0e2
ms.date: 04/27/2018
ms.keywords: SdpCreateNodeSequence, SdpCreateNodeSequence function [Bluetooth Devices], bltooth.sdpcreatenodesequence, bth_funcs_646168a7-522f-425c-99b7-706b84e02e20.xml, sdplib/SdpCreateNodeSequence
ms.topic: function
f1_keywords:
 - "sdplib/SdpCreateNodeSequence"
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpCreateNodeSequence
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpCreateNodeSequence function


## -description


The Bluetooth 
  <b>SdpCreateNodeSequence</b> function is used to create an empty sequence SDP node.


## -parameters




### -param tag [in]

A profile driver defined tag to associate with the node.


## -returns



If successful, this function returns a pointer to the newly allocated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> structure. If not successful, this
     function returns <b>NULL</b>.




## -remarks



After a sequence node is created by calling the 
    <b>SdpCreateNodeSequence</b> function, Bluetooth drivers can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpappendnodetocontainernode">
    SdpAppendNodeToContainerNode</a> function to insert other nodes into the sequence node or to add the
    new sequence node to another sequence node.

A sequence node can be added as a top-level attribute of an SDP record by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpappendnodetocontainernode">SdpAppendNodeToContainerNode</a>
 

 

