---
UID: NF:wia_lh.IWiaImageFilter.InitializeFilter
title: IWiaImageFilter::InitializeFilter (wia_lh.h)
description: The IWiaImageFilter::InitializeFilter method stores the references to pWiaItem2 and pWiaTransferCallback parameters passed into the method.
old-location: image\iwiaimagefilter_initializefilter.htm
tech.root: image
ms.assetid: 03e359aa-4745-4961-a342-79f725468aab
ms.date: 05/03/2018
ms.keywords: IWiaErrorHandler_f9d42d0d-1768-4868-bd41-b20297008312.xml, IWiaImageFilter interface [Imaging Devices],InitializeFilter method, IWiaImageFilter.InitializeFilter, IWiaImageFilter::InitializeFilter, InitializeFilter, InitializeFilter method [Imaging Devices], InitializeFilter method [Imaging Devices],IWiaImageFilter interface, image.iwiaimagefilter_initializefilter, wia_lh/IWiaImageFilter::InitializeFilter
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia_lh.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- IWiaImageFilter.InitializeFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaImageFilter::InitializeFilter


## -description


The <b>IWiaImageFilter::InitializeFilter</b> method stores the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> parameters passed into the method.


## -parameters




### -param pWiaItem2 [in]

Points to the <b>IWiaItem2</b> item that the image acquisition was initiated for by the application. In the case of <b>IWiaTransfer::Download</b>, it is the WIA item from which we obtained the <b>IWiaTransfer</b> interface, and in the case of the Preview component, it is the item that we pass into the <b>IWiaPreview::GetNewPreview</b> method.


### -param pWiaTransferCallback [in]

Points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwiatransfercallback">IWiaTransferCallback</a> interface. The IWiaTransferCallback interface is the application's callback interface, which is passed to <b>IWiaTransfer::Download</b> and <b>IWiaPreview::GetNewPreview</b>. 



## -returns



Returns S_OK on success, or a standard COM error code on failure.






## -remarks



This method is called by the COM proxy object (described in the Microsoft Windows SDK documentation) before the download call reaches the WIA service. This happens in two cases: when an application calls <b>IWiaTransfer::Download</b> method and when an application calls the <b>IWiaPreview::GetNewPreview</b> method. 

All that <b>IWiaImageFilter::InitializeFilter</b> is required to do is to store the references to <i>pWiaItem2</i> and <i>pWiaTransferCallback</i> that are passed into it. These interface pointers should be stored as member variables in this method and <b>AddRef</b> should be called for each interface pointer. These two interface pointers are needed in the filter's implementation of <b>IWiaTransferCallback::TransferCallback</b> and <b>IWiaTransferCallback::GetNextStream</b> methods.

The <b>IWiaTransferCallback</b> and <b>IWiaPreview</b> interfaces are described in the Windows SDK documentation.

This method cannot be invoked directly by the application.

The <b>IWiaItem2, IWiaPreview</b> and <b>IWiaTransfer</b> interfaces are described in the Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwiaimagefilter">IWiaImageFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwiatransfercallback">IWiaTransferCallback Interface</a>
 

 

