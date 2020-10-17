---
UID: NE:wwan._WWAN_AUTH_METHOD
title: _WWAN_AUTH_METHOD (wwan.h)
description: The WWAN_AUTH_METHOD enumeration lists supported authentication methods.
old-location: netvista\wwan_auth_method.htm
tech.root: netvista
ms.assetid: D24D8C90-8F65-42BC-8FBC-308ECC4A73C9
ms.date: 05/02/2018
keywords: ["WWAN_AUTH_METHOD enumeration"]
ms.keywords: "*PWWAN_AUTH_METHOD, WWAN_AUTH_METHOD, WWAN_AUTH_METHOD enumeration [Network Drivers Starting with Windows Vista], WwanAuthAka, WwanAuthAkaPrime, WwanAuthMethodMax, WwanAuthSim, _WWAN_AUTH_METHOD, netvista.wwan_auth_method, wwan/WWAN_AUTH_METHOD, wwan/WwanAuthAka, wwan/WwanAuthAkaPrime, wwan/WwanAuthMethodMax, wwan/WwanAuthSim"
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: WWAN_AUTH_METHOD, *PWWAN_AUTH_METHOD
f1_keywords:
 - _WWAN_AUTH_METHOD
 - wwan/_WWAN_AUTH_METHOD
 - PWWAN_AUTH_METHOD
 - wwan/PWWAN_AUTH_METHOD
 - WWAN_AUTH_METHOD
 - wwan/WWAN_AUTH_METHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_AUTH_METHOD
---

# _WWAN_AUTH_METHOD enumeration


## -description

The WWAN_AUTH_METHOD enumeration lists supported authentication methods.

## -enum-fields

### -field WwanAuthSim

Authenticate using the SIM method.

### -field WwanAuthAka

Authenticate using the AKA method.

### -field WwanAuthAkaPrime

Authenticate using the AKA' (AKA Prime) method.

### -field WwanAuthMethodMax

This value is reserved. Do not use.

## -remarks

The <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a> and <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a> structures use this enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_challenge">WWAN_AUTH_CHALLENGE</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_auth_response">WWAN_AUTH_RESPONSE</a>