---
UID: NF:wudfddi.IWDFIoRequest2.GetEffectiveIoType
title: IWDFIoRequest2::GetEffectiveIoType (wudfddi.h)
description: The GetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the IWDFIoRequest2 interface represents.
old-location: wdf\iwdfiorequest2_geteffectiveiotype.htm
tech.root: wdf
ms.assetid: 76909efd-99ca-4e47-9c81-8a48608c2543
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::GetEffectiveIoType"]
ms.keywords: GetEffectiveIoType, GetEffectiveIoType method, GetEffectiveIoType method,IWDFIoRequest2 interface, IWDFIoRequest2 interface,GetEffectiveIoType method, IWDFIoRequest2.GetEffectiveIoType, IWDFIoRequest2::GetEffectiveIoType, UMDFRequestObjectRef_cfea225a-09a5-4aed-8576-de9c44c18b81.xml, umdf.iwdfiorequest2_geteffectiveiotype, wdf.iwdfiorequest2_geteffectiveiotype, wudfddi/IWDFIoRequest2::GetEffectiveIoType
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest2::GetEffectiveIoType
 - wudfddi/IWDFIoRequest2::GetEffectiveIoType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2.GetEffectiveIoType
---

# IWDFIoRequest2::GetEffectiveIoType


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetEffectiveIoType</b> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a> interface represents.

## -returns

<b>GetEffectiveIoType</b> returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers.

## -remarks

For more information about accessing data buffers and when your driver should use <b>GetEffectiveIoType</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackwrite-onwrite">IQueueCallbackWrite::OnWrite</a> callback function can obtain the buffer access method of an I/O request. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnWrite(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in SIZE_T BytesToWrite
    )
{
    WDF_DEVICE_IO_TYPE currentIoType;

    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = pWdfRequest;

    currentIoType = r2->GetEffectiveIoType();
...
}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_device_io_type">WDF_DEVICE_IO_TYPE (UMDF)</a>

