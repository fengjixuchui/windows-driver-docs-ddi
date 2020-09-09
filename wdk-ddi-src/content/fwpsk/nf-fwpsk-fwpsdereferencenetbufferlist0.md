---
UID: NF:fwpsk.FwpsDereferenceNetBufferList0
title: FwpsDereferenceNetBufferList0 function (fwpsk.h)
description: The FwpsDereferenceNetBufferList0 function decrements the reference count for a NET_BUFFER_LIST structure that a callout driver had acquired earlier using the FwpsReferenceNetBufferList0 function.Note  FwpsDereferenceNetBufferList0 is a specific version of FwpsDereferenceNetBufferList. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpsdereferencenetbufferlist0.htm
tech.root: netvista
ms.assetid: e327fe9d-9425-4cc3-9552-88e9c4c3bdbe
ms.date: 05/02/2018
keywords: ["FwpsDereferenceNetBufferList0 function"]
ms.keywords: FwpsDereferenceNetBufferList0, FwpsDereferenceNetBufferList0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsDereferenceNetBufferList0, netvista.fwpsdereferencenetbufferlist0, wfp_ref_2_funct_3_fwps_D-H_c55180f3-4575-4279-8481-99b17215fc11.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsDereferenceNetBufferList0
 - fwpsk/FwpsDereferenceNetBufferList0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsDereferenceNetBufferList0
---

# FwpsDereferenceNetBufferList0 function


## -description

The 
  <b>FwpsDereferenceNetBufferList0</b> function decrements the reference count for a 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that a callout
  driver had acquired earlier using the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a> function.
<div class="alert"><b>Note</b>  <b>FwpsDereferenceNetBufferList0</b> is a specific version of <b>FwpsDereferenceNetBufferList</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param netBufferList 

[in, out]
A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure for which the
     reference count is being decremented.

### -param dispatchLevel 

[in]
A value that indicates that the current IRQL = DISPATCH_LEVEL. A callout driver should set this
     parameter to <b>TRUE</b> only if it is known that it is running at IRQL = DISPATCH_LEVEL. Otherwise a callout
     driver sets this parameter to <b>FALSE</b>.

## -remarks

A callout driver calls the 
    <b>FwpsDereferenceNetBufferList0</b> function to decrement the reference count for a 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that it had
    acquired earlier using the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a> function. A callout driver must not call the 
    <b>FwpsDereferenceNetBufferList0</b> function for a NET_BUFFER_LIST structure unless it previously called
    the 
    <b>
    FwpsReferenceNetBufferList0</b> for the same structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>

