---
UID: NC:d3dumddi.PFND3DDDI_BUFBLT1
title: PFND3DDDI_BUFBLT1 (d3dumddi.h)
description: Performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.
old-location: display\bufblt1.htm
tech.root: display
ms.assetid: 92F2AED7-935F-4E3E-934F-D6DF9AA87495
ms.date: 05/10/2018
ms.keywords: BufBlt1, BufBlt1 callback function [Display Devices], PFND3DDDI_BUFBLT1, PFND3DDDI_BUFBLT1 callback, d3dumddi/BufBlt1, display.bufblt1
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- BufBlt1
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_BUFBLT1 callback function


## -description


Performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer. Implemented by Windows Display Driver Model (WDDM) 1.2 or later user-mode display drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

pData [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_bufferblt1">D3DDDIARG_BUFFERBLT1</a> structure that describes the parameters of the buffer bitblt operation.


## -returns




      Returns S_OK or an appropriate error result if the buffer bitblt operation is not successfully performed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_bufferblt1">D3DDDIARG_BUFFERBLT1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

