---
UID: NE:wditypes._WDI_CIPHER_ALGORITHM
title: _WDI_CIPHER_ALGORITHM (wditypes.h)
description: The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values.
old-location: netvista\wdi_cipher_algorithm.htm
tech.root: netvista
ms.assetid: 08413358-DFBC-4AC3-97B3-380D98EFFBF3
ms.date: 05/02/2018
keywords: ["WDI_CIPHER_ALGORITHM enumeration"]
ms.keywords: WDI_CIPHER_ALGORITHM, WDI_CIPHER_ALGORITHM enumeration [Device and Driver Installation], WDI_CIPHER_ALGO_BIP, WDI_CIPHER_ALGO_CCMP, WDI_CIPHER_ALGO_GCMP, WDI_CIPHER_ALGO_IHV_END, WDI_CIPHER_ALGO_IHV_START, WDI_CIPHER_ALGO_NONE, WDI_CIPHER_ALGO_RSN_USE_GROUP, WDI_CIPHER_ALGO_TKIP, WDI_CIPHER_ALGO_WEP, WDI_CIPHER_ALGO_WEP104, WDI_CIPHER_ALGO_WEP40, WDI_CIPHER_ALGO_WPA_USE_GROUP, _WDI_CIPHER_ALGORITHM, netvista.wdi_cipher_algorithm, netvista.wifi_cipher_algorithm, wditypes/WDI_CIPHER_ALGORITHM, wditypes/WDI_CIPHER_ALGO_BIP, wditypes/WDI_CIPHER_ALGO_CCMP, wditypes/WDI_CIPHER_ALGO_GCMP, wditypes/WDI_CIPHER_ALGO_IHV_END, wditypes/WDI_CIPHER_ALGO_IHV_START, wditypes/WDI_CIPHER_ALGO_NONE, wditypes/WDI_CIPHER_ALGO_RSN_USE_GROUP, wditypes/WDI_CIPHER_ALGO_TKIP, wditypes/WDI_CIPHER_ALGO_WEP, wditypes/WDI_CIPHER_ALGO_WEP104, wditypes/WDI_CIPHER_ALGO_WEP40, wditypes/WDI_CIPHER_ALGO_WPA_USE_GROUP
req.header: wditypes.hpp
req.include-header: 
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
targetos: Windows
req.typenames: WDI_CIPHER_ALGORITHM
f1_keywords:
 - _WDI_CIPHER_ALGORITHM
 - wditypes/_WDI_CIPHER_ALGORITHM
 - WDI_CIPHER_ALGORITHM
 - wditypes/WDI_CIPHER_ALGORITHM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - WDI_CIPHER_ALGORITHM
---

# _WDI_CIPHER_ALGORITHM enumeration


## -description

The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values.

## -enum-fields

### -field WDI_CIPHER_ALGO_NONE

Specifies that no cipher algorithm is enabled or supported.

### -field WDI_CIPHER_ALGO_WEP40

Specifies a Wired Equivalent Privacy (WEP) algorithm, which is the RC4-based algorithm that is specified in the IEEE 802.11-2012 standard. This enumerator specifies the WEP cipher algorithm with a 40-bit cipher key.

### -field WDI_CIPHER_ALGO_TKIP

Specifies a Temporal Key Integrity Protocol (TKIP) algorithm, which is the RC4-based cipher suite that is based on the algorithms that are defined in the WPA specification and IEEE 802.11i-2004 standard. This cipher also uses the Michael Message Integrity Code (MIC) algorithm for forgery protection.

### -field WDI_CIPHER_ALGO_CCMP

Specifies an AES-CCMP algorithm, as specified in the IEEE 802.11i-2004 standard and RFC 3610. Advanced Encryption Standard (AES) is the encryption algorithm defined in FIPS PUB 197.

### -field WDI_CIPHER_ALGO_WEP104

Specifies a WEP cipher algorithm with a 104-bit cipher key.

### -field WDI_CIPHER_ALGO_BIP

Specifies a BIP cipher algorithm.

### -field WDI_CIPHER_ALGO_GCMP

Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies a GCMP (Galois/Counter Mode Protocol) cipher algorithm. It is the only encryption protocol supported for 802.11ad (DMG) Phy.

### -field WDI_CIPHER_ALGO_WPA_USE_GROUP

Specifies a Wi-Fi Protected Access (WPA) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.

### -field WDI_CIPHER_ALGO_RSN_USE_GROUP

Specifies a Robust Security Network (RSN) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.

### -field WDI_CIPHER_ALGO_WEP

Specifies a WEP cipher algorithm with a cipher key of any length.

### -field WDI_CIPHER_ALGO_IHV_START

Specifies the start of the range that is used to define proprietary cipher algorithms that are developed by an independent hardware vendor (IHV).

### -field WDI_CIPHER_ALGO_IHV_END

Specifies the end of the range that is used to define proprietary authentication algorithms that are developed by an IHV.

