---
UID: NF:wiamindr_lh.IWiaDrvItem.RemoveItemFromFolder
title: IWiaDrvItem::RemoveItemFromFolder (wiamindr_lh.h)
description: The IWiaDrvItem::RemoveItemFromFolder method removes an item from a parent folder.
old-location: image\iwiadrvitem_removeitemfromfolder.htm
tech.root: image
ms.assetid: f800427e-d6b6-4f4c-aee7-4b2b0d0aa0c4
ms.date: 05/03/2018
ms.keywords: DrvItem_240e14a4-36bd-4a72-b143-6f8f5c220682.xml, IWiaDrvItem interface [Imaging Devices],RemoveItemFromFolder method, IWiaDrvItem.RemoveItemFromFolder, IWiaDrvItem::RemoveItemFromFolder, RemoveItemFromFolder, RemoveItemFromFolder method [Imaging Devices], RemoveItemFromFolder method [Imaging Devices],IWiaDrvItem interface, image.iwiadrvitem_removeitemfromfolder, wiamindr_lh/IWiaDrvItem::RemoveItemFromFolder
ms.topic: method
f1_keywords:
 - "wiamindr_lh/IWiaDrvItem.RemoveItemFromFolder"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
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
- IWiaDrvItem.RemoveItemFromFolder
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::RemoveItemFromFolder

## -description

The **IWiaDrvItem::RemoveItemFromFolder** method removes an item from a parent folder.

## -parameters

### -param __MIDL__IWiaDrvItem0006

lReason [in]

- Specifies the reason for the removal of the item from the folder. This parameter can be set to one of the following values:

  | Value | Meaning |
  | --- | --- |
  | WiaItemTypeDeleted | The item is marked as deleted. |
  | WiaItemTypeDisconnected | The item is a disconnected device. |

#### - lReason [in]

Specifies the reason for the removal of the item from the folder. This parameter can be set to one of the following values:

| Value | Meaning |
| --- | --- |
| WiaItemTypeDeleted | The item is marked as deleted. |
| WiaItemTypeDisconnected | The item is a disconnected device. |

## -returns

If the method succeeds, it returns S_OK. If the item to be removed is a folder and the folder is not empty, the method returns E_INVALIDARG. If *lReason* contains an invalid reason, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## -remarks

After the item has been removed from the folder, it can no longer be used for device access.

## -see-also

[IWiaDrvItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem)

[IWiaDrvItem::AddItemToFolder](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-additemtofolder)
