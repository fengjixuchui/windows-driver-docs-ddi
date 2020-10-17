---
UID: NF:nfccx.NfcCxRegisterSequenceHandler
title: NfcCxRegisterSequenceHandler function (nfccx.h)
description: Called by the client driver during initialization to register for handling specific sequences.
old-location: nfpdrivers\_nfccxregistersequencehandler.htm
tech.root: nfpdrivers
ms.assetid: 30957475-D02B-434D-9FAB-BBCD5732DCA5
ms.date: 02/15/2018
keywords: ["NfcCxRegisterSequenceHandler function"]
ms.keywords: NfcCxRegisterSequenceHandler, NfcCxRegisterSequenceHandler method [Near-Field Proximity Drivers], nfccx/NfcCxRegisterSequenceHandler, nfpdrivers._nfccxregistersequencehandler
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nfccxstub.lib
req.dll: NfcCx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - NfcCxRegisterSequenceHandler
 - nfccx/NfcCxRegisterSequenceHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NfcCx.dll
api_name:
 - NfcCxRegisterSequenceHandler
---

# NfcCxRegisterSequenceHandler function


## -description

Called by the client driver during initialization to register for handling specific sequences.

## -parameters

### -param Device

A handle to a framework device object.

### -param Sequence

An <a href="/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_sequence">NFC_CX_SEQUENCE</a>-typed enumerator.

### -param EvtNfcCxSequenceHandler

A pointer to an <a href="/windows-hardware/drivers/ddi/nfccx/nc-nfccx-evt_nfc_cx_sequence_handler">EvtNfcCxSequenceHandler</a> callback function.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS.

## -see-also

<a href="/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) design guide</a>