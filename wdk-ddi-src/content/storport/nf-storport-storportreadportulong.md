---
UID: NF:storport.StorPortReadPortUlong
title: StorPortReadPortUlong macro (storport.h)
description: The StorPortReadPortUlong routine reads a value from a specified port address.
old-location: storage\storportreadportulong.htm
tech.root: storage
ms.assetid: b04ef64a-cf1f-4de5-acb3-e57687f64719
ms.date: 03/29/2018
keywords: ["StorPortReadPortUlong macro"]
ms.keywords: StorPortReadPortUlong, StorPortReadPortUlong routine [Storage Devices], storage.storportreadportulong, storport/StorPortReadPortUlong, storprt_3ef5c577-3d75-4797-b5ce-8f36e4080c47.xml
f1_keywords:
 - "storport/StorPortReadPortUlong"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortReadPortUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortReadPortUlong macro


## -description


The <b>StorPortReadPortUlong</b> routine reads a value from a specified port address. 


## -parameters




### -param  [in]

A pointer to the hardware device extension.


### -param p [in]

A pointer to the address from which to read. 


## -remarks



For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportulong">ScsiPortReadPortUlong</a> routine. For a buffered version of this routine see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportbufferulong">StorPortReadPortBufferUlong</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/nf-srb-scsiportreadportbufferulong">ScsiPortReadPortBufferUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadportulong">StorPortReadPortUlong</a>
 

 

