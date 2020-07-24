---
UID: NF:wdfrequest.WdfRequestGetInformation
title: WdfRequestGetInformation function (wdfrequest.h)
description: The WdfRequestGetInformation method returns completion status information for a specified I/O request.
old-location: wdf\wdfrequestgetinformation.htm
tech.root: wdf
ms.assetid: fd5f29f7-e9c6-48c4-8704-5db37b8c6337
ms.date: 02/26/2018
keywords: ["WdfRequestGetInformation function"]
ms.keywords: DFRequestObjectRef_ea947de9-aea4-4e66-8686-f4ca5a1385c4.xml, WdfRequestGetInformation, WdfRequestGetInformation method, kmdf.wdfrequestgetinformation, wdf.wdfrequestgetinformation, wdfrequest/WdfRequestGetInformation
f1_keywords:
 - "wdfrequest/WdfRequestGetInformation"
 - "WdfRequestGetInformation"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRequestGetInformation
targetos: Windows
req.typenames: 
---

# WdfRequestGetInformation function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestGetInformation</b> method returns completion status information for a specified I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestGetInformation</b> returns the information that a lower-level driver set by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetinformation">WdfRequestSetInformation</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetinformation">WdfRequestSetInformation</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a> to set completion status information for an I/O request. Your driver can call <b>WdfRequestGetInformation</b> after a lower-level driver completes a request, to obtain completion status information that the lower-level driver set. 

If your driver calls <b>WdfRequestGetInformation</b> after it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> to complete the request, <b>WdfRequestGetInformation</b> returns <b>NULL</b>.

For more information about <b>WdfRequestGetInformation</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Completing I/O Requests</a>.


#### Examples

The following code example sends an I/O request to an I/O target and then obtains status information that the I/O target provided.

```cpp
ULONG_PTR  informationRetrieved = NULL;

status = WdfIoTargetSendWriteSynchronously(
                                           ioTarget,
                                           request,
                                           &outputMemoryDescriptor,
                                           NULL,
                                           NULL,
                                           &bytesWritten
                                           );
if (NT_SUCCESS(status)) {
    informationRetrieved = WdfRequestGetInformation(request);
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetinformation">WdfRequestSetInformation</a>
 

 

