---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
title: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS (d3d10umddi.h)
description: Provides status information for an existing CryptoSession object.
old-location: display\d3dwddm2_0ddi_crypto_session_status.htm
ms.assetid: DBAFEAE2-66B6-4F2F-801D-21B7792BCA60
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS enumeration"]
ms.keywords: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS enumeration [Display Devices], D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST, D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST, d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK, display.d3dwddm2_0ddi_crypto_session_status
f1_keywords:
 - "d3d10umddi/D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS
---

# D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS enumeration


## -description


Provides status information for an existing <i>CryptoSession</i> object.


## -enum-fields




### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_OK

The <i>CryptoSession</i> object is in a functional state.


### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_LOST

The underlying hardware key for the specified <i>CryptoSession</i> has become lost. 


### -field D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS_KEY_AND_CONTENT_LOST

The underlying hardware key for the specified <i>CryptoSession</i> has become lost and protected content has become corrupted. 

