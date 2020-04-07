---
UID: NF:storport.StorPortResume
title: StorPortResume function (storport.h)
description: The StorPortResume routine resumes a paused adapter.
old-location: storage\storportresume.htm
tech.root: storage
ms.assetid: 2a1e380b-ddad-495b-a921-ebd85525d1a6
ms.date: 03/29/2018
keywords: ["StorPortResume function"]
ms.keywords: StorPortResume, StorPortResume routine [Storage Devices], storage.storportresume, storport/StorPortResume, storprt_3970ca06-96f5-4d0a-84b0-781145133788.xml
f1_keywords:
 - "storport/StorPortResume"
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
- StorPortResume
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortResume function


## -description


The <b>StorPortResume</b> routine resumes a paused adapter.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


## -returns



<b>StorPortResume</b> returns <b>TRUE</b> if the miniport driver succeeded in resuming the paused adapter, <b>FALSE</b> if not. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportpause">StorPortPause</a>
 

 

