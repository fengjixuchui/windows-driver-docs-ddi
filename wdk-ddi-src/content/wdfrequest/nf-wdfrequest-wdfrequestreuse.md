---
UID: NF:wdfrequest.WdfRequestReuse
title: WdfRequestReuse function (wdfrequest.h)
description: The WdfRequestReuse method reinitializes a framework request object so that it can be reused.
old-location: wdf\wdfrequestreuse.htm
tech.root: wdf
ms.assetid: 3d649cc5-6512-432c-9bd9-60e18507a873
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_8815216b-4632-4cc8-8afd-c4b1412ddbad.xml, WdfRequestReuse, WdfRequestReuse method, kmdf.wdfrequestreuse, wdf.wdfrequestreuse, wdfrequest/WdfRequestReuse
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestReuse"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqSendFail
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
- WdfRequestReuse
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestReuse function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestReuse</b> method reinitializes a framework request object so that it can be reused.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param ReuseParams [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -returns



<b>WdfRequestReuse</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_WDF_REQUEST_INVALID_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied an IRP in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure, but the specified request object was not obtained from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreatefromirp">WdfRequestCreateFromIrp</a>.

</td>
</tr>
</table>
 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A framework-based driver can reuse framework request objects that it created by previous calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreatefromirp">WdfRequestCreateFromIrp</a>. Drivers can also reuse request objects that they have <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/receiving-i-o-requests">received from the framework</a>, but they cannot set the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ne-wdfrequest-_wdf_request_reuse_flags">WDF_REQUEST_REUSE_SET_NEW_IRP</a> flag for those request objects.

A driver can reuse a request object after the original request has been completed. After a driver has called <b>WdfRequestReuse</b>, the request's contents must be reinitialized. The driver can specify some request parameters in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a> structure. 

If you want the reused request to have a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a> after calling <b>WdfRequestReuse</b>.

For more information about <b>WdfRequestReuse</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reusing-framework-request-objects">Reusing Framework Request Objects</a>.


#### Examples

The following code example is part of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function that calls <b>WdfRequestReuse</b> so that the driver can reuse a driver-allocated request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyRequestCompletionRoutine(
    IN WDFREQUEST  Request,
    IN WDFIOTARGET  Target,
    PWDF_REQUEST_COMPLETION_PARAMS  CompletionParams,
    IN WDFCONTEXT  Context
    )
{
    WDF_REQUEST_REUSE_PARAMS  params;
    NTSTATUS  status;
...
    WDF_REQUEST_REUSE_PARAMS_INIT(
                                  &params,
                                  WDF_REQUEST_REUSE_NO_FLAGS,
                                  STATUS_SUCCESS
                                  );

    status = WdfRequestReuse(
                             Request,
                             &params
                             );
    ASSERT(NT_SUCCESS(status));
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/ns-wdfrequest-_wdf_request_reuse_params">WDF_REQUEST_REUSE_PARAMS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdf_request_reuse_params_init">WDF_REQUEST_REUSE_PARAMS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreatefromirp">WdfRequestCreateFromIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsetcompletionroutine">WdfRequestSetCompletionRoutine</a>
 

 

