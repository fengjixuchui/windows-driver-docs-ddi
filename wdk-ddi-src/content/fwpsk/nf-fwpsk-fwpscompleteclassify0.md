---
UID: NF:fwpsk.FwpsCompleteClassify0
title: FwpsCompleteClassify0 function (fwpsk.h)
description: A callout driver calls FwpsCompleteClassify0 to asynchronously complete a pended classify request.
old-location: netvista\fwpscompleteclassify0.htm
tech.root: netvista
ms.assetid: 995e86dc-fc26-4903-bc21-45475cb4e2bc
ms.date: 05/02/2018
keywords: ["FwpsCompleteClassify0 function"]
ms.keywords: FwpsCompleteClassify0, FwpsCompleteClassify0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCompleteClassify0, netvista.fwpscompleteclassify0, wfp_ref_2_funct_3_fwps_C_32709694-e6b8-41b8-90ea-4c8ef187ab6f.xml
f1_keywords:
 - "fwpsk/FwpsCompleteClassify0"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsCompleteClassify0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsCompleteClassify0 function


## -description


A callout driver calls 
  <b>FwpsCompleteClassify0</b> to asynchronously complete a pended classify request. The callout driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> function must have previously
  called 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a> to pend the classify
  request.
<div class="alert"><b>Note</b>  <b>FwpsCompleteClassify0</b> is a specific version of <b>FwpsCompleteClassify</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param classifyHandle [in]

The classification handle that identifies the callout driver's processing at the current layer.
     This handle is obtained by calling 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">
     FwpsAcquireClassifyHandle0</a>.


### -param flags [in]


      This parameter is reserved for future use. Set to zero.
     


### -param classifyOut [in, optional]

A pointer to a deep copy of the 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure that was originally
     passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> call when the classification was pended. When classifying asynchronously, the members
     of this structure can be set the same way as they would be in the callout driver's 
     <i>classifyFn</i> function when classifying inline.
     

If this parameter is used, the classification is taken as the callout driver's final decision. If set
     to <b>NULL</b>, the indication will be reauthorized.


## -remarks



<b>FwpsCompleteClassify0</b> must be called after a callout driver has called 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a> to remove the
    classification from its pended state.

After calling this function, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a> must
    be called to free the system resources associated with the classification handle.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0">FwpsAcquireClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0">FwpsPendClassify0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0">FwpsReleaseClassifyHandle0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>
 

 

