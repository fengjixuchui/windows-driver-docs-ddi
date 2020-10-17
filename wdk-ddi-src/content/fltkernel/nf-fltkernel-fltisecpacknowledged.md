---
UID: NF:fltkernel.FltIsEcpAcknowledged
title: FltIsEcpAcknowledged function (fltkernel.h)
description: The FltIsEcpAcknowledged routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.
old-location: ifsk\fltisecpacknowledged.htm
tech.root: ifsk
ms.assetid: ae4f4dfd-2a1d-4116-b56c-f7250697cf9e
ms.date: 04/16/2018
keywords: ["FltIsEcpAcknowledged function"]
ms.keywords: FltApiRef_e_to_o_a5a70461-2108-4e8f-a01b-0fec773f6010.xml, FltIsEcpAcknowledged, FltIsEcpAcknowledged routine [Installable File System Drivers], fltkernel/FltIsEcpAcknowledged, ifsk.fltisecpacknowledged
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltIsEcpAcknowledged
 - fltkernel/FltIsEcpAcknowledged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - FltMgr.sys
api_name:
 - FltIsEcpAcknowledged
---

# FltIsEcpAcknowledged function


## -description

The <b>FltIsEcpAcknowledged</b> routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged.

## -parameters

### -param Filter 

[in]
Opaque filter pointer for the minifilter driver. This pointer uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded.

### -param EcpContext 

[in]
Pointer to the ECP to test for acknowledgment.

## -returns

The routine returns <b>TRUE</b> if the ECP was marked as acknowledged and <b>FALSE</b> otherwise.

## -remarks

To mark an ECP as acknowledged, use the <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a> routine.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltacknowledgeecp">FltAcknowledgeEcp</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetecplistfromcallbackdata">FltGetEcpListFromCallbackData</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltinsertextracreateparameter">FltInsertExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisecpfromusermode">FltIsEcpFromUserMode</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltremoveextracreateparameter">FltRemoveExtraCreateParameter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltsetecplistintocallbackdata">FltSetEcpListIntoCallbackData</a>