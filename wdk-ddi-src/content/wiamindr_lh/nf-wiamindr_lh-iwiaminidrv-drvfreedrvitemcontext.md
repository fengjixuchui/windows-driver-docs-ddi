---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvFreeDrvItemContext
title: IWiaMiniDrv::drvFreeDrvItemContext (wiamindr_lh.h)
description: The IWiaMiniDrv::drvFreeDrvItemContext method frees a device-specific context.
old-location: image\iwiaminidrv_drvfreedrvitemcontext.htm
tech.root: image
ms.assetid: bc4f751f-d92a-47e6-8cbe-0a587292b160
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvFreeDrvItemContext method, IWiaMiniDrv.drvFreeDrvItemContext, IWiaMiniDrv::drvFreeDrvItemContext, MiniDrv_59a7d220-cd1d-4cc2-870a-3260feaba7e9.xml, drvFreeDrvItemContext, drvFreeDrvItemContext method [Imaging Devices], drvFreeDrvItemContext method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvfreedrvitemcontext, wiamindr_lh/IWiaMiniDrv::drvFreeDrvItemContext
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaMiniDrv.drvFreeDrvItemContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvFreeDrvItemContext


## -description


The <b>IWiaMiniDrv::drvFreeDrvItemContext</b> method frees a device-specific context.


## -parameters




### -param __MIDL__IWiaMiniDrv0056




### -param __MIDL__IWiaMiniDrv0057




### -param __MIDL__IWiaMiniDrv0058






#### - lFlags [in]

Is currently unused.


#### - pSpecContext [in]

Points to a device-specific context. 


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>.






## -remarks



When a driver item is deleted, the WIA service frees the driver item context. This method informs the minidriver that the context is ready to be freed. The minidriver should free any memory that it allocated for the context. For example, in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties">IWiaMiniDrv::drvReadItemProperties</a>, a camera minidriver might allocate a cache to store the thumbnail for an item, and store a pointer to this cache in the driver item context. The minidriver would then free the cache in this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties">IWiaMiniDrv::drvReadItemProperties</a>
 

 

