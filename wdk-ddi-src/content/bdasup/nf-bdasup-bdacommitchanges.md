---
UID: NF:bdasup.BdaCommitChanges
title: BdaCommitChanges function (bdasup.h)
description: The BdaCommitChanges function commits the changes to BDA topology that have occurred since the last call to the BdaStartChanges function.
old-location: stream\bdacommitchanges.htm
tech.root: stream
ms.assetid: 89bac523-65f1-462e-a734-285cda9e33ac
ms.date: 04/23/2018
keywords: ["BdaCommitChanges function"]
ms.keywords: BdaCommitChanges, BdaCommitChanges function [Streaming Media Devices], bdaref_41fbbc81-4461-47a2-ba7a-725b696329f3.xml, bdasup/BdaCommitChanges, stream.bdacommitchanges
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - BdaCommitChanges
 - bdasup/BdaCommitChanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Bdasup.lib
 - Bdasup.dll
api_name:
 - BdaCommitChanges
---

# BdaCommitChanges function


## -description

The <b>BdaCommitChanges</b> function commits the changes to BDA topology that have occurred since the last call to the <b>BdaStartChanges</b> function.

## -parameters

### -param pIrp

#### - Irp [in]

Points to the IRP for the request to commit changes. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-commit-changes">KSMETHOD_BDA_COMMIT_CHANGES</a> request.

## -returns

Returns STATUS_SUCCESS or an appropriate error code.

## -remarks

A BDA minidriver calls the <b>BdaCommitChanges</b> function to commit a set of BDA topology changes after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-commit-changes">KSMETHOD_BDA_COMMIT_CHANGES</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a> method set from the network provider. BDA minidrivers define dispatch and filter-automation tables so that those minidrivers either dispatch the <b>BdaCommitChanges</b> function directly or intercept this request using an internal method (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>), which then calls the <b>BdaCommitChanges</b> function. For example, BDA minidrivers that intercept this request can obtain a pointer to the BDA filter from the passed IRP so that they can: 

<ol>
<li>
Set the new list of resources for the filter to the pending list of resources. 

</li>
<li>
Set the change state of the filter to BDA_CHANGES_COMPLETE. 

</li>
<li>
Commit the resources on the underlying device. 

</li>
</ol>
See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/changing-bda-filter-properties">Changing BDA Filter Properties</a> for more information.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff556518(v=vs.85)">BDA_CHANGE_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdacheckchanges">BdaCheckChanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bdasup/nf-bdasup-bdastartchanges">BdaStartChanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethodsetid-bdachangesync">KSMETHODSETID_BdaChangeSync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksmethod-bda-commit-changes">KSMETHOD_BDA_COMMIT_CHANGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkshandler">KStrMethodHandler</a>

