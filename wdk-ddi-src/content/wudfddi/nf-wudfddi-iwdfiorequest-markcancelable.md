---
UID: NF:wudfddi.IWDFIoRequest.MarkCancelable
title: IWDFIoRequest::MarkCancelable (wudfddi.h)
description: The MarkCancelable method enables the canceling of the I/O request.
old-location: wdf\iwdfiorequest_markcancelable.htm
tech.root: wdf
ms.assetid: 73e323a4-d40e-4414-92b7-310bfb0f6457
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest interface,MarkCancelable method, IWDFIoRequest.MarkCancelable, IWDFIoRequest::MarkCancelable, MarkCancelable, MarkCancelable method, MarkCancelable method,IWDFIoRequest interface, UMDFRequestObjectRef_c1304e95-724d-4ced-abc2-801b1606f43b.xml, umdf.iwdfiorequest_markcancelable, wdf.iwdfiorequest_markcancelable, wudfddi/IWDFIoRequest::MarkCancelable
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest.MarkCancelable"
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
- IWDFIoRequest.MarkCancelable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::MarkCancelable


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>MarkCancelable</b> method enables the canceling of the I/O request.


## -parameters




### -param pCancelCallback [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackcancel">IRequestCallbackCancel</a> interface whose method the framework calls after the I/O request is canceled.


## -remarks



After a driver receives an I/O request as input to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackread-onread">IQueueCallbackRead::OnRead</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackdeviceiocontrol-ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> event callback function, the driver can call the <b>MarkCancelable</b> method to enable canceling of the request. Later, the driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a> method to disable canceling of the request. 

Before a driver calls <b>MarkCancelable</b>, the driver must implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method. 

The User Mode Driver Framework (UMDF) allows only one <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method per queue. Therefore, when a driver calls <b>MarkCancelable</b> for requests that are associated with a particular queue to enable the framework to cancel those requests, the driver must pass a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackcancel">IRequestCallbackCancel</a> interface for the same request-callback object. Later, to cancel each request, the framework passes a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the request in a call to this request-callback object's <b>IRequestCallbackCancel::OnCancel</b> method.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a>, either from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a> method or from its regular I/O completion path.

After a driver calls <b>MarkCancelable</b> to enable canceling, the request remains cancelable while the driver has possession of the request object, unless the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">UnmarkCancelable</a> to disable canceling. 

If the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a> method to forward the request to a different queue, the following rules apply: 

<ul>
<li>
Canceling of I/O requests cannot be enabled when the driver forwards the requests to a different queue. 

Typically, the driver should not call <b>MarkCancelable</b> to enable canceling a request before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a>. Alternatively, the driver can make the request cancelable. However, the driver must then call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">UnmarkCancelable</a> to disable canceling the request before calling <b>IWDFIoRequest::ForwardToIoQueue</b>. 

</li>
<li>
While the request is in a second queue, the framework owns it and can cancel it without notifying the driver. 

</li>
<li>
After the framework dequeues the request from the second queue and delivers the request to the driver, the driver can call <b>MarkCancelable</b> to enable canceling.

</li>
</ul>

#### Examples

The following code example sets up a request so that the framework can cancel it.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    //
    // The QueryInteraface should not fail.
    //
    (VOID)this->QueryInterface(_uuidof(IRequestCallbackCancel),
                               (PVOID *)&cancelCallback);

    pWdfRequest->MarkCancelable(cancelCallback);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackdeviceiocontrol-ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackread-onread">IQueueCallbackRead::OnRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-irequestcallbackcancel">IRequestCallbackCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-irequestcallbackcancel-oncancel">IRequestCallbackCancel::OnCancel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-complete">IWDFIoRequest::Complete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-forwardtoioqueue">IWDFIoRequest::ForwardToIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-unmarkcancelable">IWDFIoRequest::UnmarkCancelable</a>
 

 

