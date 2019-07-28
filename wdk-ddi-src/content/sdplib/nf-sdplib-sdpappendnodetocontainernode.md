---
UID: NF:sdplib.SdpAppendNodeToContainerNode
title: SdpAppendNodeToContainerNode function (sdplib.h)
description: The Bluetooth SdpAppendNodeToContainerNode function is used to attach an SDP node to a sequence or alternative SDP node.
old-location: bltooth\sdpappendnodetocontainernode.htm
tech.root: bltooth
ms.assetid: beec5516-6191-4b70-8c80-ddbaedbad5c0
ms.date: 04/27/2018
ms.keywords: SdpAppendNodeToContainerNode, SdpAppendNodeToContainerNode function [Bluetooth Devices], bltooth.sdpappendnodetocontainernode, bth_funcs_dce0f01b-3dab-48d4-8230-ad3bb0d1c210.xml, sdplib/SdpAppendNodeToContainerNode
ms.topic: function
f1_keywords:
 - "sdplib/SdpAppendNodeToContainerNode"
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- sdplib.h
api_name:
- SdpAppendNodeToContainerNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# SdpAppendNodeToContainerNode function


## -description


The Bluetooth 
  <b>SdpAppendNodeToContainerNode</b> function is used to attach an SDP node to a sequence or alternative SDP
  node.


## -parameters




### -param Parent [in]

The SDP sequence or alternative node to which the 
     <b>SdpAppendNodeToContainerNode</b> function adds the child node.


### -param Node

<p>The SDP node to add to the parent node.</p>




## -returns



Possible return values include:




## -remarks



Use the 
    <b>SdpAppendNodeToContainerNode</b> function to insert any type of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a> into a sequence or alternative node,
    including other sequences.

Do not use this function to attach attribute nodes to the top level of an SDP record. Call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a> function to
    perform that action. For more information about the tree structure, see 
    <a href="https://docs.microsoft.com/previous-versions/ff536672(v=vs.85)">Converting SDP Records to a
    Tree Structure</a>.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_node_interface">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdpnode/ns-sdpnode-_sdp_node">SDP_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/sdplib/nf-sdplib-sdpaddattributetotree">SdpAddAttributeToTree</a>
 

 

