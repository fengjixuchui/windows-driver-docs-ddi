---
UID: NS:fwpsk.FWPS_CALLOUT1_
title: FWPS_CALLOUT1_ (fwpsk.h)
description: The FWPS_CALLOUT1 structure defines the data that is required for a callout driver to register a callout with the filter engine.Note  FWPS_CALLOUT1 is the specific version of FWPS_CALLOUT used in Windows 7 and later.
old-location: netvista\fwps_callout1.htm
tech.root: netvista
ms.assetid: d15c4cd4-b4f0-4363-988a-2bbb235b7b37
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT1, FWPS_CALLOUT1 structure [Network Drivers Starting with Windows Vista], FWPS_CALLOUT1_, FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION, FWP_CALLOUT_FLAG_ALLOW_OFFLOAD, FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY, FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW, FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY, fwpsk/FWPS_CALLOUT1, netvista.fwps_callout1, wfp_ref_3_struct_3_fwps_A-E_dd7d51e7-3270-4480-8845-067c010e2fca.xml
ms.topic: struct
f1_keywords:
 - "fwpsk/FWPS_CALLOUT1"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 7.
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
- fwpsk.h
api_name:
- FWPS_CALLOUT1
product:
- Windows
targetos: Windows
req.typenames: FWPS_CALLOUT1
---

# FWPS_CALLOUT1_ structure


## -description


The <b>FWPS_CALLOUT1</b> structure defines the data that is required for a callout driver to register a
  callout with the filter engine.
<div class="alert"><b>Note</b>  <b>FWPS_CALLOUT1</b> is the specific version of <b>FWPS_CALLOUT</b> used in Windows 7 and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout2_">FWPS_CALLOUT2</a> is available. For Windows Vista, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a> is available.</div><div> </div>

## -struct-fields




### -field calloutKey

A callout driver-defined <b>GUID</b> that uniquely identifies the callout.


### -field flags

Flags that specify callout-specific parameters. Possible flags are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW"></a><a id="fwp_callout_flag_conditional_on_flow"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
A callout driver can specify this flag when registering a callout that will be added at a layer
       that supports data flows. If this flag is specified, the filter engine calls the callout driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a> callout function only if there
       is a context associated with the data flow. A callout driver associates a context with a data flow by
       calling the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a> function.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_OFFLOAD"></a><a id="fwp_callout_flag_allow_offload"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_OFFLOAD</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that the callout driver's 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a> callout function is unaffected
       by offloading network data processing to offload-capable network interface cards (NICs). If this flag
       is not specified, then offloading of network data processing is disabled for all traffic that is
       processed by any filters that specify the callout for the filter's action.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY"></a><a id="fwp_callout_flag_enable_commit_add_notify"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ENABLE_COMMIT_ADD_NOTIFY</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that it can receive notifications about objects and filters that are added inside a transaction. The filter engine sends the notification after the transaction is committed.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION"></a><a id="fwp_callout_flag_allow_mid_stream_inspection"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_MID_STREAM_INSPECTION</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to indicate that it can perform  dynamic stream inspection of data flows at stream level. See <a href="https://docs.microsoft.com/windows-hardware/drivers/network/stream-inspection">Stream Inspection</a>.

</td>
</tr>
<tr>
<td width="40%"><a id="FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY"></a><a id="fwp_callout_flag_allow_reclassify"></a><dl>
<dt><b>FWP_CALLOUT_FLAG_ALLOW_RECLASSIFY</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
A callout driver specifies this flag to register itself to be called when an existing socket operation is reclassified.

</td>
</tr>
</table>
 


### -field classifyFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a> callout function. The filter
     engine calls this function whenever there is network data to be processed by the callout.


### -field notifyFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn1">notifyFn1</a> function. The filter engine calls
     this function to notify the callout driver about events that are associated with the callout.


### -field flowDeleteFn

A pointer to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a> callout function. The filter
     engine calls this function whenever a data flow that is being processed by the callout is terminated.
     

If a callout driver does not associate a context with the data flows that the callout processes, then
     this member should be set to <b>NULL</b>.


## -remarks



A callout driver passes a pointer to an initialized <b>FWPS_CALLOUT1</b> structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a> function when it
    registers a callout with the filter engine.

A callout can set the <b>FWP_CALLOUT_FLAG_CONDITIONAL_ON_FLOW</b> flag only for connections on which
    the driver is interested in performing stream inspections. This callout will be ignored on all other
    connections. Performance will be improved and the driver will not have to maintain unnecessary state
    data.

This structure is essentially identical to the previous version, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>. The only differences are that
    the members of this version store the updated versions of the callout function pointers, and additional flags are available for callout drivers to set.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout2_">FWPS_CALLOUT2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_notify_fn1">notifyFn1</a>
 

 

