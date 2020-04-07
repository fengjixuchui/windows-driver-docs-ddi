---
UID: NF:nfccx.NfcCxSetRfDiscoveryConfig
title: NfcCxSetRfDiscoveryConfig function (nfccx.h)
description: Called by the client driver to configure the RF discovery parameters.
old-location: nfpdrivers\_nfccxsetrfdiscoveryconfig.htm
tech.root: nfpdrivers
ms.assetid: D0190BA1-196D-4F8B-A367-80272F094B6B
ms.date: 02/15/2018
keywords: ["NfcCxSetRfDiscoveryConfig function"]
ms.keywords: NfcCxSetRfDiscoveryConfig, NfcCxSetRfDiscoveryConfig method [Near-Field Proximity Drivers], nfccx/NfcCxSetRfDiscoveryConfig, nfpdrivers._nfccxsetrfdiscoveryconfig
f1_keywords:
 - "nfccx/NfcCxSetRfDiscoveryConfig"
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
- NfcCxSetRfDiscoveryConfig
product:
- Windows
targetos: Windows
req.typenames: 
---

# NfcCxSetRfDiscoveryConfig function


## -description


Called by the client driver to configure the RF discovery parameters.


## -parameters




### -param Device

A handle to a framework device object.


### -param Config

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_rf_discovery_config">NFC_CX_RF_DISCOVERY_CONFIG</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

