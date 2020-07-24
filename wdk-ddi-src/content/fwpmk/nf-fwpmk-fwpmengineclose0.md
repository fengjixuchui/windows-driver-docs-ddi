---
UID: NF:fwpmk.FwpmEngineClose0
title: FwpmEngineClose0 function (fwpmk.h)
description: The FwpmEngineClose0 function closes a previously opened session to the filter engine.Note  FwpmEngineClose0 is a specific version of FwpmEngineClose.
old-location: netvista\fwpmengineclose0.htm
tech.root: netvista
ms.assetid: 79ac01ff-9976-4321-a6b1-0a1cc6e5810a
ms.date: 05/02/2018
keywords: ["FwpmEngineClose0 function"]
ms.keywords: FwpmEngineClose0, FwpmEngineClose0 function [Network Drivers Starting with Windows Vista], fwpmk/FwpmEngineClose0, netvista.fwpmengineclose0, wfp_ref_2_funct_2_fwpm_b01feaca-7c4a-44a9-aec4-f867508b0129.xml
f1_keywords:
 - "fwpmk/FwpmEngineClose0"
 - "FwpmEngineClose0"
req.header: fwpmk.h
req.include-header: Fwpmk.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpmEngineClose0
targetos: Windows
req.typenames: 
---

# FwpmEngineClose0 function


## -description


The 
  <b>FwpmEngineClose0</b> function closes a previously opened session to the filter engine.
<div class="alert"><b>Note</b>  <b>FwpmEngineClose0</b> is a specific version of <b>FwpmEngineClose</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param engineHandle [in, out]

A handle for an open session to the filter engine.


## -returns



The 
     <b>FwpmEngineClose0</b> function returns one of the following NTSTATUS codes.

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
The session to the filter engine was successfully closed.

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



A callout driver calls the 
    <b>FwpmEngineClose0</b> function to close a session to the filter engine that was previously opened by a
    call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpmk/nf-fwpmk-fwpmengineopen0">FwpmEngineOpen0</a>
 

 

