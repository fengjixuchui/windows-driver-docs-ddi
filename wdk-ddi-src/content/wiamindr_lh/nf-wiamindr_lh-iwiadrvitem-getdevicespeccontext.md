---
UID: NF:wiamindr_lh.IWiaDrvItem.GetDeviceSpecContext
title: IWiaDrvItem::GetDeviceSpecContext (wiamindr_lh.h)
description: The IWiaDrvItem::GetDeviceSpecContext method gets a device-specific context.
old-location: image\iwiadrvitem_getdevicespeccontext.htm
tech.root: image
ms.assetid: 04f8d7ef-43c6-43b7-afa1-06ae379a8e26
ms.date: 05/03/2018
ms.keywords: DrvItem_c9edf09c-212c-456c-9eb2-c6c87adf59f3.xml, GetDeviceSpecContext, GetDeviceSpecContext method [Imaging Devices], GetDeviceSpecContext method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetDeviceSpecContext method, IWiaDrvItem.GetDeviceSpecContext, IWiaDrvItem::GetDeviceSpecContext, image.iwiadrvitem_getdevicespeccontext, wiamindr_lh/IWiaDrvItem::GetDeviceSpecContext
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
- COM
api_location:
- wiamindr_lh.h
api_name:
- IWiaDrvItem.GetDeviceSpecContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::GetDeviceSpecContext


## -description


The<b> IWiaDrvItem::GetDeviceSpecContext</b> method gets a device-specific context.


## -parameters




### -param __MIDL__IWiaDrvItem0001






#### - ppSpecContext [out, optional]

Points to a memory location that will receive the address of a device-specific context.


## -returns



If the method succeeds, it stores a pointer to the device-specific context in <i>ppSpecContext</i> and returns S_OK. If the method fails because the parameter <i>ppSpecContext</i> specifies an invalid pointer, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.




## -remarks



Minidrivers typically use this method to obtain a pointer to a device-specific context associated with an <b>IWiaDrvItem</b> item. The device-specific context is associated with the item when the item is created using the driver services library function <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatedrvitem">wiasCreateDrvItem</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatedrvitem">wiasCreateDrvItem</a>
 

 

