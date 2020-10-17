---
UID: NE:wwan._WWAN_SMS_FLAG
title: _WWAN_SMS_FLAG (wwan.h)
description: The WWAN_SMS_FLAG enumeration lists different flags to filter SMS text messages.
old-location: netvista\wwan_sms_flag.htm
tech.root: netvista
ms.assetid: 6620d6c8-2b8a-440e-acf4-fb08570b13bf
ms.date: 05/02/2018
keywords: ["WWAN_SMS_FLAG enumeration"]
ms.keywords: "*PWWAN_SMS_FLAG, PWWAN_SMS_FLAG, PWWAN_SMS_FLAG enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_FLAG, WWAN_SMS_FLAG enumeration [Network Drivers Starting with Windows Vista], WwanRef_379a284f-534f-4acb-88c7-d60f7627ab32.xml, WwanSmsFlagAll, WwanSmsFlagDraft, WwanSmsFlagIndex, WwanSmsFlagMax, WwanSmsFlagNew, WwanSmsFlagOld, WwanSmsFlagSent, _WWAN_SMS_FLAG, netvista.wwan_sms_flag, wwan/PWWAN_SMS_FLAG, wwan/WWAN_SMS_FLAG, wwan/WwanSmsFlagAll, wwan/WwanSmsFlagDraft, wwan/WwanSmsFlagIndex, wwan/WwanSmsFlagMax, wwan/WwanSmsFlagNew, wwan/WwanSmsFlagOld, wwan/WwanSmsFlagSent"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.typenames: WWAN_SMS_FLAG, *PWWAN_SMS_FLAG
f1_keywords:
 - _WWAN_SMS_FLAG
 - wwan/_WWAN_SMS_FLAG
 - PWWAN_SMS_FLAG
 - wwan/PWWAN_SMS_FLAG
 - WWAN_SMS_FLAG
 - wwan/WWAN_SMS_FLAG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_SMS_FLAG
---

# _WWAN_SMS_FLAG enumeration


## -description

The WWAN_SMS_FLAG enumeration lists different flags to filter SMS text messages.

## -enum-fields

### -field WwanSmsFlagAll

No filter is set.

### -field WwanSmsFlagIndex

Filter based on the value of an index.

### -field WwanSmsFlagNew

Filter for new (unread) messages.

### -field WwanSmsFlagOld

Filter for old (read) messages.

### -field WwanSmsFlagSent

Filter for sent messages.

### -field WwanSmsFlagDraft

Filter for draft messages.

### -field WwanSmsFlagMax

The total number of filter flags.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_filter">WWAN_SMS_FILTER</a>