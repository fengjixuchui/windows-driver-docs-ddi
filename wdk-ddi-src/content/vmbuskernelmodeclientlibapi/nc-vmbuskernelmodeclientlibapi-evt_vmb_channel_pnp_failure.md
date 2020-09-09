---
UID: NC:vmbuskernelmodeclientlibapi.EVT_VMB_CHANNEL_PNP_FAILURE
title: EVT_VMB_CHANNEL_PNP_FAILURE (vmbuskernelmodeclientlibapi.h)
description: The EvtChannelPnpFailure callback function is invoked if the client endpoint in the guest virtual machine asynchronously fails to connect even though a PnP device was located.
old-location: netvista\evt_vmb_channel_pnp_failure.htm
tech.root: netvista
ms.assetid: 3331C043-CFB2-434C-8475-2F5F094F2460
ms.date: 05/02/2018
keywords: ["EVT_VMB_CHANNEL_PNP_FAILURE callback function"]
ms.keywords: EVT_VMB_CHANNEL_PNP_FAILURE, EVT_VMB_CHANNEL_PNP_FAILURE callback, EvtChannelPnpFailure, EvtChannelPnpFailure callback function [Network Drivers Starting with Windows Vista], PFN_VMB_CHANNEL_PNP_FAILURE, PFN_VMB_CHANNEL_PNP_FAILURE callback function pointer [Network Drivers Starting with Windows Vista], netvista.evt_vmb_channel_pnp_failure, vmbuskernelmodeclientlibapi/EvtChannelPnpFailure
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_VMB_CHANNEL_PNP_FAILURE
 - vmbuskernelmodeclientlibapi/EVT_VMB_CHANNEL_PNP_FAILURE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - VmbusKernelModeClientLibApi.h
api_name:
 - PFN_VMB_CHANNEL_PNP_FAILURE
---

# EVT_VMB_CHANNEL_PNP_FAILURE callback function


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <i>EvtChannelPnpFailure</i> callback function is invoked if the client endpoint in the
guest virtual machine asynchronously fails to connect even though a
PnP device was located.

## -parameters

### -param Channel 

[in]
The channel of the client endpoint.

### -param FailureStatus 

[in]
A failure code.

## -remarks

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbclientchannelinitsettargetpnp">VmbClientChannelInitSetTargetPnp</a> function registers <i>EvtChannelPnpFailure</i> code to run in the event  of this kind of failure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vmbuskernelmodeclientlibapi/nf-vmbuskernelmodeclientlibapi-vmbclientchannelinitsettargetpnp">VmbClientChannelInitSetTargetPnp</a>

