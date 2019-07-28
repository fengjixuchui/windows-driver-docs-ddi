---
UID: NF:rilapi.RIL_SendMsgAck_V1
title: RIL_SendMsgAck_V1 function (rilapi.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendmsgack_v1.htm
tech.root: netvista
ms.assetid: 5a3c148e-d113-4cbc-a88a-691531bb3d9d
ms.date: 05/02/2018
ms.keywords: RIL_SendMsgAck_V1, RIL_SendMsgAck_V1 method [Network Drivers Starting with Windows Vista], netvista.ril_sendmsgack_v1, rilapi/RIL_SendMsgAck_V1
ms.topic: function
f1_keywords:
 - "rilapi/RIL_SendMsgAck_V1"
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
- RIL_SendMsgAck_V1
product:
- Windows
targetos: Windows
req.typenames: 
---

# RIL_SendMsgAck_V1 function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param hUiccApp


### -param dwAckID


### -param dwMsgStatus


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



