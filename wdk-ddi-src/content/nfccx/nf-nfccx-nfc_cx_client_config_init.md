---
UID: NF:nfccx.NFC_CX_CLIENT_CONFIG_INIT
title: NFC_CX_CLIENT_CONFIG_INIT function (nfccx.h)
description: The NFC_CX_CLIENT_CONFIG_INIT function initializes the NFC_CX_CLIENT_CONFIG structure.
old-location: nfpdrivers\nfc_cx_client_config_init.htm
tech.root: nfpdrivers
ms.assetid: 0679406E-091D-4E66-956A-54E3A517BF4C
ms.date: 02/15/2018
keywords: ["NFC_CX_CLIENT_CONFIG_INIT function"]
ms.keywords: NFC_CX_CLIENT_CONFIG_INIT, NFC_CX_CLIENT_CONFIG_INIT function [Near-Field Proximity Drivers], nfccx/NFC_CX_CLIENT_CONFIG_INIT, nfpdrivers.nfc_cx_client_config_init
f1_keywords:
 - "nfccx/NFC_CX_CLIENT_CONFIG_INIT"
req.header: nfccx.h
req.include-header: Ncidef.h
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
req.lib: Nfccxstub.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- nfccxstub.lib
- nfccxstub.dll
api_name:
- NFC_CX_CLIENT_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# NFC_CX_CLIENT_CONFIG_INIT function


## -description


The <b>NFC_CX_CLIENT_CONFIG_INIT</b> function initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_client_config">NFC_CX_CLIENT_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ns-nfccx-_nfc_cx_client_config">NFC_CX_CLIENT_CONFIG</a> structure. 


### -param BusType [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfccx/ne-nfccx-_nfc_cx_transport_type">NFC_CX_TRANSPORT_TYPE</a> enumeration. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

