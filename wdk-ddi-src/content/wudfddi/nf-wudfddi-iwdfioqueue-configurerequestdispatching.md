---
UID: NF:wudfddi.IWDFIoQueue.ConfigureRequestDispatching
title: IWDFIoQueue::ConfigureRequestDispatching (wudfddi.h)
description: The ConfigureRequestDispatching method configures the queuing of I/O requests of the given type.
old-location: wdf\iwdfioqueue_configurerequestdispatching.htm
tech.root: wdf
ms.assetid: 376b0cc3-8189-499e-ad7f-5844f8cb4221
ms.date: 02/26/2018
keywords: ["IWDFIoQueue::ConfigureRequestDispatching"]
ms.keywords: ConfigureRequestDispatching, ConfigureRequestDispatching method, ConfigureRequestDispatching method,IWDFIoQueue interface, IWDFIoQueue interface,ConfigureRequestDispatching method, IWDFIoQueue.ConfigureRequestDispatching, IWDFIoQueue::ConfigureRequestDispatching, UMDFQueueObjectRef_8aab2e0a-7864-4a37-abba-2807327dd4dc.xml, umdf.iwdfioqueue_configurerequestdispatching, wdf.iwdfioqueue_configurerequestdispatching, wudfddi/IWDFIoQueue::ConfigureRequestDispatching
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoQueue::ConfigureRequestDispatching
 - wudfddi/IWDFIoQueue::ConfigureRequestDispatching
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoQueue.ConfigureRequestDispatching
---

# IWDFIoQueue::ConfigureRequestDispatching


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ConfigureRequestDispatching</b> method configures the queuing of I/O requests of the given type.

## -parameters

### -param RequestType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>-typed value that identifies the request type to be queued. The only valid values are <b>WdfRequestCreate</b>, <b>WdfRequestRead</b>, <b>WdfRequestWrite</b>, and <b>WdfRequestDeviceIoControl</b>.

### -param Forward 

[in]
A BOOL value that specifies whether requests of the specified type are queued. <b>TRUE</b> indicates to enable queuing requests; <b>FALSE</b> indicates to disable queuing requests.

## -returns

<b>ConfigureRequestDispatching</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

The driver can call the <b>ConfigureRequestDispatching</b> method multiple times to configure how each request type is dispatched to the I/O queue. 


#### Examples

The following code example shows how to configure forwarding for IOCTL requests.


```
    //
    // Configure forwarding for IOCTL requests
    //
    HRESULT hr = m_FxQueue->ConfigureRequestDispatching(
                                                        WdfRequestDeviceIoControl,
                                                        true
                                                        );

```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfioqueue">IWDFIoQueue</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/ne-wdfrequest-_wdf_request_type">WDF_REQUEST_TYPE</a>