---
UID: NF:nfccx.NfcCxDeviceInitialize
title: NfcCxDeviceInitialize function (nfccx.h)
description: Called by the client driver after a WDF device has been created during the AddDevice routine.
old-location: nfpdrivers\_nfccxdeviceinitialize.htm
tech.root: nfpdrivers
ms.assetid: E9282552-93AB-4380-A270-1A538CCF8C0E
ms.date: 02/15/2018
keywords: ["NfcCxDeviceInitialize function"]
ms.keywords: NfcCxDeviceInitialize, NfcCxDeviceInitialize method [Near-Field Proximity Drivers], nfccx/NfcCxDeviceInitialize, nfpdrivers._nfccxdeviceinitialize
f1_keywords:
 - "nfccx/NfcCxDeviceInitialize"
 - "NfcCxDeviceInitialize"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NfcCx.dll
api_name:
- NfcCxDeviceInitialize
targetos: Windows
req.typenames: 
---

# NfcCxDeviceInitialize function


## -description


Called by the client driver after a WDF device has been created during the AddDevice routine.


## -parameters




### -param Device

A handle to a framework device object.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

