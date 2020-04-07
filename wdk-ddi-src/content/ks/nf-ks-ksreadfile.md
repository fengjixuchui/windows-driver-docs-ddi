---
UID: NF:ks.KsReadFile
title: KsReadFile function (ks.h)
description: The KsReadFile function performs a read against the specified file object.
old-location: stream\ksreadfile.htm
tech.root: stream
ms.assetid: e3bb6ead-8129-4605-8755-3a56d4b3d8f6
ms.date: 04/23/2018
keywords: ["KsReadFile function"]
ms.keywords: KsReadFile, KsReadFile function [Streaming Media Devices], ks/KsReadFile, ksfunc_9264bdad-2acc-46fe-9ca3-d006bf6c3e23.xml, stream.ksreadfile
f1_keywords:
 - "ks/KsReadFile"
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
- KsReadFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsReadFile function


## -description


The <b>KsReadFile</b> function performs a read against the specified file object. It is assumed the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object. The function attempts to use <b>FastIoDispatch</b> if possible, or generates a read request against the device object. All relevant statistics are updated.


## -parameters




### -param FileObject [in]

Specifies the file object to perform the read against.


### -param Event [in, optional]

Optionally contains the event to use in the read. If no event is passed, the call is assumed to be on a synchronous file object. If not, the caller is waiting for the file object's event, or it may be asynchronously completed. If the file has been opened for synchronous I/O, this must be <b>NULL</b>. If the variable is used, it must be an event allocated by the object manager.


### -param PortContext [in, optional]

Optionally contains context information for a completion port.


### -param IoStatusBlock [out]

Specifies the address where the status information is to be returned. This is always assumed to be a valid address, regardless of the requester mode.


### -param Buffer [out]

Specifies the buffer in which to place the data read. If the buffer needs to be probed and locked, an exception handler is used, along with <i>RequesterMode</i>.


### -param Length [in]

Specifies the size of the buffer passed.


### -param OPTIONAL




### -param RequestorMode [in]

Indicates the processor mode to place in the read IRP if one needs to be generated. Additionally, it is used if the buffer needs to be probed and locked. This variable also determines if a fast I/O call can be performed. If the requester mode is not KernelMode, but the previous mode was, then fast I/O cannot be used.


#### - Key [in, optional]

Optionally contains a key, or zero if none


## -returns



The <b>KsReadFile</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or it returns a read error if unsuccessful.



