---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PROCESSING_COMPLETE
title: EVT_VMB_CHANNEL_PROCESSING_COMPLETE (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelProcessingComplete callback function is invoked when a group of packets has been delivered by the EvtVmbChannelProcessPacket function, if there is a pause before delivering subsequent packets.
old-location: netvista\evt_vmb_channel_processing_complete.htm
tech.root: netvista
ms.assetid: E30A169E-0EC6-4128-B268-5FC1CD37A877
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback function"]
ms.keywords: EVT_VMB_CHANNEL_PROCESSING_COMPLETE, EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback, EvtVmbChannelProcessingComplete, EvtVmbChannelProcessingComplete callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_PROCESSING_COMPLETE, PFN_VMB_CHANNEL_PROCESSING_COMPLETE callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_processing_complete, vmbuskernelmodeclientlibapi/EvtVmbChannelProcessingComplete
f1_keywords:
 - "vmbuskernelmodeclientlibapi/PFN_VMB_CHANNEL_PROCESSING_COMPLETE"
 - "PFN_VMB_CHANNEL_PROCESSING_COMPLETE"
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- VmbusKernelModeClientLibApi.h
api_name:
- PFN_VMB_CHANNEL_PROCESSING_COMPLETE
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_PROCESSING_COMPLETE callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelProcessingComplete</i> callback function is invoked when a group of packets has been delivered by
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a> function, if there is a pause before delivering subsequent packets.   


## -parameters




### -param Channel [in]

The channel one which the packets are delivered.


### -param PacketsProcessed [in]

The number of packets which were delivered in this batch.


## -remarks



The client driver registers its implementation of this callback function by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a> function. 

A pause in packet processing might occur because the
incoming ring buffer was empty.

This callback function can be invoked at DISPATCH_LEVEL or lower, unless the channel
has been configured to defer packet processing to a worker thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_process_packet">EvtVmbChannelProcessPacket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelinitsetprocesspacketcallbacks">VmbChannelInitSetProcessPacketCallbacks</a>
 

 

