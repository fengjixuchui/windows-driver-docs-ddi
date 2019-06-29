---
UID: NC:d3dumddi.PFND3DDDI_GETPITCH
title: PFND3DDDI_GETPITCH (d3dumddi.h)
description: The GetPitch function retrieves the pitch of a protected or non-lockable surface.
old-location: display\getpitch.htm
tech.root: display
ms.assetid: 1a5721a3-c03f-4827-9626-c9b6af5059a1
ms.date: 05/10/2018
ms.keywords: GetPitch, GetPitch callback function [Display Devices], PFND3DDDI_GETPITCH, PFND3DDDI_GETPITCH callback, UserModeDisplayDriver_Functions_6a055fa5-1f52-4d88-af1b-e9cab4abef13.xml, d3dumddi/GetPitch, display.getpitch
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetPitch is supported beginning with the Windows 7 operating system.
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- GetPitch
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_GETPITCH callback function


## -description


The <i>GetPitch</i> function retrieves the pitch of a protected or non-lockable surface. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). 


### -param *


*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_getpitch">D3DDDIARG_GETPITCH</a> structure that describes the protected surface. 


## -returns



The <i>GetPitch</i> function returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The pitch of the protected surface is successfully retrieved.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the GetPitch function.|

## -remarks



Hardware and drivers can optionally support the <i>GetPitch</i> function.  

The surface for which the <i>GetPitch</i> function returns the pitch can be non-lockable or protected. Therefore, the application cannot retrieve the pitch of the surface through a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lock">Lock</a> function. The application must retrieve the pitch of the surface to properly allocate the system memory buffer that the application subsequently uses in calls to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt">DecryptionBlt</a> functions. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_getpitch">D3DDDIARG_GETPITCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt">DecryptionBlt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a>
 

 

