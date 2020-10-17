---
UID: NF:wdfrequest.WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
title: WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function (wdfrequest.h)
description: The WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function sets a time-out value in a driver's WDF_REQUEST_SEND_OPTIONS structure.
old-location: wdf\wdf_request_send_options_set_timeout.htm
tech.root: wdf
ms.assetid: 729bd44f-9ac7-4b3d-905d-a78b10fba2a7
ms.date: 02/26/2018
keywords: ["WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function"]
ms.keywords: DFRequestObjectRef_bcbdd786-6d81-45f7-a70b-96e781da0d36.xml, WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT, WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function, kmdf.wdf_request_send_options_set_timeout, wdf.wdf_request_send_options_set_timeout, wdfrequest/WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
 - wdfrequest/WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfrequest.h
api_name:
 - WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT
---

# WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> function sets a time-out value in a driver's <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

## -parameters

### -param Options 

[in, out]
A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

### -param Timeout 

[in]
An absolute or relative time-out value. For more information, see the <b>Timeout</b> member of the <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure.

## -remarks

To set a time-out value, your driver must call <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> after it calls <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_send_options_init">WDF_REQUEST_SEND_OPTIONS_INIT</a>.

The <b>WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT</b> function stores the specified timeout value in the specified <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure's <b>Timeout</b> member. It also sets the <b>WDF_REQUEST_SEND_OPTION_TIMEOUT</b> flag in the structure's <b>Flags</b> member.


#### Examples

The following code example initializes a <a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure and sets a time-out value for the structure. (The example calls <a href="/windows-hardware/drivers/ddi/wdfcore/nf-wdfcore-wdf_rel_timeout_in_sec">WDF_REL_TIMEOUT_IN_SEC</a> to specify a relative time-out value of 10 seconds.) The example then uses the <b>WDF_REQUEST_SEND_OPTIONS</b> structure as input to <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipewritesynchronously">WdfUsbTargetPipeWriteSynchronously</a>.

```cpp
WDF_REQUEST_SEND_OPTIONS  syncReqOptions;

WDF_REQUEST_SEND_OPTIONS_INIT(
                              &syncReqOptions,
                              0
                              );
WDF_REQUEST_SEND_OPTIONS_SET_TIMEOUT(
                                     &syncReqOptions,
                                     WDF_REL_TIMEOUT_IN_SEC(10)
                                     );
status = WdfUsbTargetPipeWriteSynchronously(
                                            pipeHandle,
                                            NULL,
                                            &syncReqOptions,
                                            &writeBufDesc,
                                            NULL
                                            );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdf_request_send_options_init">WDF_REQUEST_SEND_OPTIONS_INIT</a>