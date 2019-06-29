---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_POST_STARTED
title: EVT_VMB_CHANNEL_POST_STARTED (vmbuskernelmodeclientlibapi.h)
description: The EvtVmbChannelPostStarted callback function is invoked at either endpoint after packets can be received from the opposite endpoint.
old-location: netvista\evt_vmb_channel_post_started.htm
tech.root: netvista
ms.assetid: 0F48459F-BA02-4A0E-9228-BC064A6AD150
ms.date: 05/02/2018
ms.keywords: EVT_VMB_CHANNEL_POST_STARTED, EVT_VMB_CHANNEL_POST_STARTED callback, EvtVmbChannelPostStarted, EvtVmbChannelPostStarted callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_POST_STARTED, PFN_VMB_CHANNEL_POST_STARTED callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_post_started, vmbuskernelmodeclientlibapi/EvtVmbChannelPostStarted
ms.topic: callback
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- VmbusKernelModeClientLibApi.h
api_name:
- PFN_VMB_CHANNEL_POST_STARTED
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VMB_CHANNEL_POST_STARTED callback function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtVmbChannelPostStarted</i> callback function is invoked at either endpoint after packets can be received from
the opposite endpoint.  


## -parameters




### -param Channel [in]

The channel for these endpoints.


## -returns



This callback function does not return a value.




## -remarks



After a channel is created, a client driver can specify callback functions for state changes, including  <i>EvtVmbChannelPostStarted</i>, by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a> function.

After a channel has been  
configured, the Kernel Mode Client Library (KMCL) client calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a> function to open the channel.  When a channel is opened, KMCL invokes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened">EvtVmbChannelOpened</a> callback function. After the channel endpoints can receive packets but before packets are processed, KMCL invokes the <i>EvtVmbChannelPostStarted</i> callback.

You can wait for sent packets to complete in this function, such as by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest">VmbChannelSendSynchronousRequest</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_opened">EvtVmbChannelOpened</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nc-vmbuskernelmodeclientlibapi-evt_vmb_channel_post_started">EvtVmbChannelPostStarted</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmb_channel_state_change_callbacks_init">VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelenable">VmbChannelEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest">VmbChannelSendSynchronousRequest</a>
 

 

