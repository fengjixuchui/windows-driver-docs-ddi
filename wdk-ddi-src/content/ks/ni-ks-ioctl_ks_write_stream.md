---
UID: NI:ks.IOCTL_KS_WRITE_STREAM
title: IOCTL_KS_WRITE_STREAM (ks.h)
description: An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_write_stream.htm
tech.root: stream
ms.assetid: 560cfc18-5cbe-4af7-b579-3904ee68acbf
ms.date: 04/23/2018
ms.keywords: IOCTL_KS_WRITE_STREAM, IOCTL_KS_WRITE_STREAM control, IOCTL_KS_WRITE_STREAM control code [Streaming Media Devices], ks-ioctl_83263ce8-e0b1-4ae5-a5b8-848e0fb99471.xml, ks/IOCTL_KS_WRITE_STREAM, stream.ioctl_ks_write_stream
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- IOCTL_KS_WRITE_STREAM
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_WRITE_STREAM IOCTL


## -description


An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> function.


## -ioctlparameters




### -input-buffer

A client provides a pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structures in <b>InBuffer</b>. The stream data to write is contained in the buffers pointed to by the stream headers. The headers can also contain presentation time and duration. 


### -input-buffer-length

The <b>InLength</b> parameter should specify the size, in bytes, of the input buffer contents.


### -output-buffer

Kernel streaming provides the number of bytes written in the <b>BytesReturned</b> parameter.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ni-ks-ioctl_ks_read_stream">IOCTL_KS_READ_STREAM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksprobestreamirp">KsProbeStreamIrp</a>
 

 

