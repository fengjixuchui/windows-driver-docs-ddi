---
UID: NF:wudfddi.IWDFIoRequest3.RetrieveActivityId
title: IWDFIoRequest3::RetrieveActivityId (wudfddi.h)
description: The RetrieveActivityId method retrieves the current activity identifier associated with an I/O request.
old-location: wdf\iwdfiorequest3_retrieveactivityid.htm
tech.root: wdf
ms.assetid: A90FCF3C-B648-4E97-887E-FCE58D7FA13A
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest3 interface,RetrieveActivityId method, IWDFIoRequest3.RetrieveActivityId, IWDFIoRequest3::RetrieveActivityId, RetrieveActivityId, RetrieveActivityId method, RetrieveActivityId method,IWDFIoRequest3 interface, umdf.iwdfiorequest3_retrieveactivityid, wdf.iwdfiorequest3_retrieveactivityid, wudfddi/IWDFIoRequest3::RetrieveActivityId
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequest3.RetrieveActivityId"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
- IWDFIoRequest3.RetrieveActivityId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest3::RetrieveActivityId


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>RetrieveActivityId</b> method retrieves the current activity identifier associated with an I/O request.


## -parameters




### -param ActivityId [out]

A pointer to a location to store the retrieved GUID.


## -returns



<b>RetrieveActivityId</b> returns S_OK if the call is successful. Otherwise, this method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32   (ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request.

</td>
</tr>
</table>
 




## -remarks



Requests reflected from kernel mode have an activity identifier available only if the Kernel Trace provider is enabled or if the UMDF driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setactivityid">IWDFIoRequest3::SetActivityId</a> after receiving the request. For more information about Event Tracing for Windows (ETW), see <a href="https://docs.microsoft.com/windows/desktop/ETW/event-tracing-portal">Event Tracing</a>.

Requests initiated by the UMDF driver have an activity identifier available only if the UMDF driver previously called  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setactivityid">IWDFIoRequest3::SetActivityId</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-reuse">IWdfIoRequest2::Reuse</a>.

For more information about activity identifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-activity-identifiers">Using Activity Identifiers</a>.

The UMDF 2 equivalent of this method is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveactivityid">WdfRequestRetrieveActivityId</a>.


#### Examples

The following code example shows a driver can retrieve an  activity identifier from one request and then use it to set the activity identifier for another request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>hrQI = pWdfRequest->QueryInterface(IID_PPV_ARGS(&pOriginalRequest3));
ASSERT(SUCCEEDED(hrQI));

hrQI = pNewRequest->QueryInterface(IID_PPV_ARGS(&pNewRequest3));
ASSERT(SUCCEEDED(hrQI));

//
// Obtain activity id from original request and set in the new one
//

pOriginalRequest3->RetrieveActivityId(&activityId);
pNewRequest3->SetActivityId(&activityId);

pOriginalRequest3->Release();
pNewRequest3->Release();

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest3">IWDFIoRequest3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest3-setactivityid">IWDFIoRequest3::SetActivityId</a>
 

 

