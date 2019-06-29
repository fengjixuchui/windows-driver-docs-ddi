---
UID: NF:wiamdef.wiasCreateDrvItem
title: wiasCreateDrvItem function (wiamdef.h)
description: The wiasCreateDrvItem function creates an IWiaDrvItem Interface object.
old-location: image\wiascreatedrvitem.htm
tech.root: image
ms.assetid: bc91133a-ae6a-447a-8519-65fbe2929521
ms.date: 05/03/2018
ms.keywords: image.wiascreatedrvitem, wiamdef/wiasCreateDrvItem, wiasCreateDrvItem, wiasCreateDrvItem function [Imaging Devices], wiasFncs_9bede31d-0ac0-4cc7-bdd5-7734e5f82dfc.xml
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasCreateDrvItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasCreateDrvItem function


## -description


The <b>wiasCreateDrvItem </b>function creates an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem Interface</a> object.


## -parameters




### -param lObjectFlags

Specifies the object item type, which must be WiaItemTypeFolder or WiaItemTypeFile (possibly the bitwise OR of these). These flags are described in the Microsoft Windows SDK documentation.


### -param bstrItemName

Specifies a string that contains the item name without path information.


### -param bstrFullItemName

Specifies a string that contains the item name with path information.


### -param pIMiniDrv [in, out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv Interface</a> of the current minidriver.


### -param cbDevSpecContext

Specifies the size in bytes of the device specific context.


### -param ppDevSpecContext [out]

Pointer to a memory location that receives the address of the device specific context. Set this to <b>NULL</b> if the information is not needed.


### -param ppIWiaDrvItem [out]

Pointer to a memory location that receives the address of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem Interface</a> for the newly created <b>IWiaDrvItem</b> object.


## -returns



On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).




## -remarks



This function creates and initializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/image/iwiadrvitem-com-interface">IWiaDrvItem COM Interface</a> object with the specified name and attributes. It also creates a context for the <b>IWiaDrvItem</b> object. Minidrivers typically use this function to build a tree of device items.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiascreatechildappitem">wiasCreateChildAppItem</a>
 

 

