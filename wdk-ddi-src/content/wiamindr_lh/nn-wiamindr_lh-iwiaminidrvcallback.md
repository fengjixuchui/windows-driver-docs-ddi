---
UID: NN:wiamindr_lh.IWiaMiniDrvCallBack
title: IWiaMiniDrvCallBack (wiamindr_lh.h)
description: The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.
old-location: image\iwiaminidrvcallback_interface.htm
tech.root: image
ms.assetid: cf2460c5-325f-43c3-a1fe-5b6982234194
ms.date: 05/03/2018
ms.keywords: CallBack_2e94f80e-dde0-4289-8911-a769a909b4d8.xml, IWiaMiniDrvCallBack, IWiaMiniDrvCallBack interface [Imaging Devices], IWiaMiniDrvCallBack interface [Imaging Devices],described, image.iwiaminidrvcallback_interface, wiamindr_lh/IWiaMiniDrvCallBack
ms.topic: interface
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
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
- IWiaMiniDrvCallBack
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaMiniDrvCallBack interface


## -description


The <b>IWiaMiniDrvCallBack</b> interface provides the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback">MiniDrvCallback</a> method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.

This method can also convey status information, such as the percentage of data transferred.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWiaMiniDrvCallBack</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWiaMiniDrvCallBack</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWiaMiniDrvCallBack</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback">MiniDrvCallback</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback">MiniDrvCallback</a> method provides a callback method for WIA minidrivers to use during a callback data transfer.

</td>
</tr>
</table> 

