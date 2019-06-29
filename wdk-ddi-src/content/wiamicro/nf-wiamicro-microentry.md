---
UID: NF:wiamicro.MicroEntry
title: MicroEntry function (wiamicro.h)
description: The MicroEntry function responds to commands sent by the WIA Flatbed driver.
old-location: image\microentry.htm
tech.root: image
ms.assetid: 3e0c51af-ceb9-4c06-ab6a-ccc468997fdd
ms.date: 05/03/2018
ms.keywords: MicroDrv_04aa15b3-5e4d-453d-b41a-a4de3c1228f7.xml, MicroEntry, MicroEntry function [Imaging Devices], image.microentry, wiamicro/MicroEntry
ms.topic: function
req.header: wiamicro.h
req.include-header: Wiamicro.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
- wiamicro.h
api_name:
- MicroEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# MicroEntry function


## -description


The<b> MicroEntry </b>function responds to commands sent by the WIA Flatbed driver. 


## -parameters




### -param lCommand

Specifies a command issued to the microdriver by the WIA Flatbed driver. 


### -param pValue [in, out]

Points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamicro/ns-wiamicro-val">VAL</a> structure that is used to pass information between the WIA Flatbed driver and the microdriver.


## -returns



If the function succeeds, it returns S_OK. If a passed command is not supported,  the function returns E_NOTIMPL. For any error, error information must be put in the <b>lVal</b> member of the VAL structure pointed to by <i>pValue</i>.




## -remarks



This function performs many different tasks, depending on the command passed in the <i>lCommand</i> parameter. See the <a href="https://docs.microsoft.com/windows-hardware/drivers/image/wia-microdriver-commands">WIA Microdriver Commands</a> reference section for a list of these commands.

Two structures are passed to the function. A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamicro/ns-wiamicro-val">VAL</a> structure is passed in the <i>pValue</i> pointer, and the <b>pScanInfo</b> member of the VAL structure points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamicro/ns-wiamicro-_scaninfo">SCANINFO</a> structure. The VAL structure is used to pass information between the WIA Flatbed Driver and the microdriver. The SCANINFO structure is used to store and communicate parameters of a scan data acquisition. Many of the commands passed to this function set values in the SCANINFO structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamicro/ns-wiamicro-_scaninfo">SCANINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamicro/ns-wiamicro-val">VAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/image/wia-microdriver-commands">WIA Microdriver Commands</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">WIA Microdriver Structures</a>
 

 

