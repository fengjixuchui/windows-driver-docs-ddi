---
UID: NC:mrx.PMRX_CHKFCB_CALLDOWN
title: PMRX_CHKFCB_CALLDOWN (mrx.h)
description: The MRxAreFilesAliased routine is called by RDBSS to request the network mini-redirector to determine if two FCB structures represent the same file.
old-location: ifsk\mrxarefilesaliased.htm
tech.root: ifsk
ms.assetid: 273266b3-98f4-4c93-a06b-8e149440ad24
ms.date: 04/16/2018
keywords: ["PMRX_CHKFCB_CALLDOWN callback function"]
ms.keywords: MRxAreFilesAliased, MRxAreFilesAliased routine [Installable File System Drivers], PMRX_CHKFCB_CALLDOWN, ifsk.mrxarefilesaliased, mrx/MRxAreFilesAliased, mrxref_5d6e6988-84d7-43ac-860e-4f184686a9e6.xml
req.header: mrx.h
req.include-header: Mrx.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_CHKFCB_CALLDOWN
 - mrx/PMRX_CHKFCB_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - MRxAreFilesAliased
---

# PMRX_CHKFCB_CALLDOWN callback function


## -description

The<b> MRxAreFilesAliased</b> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request the network mini-redirector to determine if two FCB structures represent the same file.

## -parameters

### -param Fcb1 

[in]
A pointer to the first FCB structure.

### -param Fcb2 

[in]
A pointer to the second FCB structure.

## -returns

<b>MRxAreFilesAliased</b> returns STATUS_SUCCESS indicating that the files are not aliased, or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
The <b>IndexNumber.QuadPart</b> members of the two FCB structures are identical. This value indicates that the two files that are being compared are aliases.

</td>
</tr>
</table>

## -remarks

RDBSS calls this routine when processing two files that appear to be the same but have different names (for example, an MS-DOS short name and a long name).

<b>MRxAreFilesAliased</b> is called by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a> routine when purging all the structures of an FOBX structure associated with a NET_ROOT structure. As part of this process, an attempt is made to purge all the FOBX structures that had a close pending before the purge request was received. RDBSS needs to scavenge any temporary FOBX structures in the following cases: 

<ol>
<li>
The <i>PurgingFcb</i> parameter that is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a> routine is the FCB structure for which the scavenging should occur. When this parameter is a directory, RDBSS needs to ensure that files that can potentially be in that directory are closed.

</li>
<li>
The FCB structure that is associated with the FOBX structure on the <b>FobxsToBeFinalized</b> member of the RDBSS_SCAVENGER structure doesn't point to the same FCB structure as the <i>PurgingFCB</i> parameter passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a>. This is complicated by the fact that they might not be the same FCB structures, but are actually the same file because of aliasing. In this case, the <b>MRxAreFilesAliased</b> routine is called to determine if the FCB structure is aliased.

</li>
</ol>
<b>MRxAreFilesAliased</b> is also called by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxscavengefobxsfornetroot">RxScavengeFobxsForNetRoot</a> routine when purging all the file objects associated with a NET_ROOT structure. This is complicated by the fact that the <i>PurgingFCB</i> parameter passed to <b>RxScavengeFobxsForNetRoot</b> and the FCB structure that is associated with the NET_ROOT structure might actually be the same file because of aliasing. In this case, the <b>MRxAreFilesAliased</b> routine is called to determine if the FCB structure is aliased.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)">MRxCleanupFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_calldown">MRxCloseSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcollapseopen">MRxCollapseOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fcb">MRxDeallocateForFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_deallocate_for_fobx">MRxDeallocateForFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_extendfile_calldown">MRxExtendForCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxextendfornoncache">MRxExtendForNonCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxflush">MRxFlush</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_forceclosed_calldown">MRxForceClosed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nc-mrx-pmrx_is_lock_realizable">MRxIsLockRealizable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen">MRxShouldTryToCollapseThisOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxtruncate">MRxTruncate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxzeroextend">MRxZeroExtend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxpurgerelatedfobxs">RxPurgeRelatedFobxs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scavengr/nf-scavengr-rxscavengefobxsfornetroot">RxScavengeFobxsForNetRoot</a>

