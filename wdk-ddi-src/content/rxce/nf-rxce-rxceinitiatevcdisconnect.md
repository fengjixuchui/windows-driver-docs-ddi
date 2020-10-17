---
UID: NF:rxce.RxCeInitiateVCDisconnect
title: RxCeInitiateVCDisconnect function (rxce.h)
description: RxCeInitiateVCDisconnect initiates a disconnect on the virtual circuit.
old-location: ifsk\rxceinitiatevcdisconnect.htm
tech.root: ifsk
ms.assetid: 978ddc02-9ff0-4798-879c-e4bc99081dcb
ms.date: 04/16/2018
keywords: ["RxCeInitiateVCDisconnect function"]
ms.keywords: RxCeInitiateVCDisconnect, RxCeInitiateVCDisconnect function [Installable File System Drivers], ifsk.rxceinitiatevcdisconnect, rxce/RxCeInitiateVCDisconnect, rxref_1893aa5d-dda4-49f7-b4bb-dc9bdd75154a.xml
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RxCeInitiateVCDisconnect
 - rxce/RxCeInitiateVCDisconnect
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxce.h
api_name:
 - RxCeInitiateVCDisconnect
---

# RxCeInitiateVCDisconnect function


## -description

<b>RxCeInitiateVCDisconnect</b> initiates a disconnect on the virtual circuit.

## -parameters

### -param pVc 

[in]
A pointer to the virtual circuit structure to be disconnected.

## -returns

<b>RxCeInitiateVCDisconnect</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>pVc</i> parameter passed to this routine was invalid. 

</td>
</tr>
</table>

## -remarks

<b>RxCeInitiateVCDisconnect</b> must be called in the context of a system worker thread.

## -see-also

<a href="/windows-hardware/drivers/ddi/rxce/nf-rxce-rxcebuildvc">RxCeBuildVC</a>



<a href="/windows-hardware/drivers/ddi/rxce/nf-rxce-rxceteardownvc">RxCeTearDownVC</a>