---
UID: NC:fwpsk.FWPS_NET_BUFFER_LIST_NOTIFY_FN1
title: FWPS_NET_BUFFER_LIST_NOTIFY_FN1 (fwpsk.h)
description: The filter engine calls the FWPS_NET_BUFFER_LIST_NOTIFY_FN1 callout function to notify the callout driver about events that are associated with packets tagged by the callout.Note   FWPS_NET_BUFFER_LIST_NOTIFY_FN1 is the specific version of FWPS_NET_BUFFER_LIST_NOTIFY_FN used in Windows 8 and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 7, FWPS_NET_BUFFER_LIST_NOTIFY_FN0 is available.
old-location: netvista\fwps_net_buffer_list_notify_fn1.htm
tech.root: netvista
ms.assetid: fe9ab4b2-5692-4b6e-a7fc-11e9ac8280bc
ms.date: 05/02/2018
keywords: ["FWPS_NET_BUFFER_LIST_NOTIFY_FN1 callback function"]
ms.keywords: FWPS_NET_BUFFER_LIST_NOTIFY_FN1, FWPS_NET_BUFFER_LIST_NOTIFY_FN1 callback, FwpsNetBufferListNotifyFN1, FwpsNetBufferListNotifyFN1 callback function [Network Drivers Starting with Windows Vista], fwpsk/FwpsNetBufferListNotifyFN1, netvista.fwps_net_buffer_list_notify_fn1
f1_keywords:
 - "fwpsk/FwpsNetBufferListNotifyFN1"
 - "FwpsNetBufferListNotifyFN1"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- fwpsk.h
api_name:
- FwpsNetBufferListNotifyFN1
targetos: Windows
req.typenames: 
---

# FWPS_NET_BUFFER_LIST_NOTIFY_FN1 callback function


## -description


The filter engine calls the <i>
  FWPS_NET_BUFFER_LIST_NOTIFY_FN1</i> callout function to notify the callout driver about events that are
  associated with packets tagged by the callout.<div class="alert"><b>Note</b>  <i>
  FWPS_NET_BUFFER_LIST_NOTIFY_FN1</i> is the specific version of <i>FWPS_NET_BUFFER_LIST_NOTIFY_FN</i> used in Windows 8 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a> is available.</div>
<div> </div>



## -parameters




### -param eventType [in]

A value that indicates the type of notification that the filter engine is sending to the callout.
     This parameter will be set to one of the values of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_net_buffer_list_event_type0_">
     FWPS_NET_BUFFER_LIST_EVENT_TYPE0</a> enumeration.


### -param netBufferList [in, out]

A pointer to the buffer list that contains packets that were previously tagged as interesting by
     the callout driver.


### -param newNetBufferList [in, out, optional]

A pointer to an updated buffer list that contains packets that are interesting to the callout
     driver. The use of this parameter differs depending on the type of event. For events where a change is
     made to the indicated packet, the changed version is passed as this parameter.


### -param layerId [in]

The layer from which the notification function was called.


### -param context [in]

The context used to tag the packets of interest. This value is the value assigned to the packet by
     the callout driver and is used to identify the packet.


### -param contextTag [in]

The context tag used to associate the packets of interest with the context of the callout
     driver.


## -returns



A callout's 
  <i>
  FWPS_NET_BUFFER_LIST_NOTIFY_FN1</i> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout driver accepts the notification from the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



This function is associated with a callout driver by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>. A callout driver can use a single notification function to
    handle messages for multiple associated buffer lists by using the context and context tag to
    differentiate between instances.

This function is identical to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>, except that the return type is <b>NTSTATUS</b> instead of <b>VOID</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_net_buffer_list_event_type0_">
     FWPS_NET_BUFFER_LIST_EVENT_TYPE0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_net_buffer_list_notify_fn0">FWPS_NET_BUFFER_LIST_NOTIFY_FN0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsnetbufferlistassociatecontext1">FwpsNetBufferListAssociateContext1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-packet-tagging">Using Packet Tagging</a>
 

 

