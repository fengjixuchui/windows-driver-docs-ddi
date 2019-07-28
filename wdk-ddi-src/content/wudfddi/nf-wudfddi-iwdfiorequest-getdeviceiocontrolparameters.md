---
UID: NF:wudfddi.IWDFIoRequest.GetDeviceIoControlParameters
title: IWDFIoRequest::GetDeviceIoControlParameters (wudfddi.h)
description: The GetDeviceIoControlParameters method retrieves the request parameters for a device I/O control-type request.
old-location: wdf\iwdfiorequest_getdeviceiocontrolparameters.htm
tech.root: wdf
ms.assetid: 96de6f7a-da1d-44a6-b1f7-44859312a662
ms.date: 02/26/2018
ms.keywords: GetDeviceIoControlParameters, GetDeviceIoControlParameters method, GetDeviceIoControlParameters method,IWDFIoRequest interface, IWDFIoRequest interface,GetDeviceIoControlParameters method, IWDFIoRequest.GetDeviceIoControlParameters, IWDFIoRequest::GetDeviceIoControlParameters, UMDFRequestObjectRef_8a0fa5cd-af16-4599-8282-4ca0a81591ac.xml, umdf.iwdfiorequest_getdeviceiocontrolparameters, wdf.iwdfiorequest_getdeviceiocontrolparameters, wudfddi/IWDFIoRequest::GetDeviceIoControlParameters
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest.GetDeviceIoControlParameters"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest.GetDeviceIoControlParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetDeviceIoControlParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDeviceIoControlParameters</b> method retrieves the request parameters for a device I/O control-type request.


## -parameters




### -param pControlCode [out]

A pointer to a variable that receives the control code that identifies the specific operation to be performed.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pInBufferSize [out]

A pointer to a variable that receives the size, in bytes, of the input data buffer for the request. To retrieve the input data buffer, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutBufferSize [out]

A pointer to a variable that receives the size, in bytes, of the output data buffer for the request. To retrieve the output data buffer, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a> method.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -remarks



The call to <b>GetDeviceIoControlParameters</b> fails if the request type is not a device I/O control type.

Although the driver can optionally specify <b>NULL</b> for each of the <i>pControlCode</i>, <i>pInBufferSize</i>, and <i>pOutBufferSize</i> parameters, the driver must specify at least one non-<b>NULL</b> parameter for <b>GetDeviceIoControlParameters</b> to execute successfully.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>
 

 

