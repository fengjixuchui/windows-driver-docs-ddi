---
UID: NF:wia_lh.IWiaTransferCallback.GetNextStream
title: IWiaTransferCallback::GetNextStream (wia_lh.h)
description: The IWiaTransferCallback::GetNextStream method is implemented by an image processing filter.
old-location: image\iwiatransfercallback_getnextstream.htm
tech.root: image
ms.assetid: 025c29d3-1167-4aa3-8399-01dab5729267
ms.date: 05/03/2018
ms.keywords: GetNextStream, GetNextStream method [Imaging Devices], GetNextStream method [Imaging Devices],IWiaTransferCallback interface, IWiaTransferCallback interface [Imaging Devices],GetNextStream method, IWiaTransferCallback.GetNextStream, IWiaTransferCallback::GetNextStream, IWiaTransfercallback_155c3198-1ed9-46a9-b6d8-0d6029bf0803.xml, image.iwiatransfercallback_getnextstream, wia_lh/IWiaTransferCallback::GetNextStream
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia.h
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
- wia_lh.h
api_name:
- IWiaTransferCallback.GetNextStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaTransferCallback::GetNextStream


## -description


The <b>IWiaTransferCallback::GetNextStream</b> method is implemented by an image processing filter. It is called by the WIA service as a result of an application calling <b>IWiaTransfer::Download</b> or the preview component's <b>IWiaPreview::GetNewPreview</b>. The <b>IWiaTransfer</b> and <b>IWiaPreview</b> interfaces are described in the Microsoft Windows SDK documentation.


## -parameters




### -param lFlags [in]

Is reserved. Set to zero. 


### -param bstrItemName [in]

Specifies a string containing the name of the item.


### -param bstrFullItemName [in]

Specifies a string containing the full name of the item. 


### -param ppDestination [out]

Specifies a pointer to the output stream. 


## -returns



Returns S_OK if successful, or a standard COM error value otherwise. 




## -remarks



An image processing filter's implementation of <b>IWiaTransferCallback::GetNextStream</b> and <b>IWiaTransferCallback::TransferCallback</b> are called during image acquisition, when the WIA mini-driver asks for the destination stream from the client and when the mini-driver sends progress messages back to the application.

An image processing filter's implementation of <b>IWiaTransferCallback::GetNextStream</b> must delegate to the application's <b>IWiaTransferCallback::GetNextStream</b> method. The image processing filter then uses the stream returned by the application callback's <b>IWiaTransferCallback::GetNextStream</b> implementation to create its own stream (the "filtering stream") that it passes back to the WIA service. 

In its <b>IWiaTransferCallback::GetNextStream</b> implementation, the image processing filter should read which properties are needed for its image processing from the item for which the image is being acquired. The filter must not read the properties directly from the <i>pWiaItem2</i> passed into <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaimagefilter-initializefilter">IWiaImageFilter::InitializeFilter</a>; rather it must call <b>IWiaItem2::FindItemByName </b>(described in the Windows SDK documentation) on this WIA item to obtain the actual WIA item. The reason is that during a folder transfer the images acquired correspond to the child items of <i>pWiaItem2</i> rather than to <i>pWiaItem2</i> itself. 


<div class="alert"><b>Note</b>    This method is not called by the preview component during <b>IWiaPreview::UpdatePreview</b>.</div>
<div> </div>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nf-wia_lh-iwiaimagefilter-initializefilter">IWiaImageFilter::InitializeFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwiatransfercallback">IWiaTransferCallback</a>
 

 

