---
UID: NF:netrequest.NetRequestMethodComplete
title: NetRequestMethodComplete function (netrequest.h)
description: Completes a method (OID) request.
tech.root: netvista
ms.assetid: 5f846a1d-3de6-44d8-9aa0-0111962cdc57
ms.date: 02/08/2018
keywords: ["NetRequestMethodComplete function"]
f1_keywords:
 - "netrequest/NetRequestMethodComplete"
ms.keywords: NetRequestMethodComplete
req.header: netrequest.h
req.include-header: netadaptercx.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.lib:
req.dll:
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
req.alt-api:
req.alt-loc:
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netrequest.h
api_name: 
- NetRequestMethodComplete
targetos: Windows
product:
- Windows
---

# NetRequestMethodComplete function


## -description



Completes a method (OID) request.

## -parameters

### -param Request
A handle to a network request object.

### -param CompletionStatus
An NTSTATUS value that represents the completion status of the request. Valid status values include, but are not limited to, the following:

| Return code | Description |
| --- | --- |
| STATUS_SUCCESS | The driver successfully completed the request. |
| STATUS_CANCELLED | The driver canceled the request. |
| STATUS_UNSUCCESSFUL | The driver encountered an error while processing the request. |

### -param BytesRead
The number of bytes that the client driver read from the request buffer.

### -param BytesWritten
The number of bytes that the client driver wrote to the request buffer.

## -remarks
Typically, the client driver calls **NetRequestMethodComplete** from one of its control request handler routines. For more info, see [Handling Control Requests](https://docs.microsoft.com/windows-hardware/drivers/netcx/handling-control-requests#completing-requests).

After this method returns, the request handle is no longer valid. NetAdapterCx removes it from the NETQUEUE and deletes the NETREQUEST object.



## -see-also

[NetRequestCompleteWithoutInformation](nf-netrequest-netrequestcompletewithoutinformation.md)

[NetRequestQueryDataComplete](nf-netrequest-netrequestquerydatacomplete.md)

[NetRequestSetDataComplete](nf-netrequest-netrequestsetdatacomplete.md)
