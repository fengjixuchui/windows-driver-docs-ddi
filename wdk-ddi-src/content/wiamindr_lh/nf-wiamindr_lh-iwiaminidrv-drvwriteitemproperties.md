---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvWriteItemProperties
title: IWiaMiniDrv::drvWriteItemProperties (wiamindr_lh.h)
description: The IWiaMiniDrv::drvWriteItemProperties method writes driver item properties to a WIA hardware device.
old-location: image\iwiaminidrv_drvwriteitemproperties.htm
tech.root: image
ms.assetid: 350cb7f6-499f-4fbc-b5c0-6f4daf2a2af0
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvWriteItemProperties method, IWiaMiniDrv.drvWriteItemProperties, IWiaMiniDrv::drvWriteItemProperties, MiniDrv_9296f23a-679c-48e0-b594-ece8a1030e50.xml, drvWriteItemProperties, drvWriteItemProperties method [Imaging Devices], drvWriteItemProperties method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvwriteitemproperties, wiamindr_lh/IWiaMiniDrv::drvWriteItemProperties
ms.topic: method
f1_keywords:
 - "wiamindr_lh/IWiaMiniDrv.drvWriteItemProperties"
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
- IWiaMiniDrv.drvWriteItemProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvWriteItemProperties

## -description

The **IWiaMiniDrv::drvWriteItemProperties** method writes driver item properties to a WIA hardware device.

## -parameters

### -param __MIDL__IWiaMiniDrv0021

lFlags [in]

- Is currently unused.

### -param __MIDL__IWiaMiniDrv0022

pWiasContext [in]

- Pointer to a WIA item context.

### -param __MIDL__IWiaMiniDrv0023

plDevErrVal [out]

- Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

### -param __MIDL__IWiaMiniDrv0024

pmdtc [in]

- Points to a [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure containing the device transfer context.

#### - lFlags [in]

Is currently unused.

#### - pWiasContext [in]

Pointer to a WIA item context.

#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.

#### - pmdtc [in]

Points to a [MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context) structure containing the device transfer context.

## -returns

On success, the method should return S_OK and clear the device error value pointed to by *plDevErrVal*. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by *plDevErrVal*.

The value pointed to by *plDevErrVal* can be converted to a string by calling [IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr).

## -see-also

[IWiaMiniDrv](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv)

[IWiaMiniDrv::drvGetDeviceErrorStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr)

[IWiaMiniDrv::drvReadItemProperties](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvreaditemproperties)

[MINIDRV_TRANSFER_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_minidrv_transfer_context)

[wiasGetRootItem](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasgetrootitem)

[wiasReadMultiple](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadmultiple)

[wiasReadPropBin](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadpropbin)

[wiasReadPropFloat](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadpropfloat)

[wiasReadPropGuid](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadpropguid)

[wiasReadPropLong](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadproplong)

[wiasReadPropStr](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wiasreadpropstr)
