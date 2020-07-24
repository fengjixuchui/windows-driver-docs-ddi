---
UID: NS:ksmedia._tagKSTELEPHONY_CALLCONTROL
title: _tagKSTELEPHONY_CALLCONTROL (ksmedia.h)
description: The KSTELEPHONY_CALLCONTROL structure specifies the phone call type and control operation to use for the KSPROPERTY_TELEPHONY_CALLCONTROL property.
old-location: audio\kstelephony_callcontrol.htm
tech.root: audio
ms.assetid: 44CA5D9D-EF6E-4681-93EB-B803638896F9
ms.date: 05/08/2018
keywords: ["_tagKSTELEPHONY_CALLCONTROL structure"]
ms.keywords: "*PKSTELEPHONY_CALLCONTROL, KSTELEPHONY_CALLCONTROL, KSTELEPHONY_CALLCONTROL structure [Audio Devices], PKSTELEPHONY_CALLCONTROL, PKSTELEPHONY_CALLCONTROL structure pointer [Audio Devices], _tagKSTELEPHONY_CALLCONTROL, audio.kstelephony_callcontrol, ksmedia/KSTELEPHONY_CALLCONTROL, ksmedia/PKSTELEPHONY_CALLCONTROL"
f1_keywords:
 - "ksmedia/KSTELEPHONY_CALLCONTROL"
 - "KSTELEPHONY_CALLCONTROL"
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
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
- ksmedia.h
api_name:
- KSTELEPHONY_CALLCONTROL
targetos: Windows
req.typenames: KSTELEPHONY_CALLCONTROL, *PKSTELEPHONY_CALLCONTROL
---

# _tagKSTELEPHONY_CALLCONTROL structure


## -description


The <b>KSTELEPHONY_CALLCONTROL</b> structure specifies the phone call type and control operation to use for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-telephony-callcontrol">KSPROPERTY_TELEPHONY_CALLCONTROL</a> property.


## -struct-fields




### -field CallType

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).


### -field CallControlOp

Specifies the call control operation (enable or disable).

