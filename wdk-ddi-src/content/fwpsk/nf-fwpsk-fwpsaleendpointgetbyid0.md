---
UID: NF:fwpsk.FwpsAleEndpointGetById0
title: FwpsAleEndpointGetById0 function (fwpsk.h)
description: The FwpsAleEndpointGetById0 function retrieves information about an application layer enforcement (ALE) endpoint.Note  FwpsAleEndpointGetById0 is a specific version of FwpsAleEndpointGetById.
old-location: netvista\fwpsaleendpointgetbyid0.htm
tech.root: netvista
ms.assetid: fa9a5078-d254-4b4a-bbfb-256491beff5f
ms.date: 05/02/2018
keywords: ["FwpsAleEndpointGetById0 function"]
ms.keywords: FwpsAleEndpointGetById0, FwpsAleEndpointGetById0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsAleEndpointGetById0, netvista.fwpsaleendpointgetbyid0, wfp_ref_2_funct_3_fwps_A-B_3feb07cf-ae5a-4412-a51a-8e4d4d65c31d.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsAleEndpointGetById0
 - fwpsk/FwpsAleEndpointGetById0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsAleEndpointGetById0
---

# FwpsAleEndpointGetById0 function


## -description

The 
  <b>FwpsAleEndpointGetById0</b> function retrieves information about an application layer enforcement (ALE)
  endpoint.
<div class="alert"><b>Note</b>  <b>FwpsAleEndpointGetById0</b> is a specific version of <b>FwpsAleEndpointGetById</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param engineHandle 

[in]
A handle for an open session with the filter engine. This handle is obtained when a session is
     opened by calling 
     <a href="/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>.

### -param endpointId 

[in]
The unique endpoint identifier.

### -param properties 

[out]
A pointer to an 
     <a href="/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_ale_endpoint_properties0">
     FWPS_ALE_ENDPOINT_PROPERTIES0</a> structure that contains the properties of the endpoint.

## -returns

The 
     <b>FwpsAleEndpointGetById0</b> function returns one of the following NTSTATUS codes.

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
The function succeeded.

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

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointenum0">FwpsAleEndpointEnum0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointgetsecurityinfo0">
   FwpsAleEndpointGetSecurityInfo0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsaleendpointsetsecurityinfo0">
   FwpsAleEndpointSetSecurityInfo0</a>