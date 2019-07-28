---
UID: NF:rilapi.RIL_OpenUiccLogicalChannel
title: RIL_OpenUiccLogicalChannel function (rilapi.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_openuicclogicalchannel.htm
tech.root: netvista
ms.assetid: 8e77d55d-62f5-450c-9d9a-41acfece84c0
ms.date: 05/02/2018
ms.keywords: RIL_OpenUiccLogicalChannel, RIL_OpenUiccLogicalChannel method [Network Drivers Starting with Windows Vista], netvista.ril_openuicclogicalchannel, rilapi/RIL_OpenUiccLogicalChannel
ms.topic: function
f1_keywords:
 - "rilapi/RIL_OpenUiccLogicalChannel"
req.header: rilapi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapi.h
api_name:
- RIL_OpenUiccLogicalChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# RIL_OpenUiccLogicalChannel function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param dwChannelGroup


### -param dwAppIdLength


### -param pbAppId


### -param dwSelectP2Arg


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



