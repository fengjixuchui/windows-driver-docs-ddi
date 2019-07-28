---
UID: NS:d3dumddi._D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
title: _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE (d3dumddi.h)
description: A structure that holds information to wait for synchronized objects.
old-location: display\d3dddicb_submitwaitforsyncobjectstohwqueue.htm
tech.root: display
ms.assetid: 9890EB61-2CED-41AB-9A87-76D5020D84A0
ms.date: 05/10/2018
ms.keywords: D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure [Display Devices], _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, d3dumddi/D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE, display.d3dddicb_submitwaitforsyncobjectstohwqueue
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE"
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE
---

# _D3DDDICB_SUBMITWAITFORSYNCOBJECTSTOHWQUEUE structure


## -description


A structure that holds information to wait for synchronized objects. 


## -struct-fields




### -field hHwQueue

Hardware queue to queue the wait on.



### -field ObjectCount

Number of objects to wait on.



### -field ObjectHandleArray

Handles to monitored fence synchronization objects to wait on.



### -field FenceValueArray

Monitored fence values to be waited on.


