---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvGetCapabilities
title: IWiaMiniDrv::drvGetCapabilities (wiamindr_lh.h)
description: The IWiaMiniDrv::drvGetCapabilities method returns an array of events and commands that a device supports.
old-location: image\iwiaminidrv_drvgetcapabilities.htm
tech.root: image
ms.assetid: 946a6ea7-5818-4959-adf2-3568c1b64b1a
ms.date: 05/03/2018
ms.keywords: IWiaMiniDrv interface [Imaging Devices],drvGetCapabilities method, IWiaMiniDrv.drvGetCapabilities, IWiaMiniDrv::drvGetCapabilities, MiniDrv_c88a03f8-d527-47b0-953c-a7bf231c733e.xml, drvGetCapabilities, drvGetCapabilities method [Imaging Devices], drvGetCapabilities method [Imaging Devices],IWiaMiniDrv interface, image.iwiaminidrv_drvgetcapabilities, wiamindr_lh/IWiaMiniDrv::drvGetCapabilities
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
- IWiaMiniDrv.drvGetCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrv::drvGetCapabilities


## -description


The <b>IWiaMiniDrv::drvGetCapabilities</b> method returns an array of events and commands that a device supports.


## -parameters




### -param __MIDL__IWiaMiniDrv0048




### -param __MIDL__IWiaMiniDrv0049




### -param __MIDL__IWiaMiniDrv0050




### -param __MIDL__IWiaMiniDrv0051




### -param __MIDL__IWiaMiniDrv0052






#### - lFlags [in]

Specifies whether the array pointed to by <i>ppCapabilites</i> consists of commands, or events, or both. This parameter can be either of the following flags or of both of them combined by an OR operator.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WIA_DEVICE_COMMANDS

</td>
<td>
The array consists of device commands.

</td>
</tr>
<tr>
<td>
WIA_DEVICE_EVENTS

</td>
<td>
The array consists of device events.

</td>
</tr>
</table>
 


#### - pWiasContext [in]

Pointer to a WIA item context.


#### - pcelt [out]

Points to a memory location that will receive the number of elements in the array pointed to by the <i>ppCapabilities</i> parameter.


#### - plDevErrVal [out]

Points to a memory location that will receive a status code for this method. If this method returns S_OK, the value stored will be zero. Otherwise, a minidriver-specific error code will be stored at the location pointed to by this parameter.


#### - ppCapabilities [out, optional]

Points to a memory location that will receive the address of the first element of an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_dev_cap_drv">WIA_DEV_CAP_DRV</a> structures that contain the GUIDs of events and commands that the device supports. 


## -returns



On success, the method should return S_OK and clear the device error value pointed to by <i>plDevErrVal</i>. If the method fails, it should return a standard COM error code and place a minidriver-specific error code value in the memory pointed to by <i>plDevErrVal</i>. 

The value pointed to by <i>plDevErrVal</i> can be converted to a string by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>.




## -remarks



The WIA service calls the minidriver method <b>IWiaMiniDrv::drvGetCapabilities</b> to obtain a list of hardware command capabilities and/or device events. In response to this call, a minidriver sets <i>ppCapabilities</i> with the address of an array of pointers to GUID data. Each GUID corresponds to an event notification or a device command supported by the imaging device. When the <i>lFlags</i> parameter is set to WIA_DEVICE_COMMANDS, the array of GUIDs contains device commands. When <i>lFlags</i> is set to WIA_DEVICE_EVENTS, the array of GUIDs contains events. If <i>lFlags</i> is set to WIA_DEVICE_COMMANDS | WIA_DEVICE_EVENTS, the array of GUIDs contains both events and commands, listed in that order.

The <i>Wiadef.h</i> header lists several predefined commands and events.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiaminidrv">IWiaMiniDrv</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetdeviceerrorstr">IWiaMiniDrv::drvGetDeviceErrorStr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/ns-wiamindr_lh-_wia_dev_cap_drv">WIA_DEV_CAP_DRV</a>
 

 

