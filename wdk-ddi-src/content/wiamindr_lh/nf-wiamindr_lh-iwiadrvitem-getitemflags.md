---
UID: NF:wiamindr_lh.IWiaDrvItem.GetItemFlags
title: IWiaDrvItem::GetItemFlags (wiamindr_lh.h)
description: The IWiaDrvItem::GetItemFlags method gets the item flags of the current IWiaDrvItem item.
old-location: image\iwiadrvitem_getitemflags.htm
tech.root: image
ms.assetid: 47358d69-ef45-4cac-8187-72c354912c4e
ms.date: 05/03/2018
ms.keywords: DrvItem_6fcac1f5-c754-4158-a1a0-61efe0d3913c.xml, GetItemFlags, GetItemFlags method [Imaging Devices], GetItemFlags method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetItemFlags method, IWiaDrvItem.GetItemFlags, IWiaDrvItem::GetItemFlags, image.iwiadrvitem_getitemflags, wiamindr_lh/IWiaDrvItem::GetItemFlags
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
- IWiaDrvItem.GetItemFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::GetItemFlags


## -description


The <b>IWiaDrvItem::GetItemFlags</b> method gets the item flags of the current <b>IWiaDrvItem</b> item.


## -parameters




### -param __MIDL__IWiaDrvItem0000






#### - plFlags [out]

Points to a memory location that will receive the item flags.


## -returns



If the method succeeds, it places the item flag values in the location pointed to by <i>plFlags</i> and returns S_OK. If the pointer <i>plFlags</i> is invalid, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.




## -remarks



The method places the current <b>IWiaDrvItem</b> item's flag values in the location pointed to by <i>pIFlags</i>. The item's flag values were set when the item was created by the driver services library function <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatedrvitem">wiasCreateDrvItem</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatedrvitem">wiasCreateDrvItem</a>
 

 

