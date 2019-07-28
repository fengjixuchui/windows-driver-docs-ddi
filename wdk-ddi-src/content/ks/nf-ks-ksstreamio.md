---
UID: NF:ks.KsStreamIo
title: KsStreamIo function (ks.h)
description: The KsStreamIo function performs a stream read or write against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates a read or write request against the device object.
old-location: stream\ksstreamio.htm
tech.root: stream
ms.assetid: 74c62a30-42b9-4ea7-b52a-014e263d886e
ms.date: 04/23/2018
ms.keywords: KsStreamIo, KsStreamIo function [Streaming Media Devices], ks/KsStreamIo, ksfunc_c2f256a3-f01a-45e1-b7de-1eed5bacde7a.xml, stream.ksstreamio
ms.topic: function
f1_keywords:
 - "ks/KsStreamIo"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsStreamIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsStreamIo function


## -description


The <b>KsStreamIo</b> function performs a stream read or write against the specified file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates a read or write request against the device object.


## -parameters




### -param FileObject [in]

Specifies the file object to perform the I/O against.


### -param Event [in, optional]

Optionally contains the event to use in the I/O. If none is passed, the call is assumed to be on a synchronous file object or the caller is waiting for the file object's event, or else it can be asynchronously completed. If used, and the KSSTREAM_SYNCHRONOUS flag is not set, this must be an event allocated by the object manager. If the caller is performing asynchronous I/O, it must either wait for the file object's event or pass an event in this parameter and wait for it. If this is not done, then there is no way for the caller to know when the IoStatusBlock has been updated by the call.


### -param PortContext [in, optional]

Optionally contains context information for a completion port.


### -param CompletionRoutine [in, optional]

Optionally points to a completion routine for this IRP.


### -param CompletionContext [in, optional]

If <i>CompletionRoutine</i> is specified, this provides a context pointer in the completion routine callback.


### -param OPTIONAL




### -param IoStatusBlock [out]

Location to return the status information. This is always assumed to be a valid address, regardless of the requester mode. The value must remain valid until the call has updated the status. The caller must either perform synchronous I/O or must wait for the file object's event or an event passed in the Event parameter before allowing this address to become invalid.


### -param StreamHeaders [in, out]

Specifies the list of stream headers. This address, as well as the addresses of the data buffers, are assumed to have been probed for appropriate access. Kernel-mode clients submitting streaming headers must allocate the headers from NonPagedPool memory.


### -param Length [in]

Specifies the size of the <i>StreamHeaders</i> passed.


### -param Flags [in]

Specifies various flags for the I/O. See the following table for the values used.


### -param RequestorMode [in]

Indicates the processor mode to place in the IRP if one is needs to be generated. This variable also determines if a fast I/O call can be performed. If the requester mode is not kernel mode, but the previous mode is, then fast I/O cannot be used.


#### - CompletionInvocationFlags [in, optional]

Specifies invocation flags specifying when the completion routine is invoked. See following table for the values used.


## -returns



The <b>KsStreamIo</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or if unsuccessful it returns an I/O error.




## -remarks



The following enumerated values are used for the <i>CompletionInvocationFlags</i> variable and are of type KSCOMPLETION_INVOCATION:

<table>
<tr>
<th><i>CompletionInvocationFlags</i>
       Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KsInvokeOnSuccess

</td>
<td>
Invokes the completion routine on success.

</td>
</tr>
<tr>
<td>
KsInvokeOnError

</td>
<td>
Invokes the completion routine on error.

</td>
</tr>
<tr>
<td>
KsInvokeOnCancel

</td>
<td>
Invokes the completion routine on cancellation.

</td>
</tr>
</table>
 

The following defined values are used for the <i>Flags</i> variable:

<table>
<tr>
<th><i>Flags</i>  Values</th>
<th>Description</th>
</tr>
<tr>
<td>
KSSTREAM_READ

</td>
<td>
Specifies that an IOCTL_KS_STREAMREAD IRP is to be built. This is the default.

</td>
</tr>
<tr>
<td>
KSSTREAM_WRITE

</td>
<td>
Specifies that an IOCTL_KS_STREAMWRITE IRP is to be built.

</td>
</tr>
<tr>
<td>
KSSTREAM_PAGED_DATA

</td>
<td>
Specifies that the data is pageable. This is the default and can be used at all times.

</td>
</tr>
<tr>
<td>
KSSTREAM_NONPAGED_DATA

</td>
<td>
Specifies that the data is nonpaged and can be used as a performance enhancement.

</td>
</tr>
<tr>
<td>
KSSTREAM_SYNCHRONOUS

</td>
<td>
Specifies that the IRP is synchronous. This means that if the <i>Event</i> parameter is passed, it is not treated as an object manager event and is not referenced or dereferenced.

</td>
</tr>
</table>
 

KSSTREAM_READ is equivalent to KSPROBE_STREAMREAD.

Similarly, KSSTREAM_WRITE is equivalent to KSPROBE_STREAMWRITE.



