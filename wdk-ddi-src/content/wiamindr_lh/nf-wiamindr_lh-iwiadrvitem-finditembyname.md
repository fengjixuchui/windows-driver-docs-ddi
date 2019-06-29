---
UID: NF:wiamindr_lh.IWiaDrvItem.FindItemByName
title: IWiaDrvItem::FindItemByName (wiamindr_lh.h)
description: The IWiaDrvItem::FindItemByName method locates an item in a driver item tree by the item's full name.
old-location: image\iwiadrvitem_finditembyname.htm
tech.root: image
ms.assetid: 59a77753-1f34-4224-af11-c6bbfa847619
ms.date: 05/03/2018
ms.keywords: DrvItem_d3717889-b428-4dbc-8ef9-c501a52f3328.xml, FindItemByName, FindItemByName method [Imaging Devices], FindItemByName method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],FindItemByName method, IWiaDrvItem.FindItemByName, IWiaDrvItem::FindItemByName, image.iwiadrvitem_finditembyname, wiamindr_lh/IWiaDrvItem::FindItemByName
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
- IWiaDrvItem.FindItemByName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::FindItemByName


## -description


The<b> IWiaDrvItem::FindItemByName</b> method locates an item in a driver item tree by the item's full name.


## -parameters




### -param __MIDL__IWiaDrvItem0007




### -param __MIDL__IWiaDrvItem0008




### -param __MIDL__IWiaDrvItem0009






#### - bstrFullItemName [in]

Specifies the full name of the item to find.


#### - lFlags [in]

Reserved. Set to zero. 


#### - ppItem [out, optional]

Points to a memory location that will receive the address of the found <b>IWiaDrvItem</b> item. 


## -returns



If the method succeeds, it stores a pointer to the found item in <i>ppItem</i> and returns S_OK. If the method fails, it places <b>NULL</b> in <i>ppItem</i> and returns S_FALSE. If this method does not find the required item, it returns S_FALSE. If an error occurred during the search, a standard COM error code will be returned.




## -remarks



Minidrivers call this method to find an item in a driver item tree when the item's full name is known. The item's full name is obtained in the method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname">IWiaDrvItem::GetFullItemName</a>.

This method starts the search for the specified item at the root item in the driver item tree.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-findchilditembyname">IWiaDrvItem::FindChildItemByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfullitemname">IWiaDrvItem::GetFullItemName</a>
 

 

