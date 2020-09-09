---
UID: NF:stiusd.IStiUSD.RawReadCommand
title: IStiUSD::RawReadCommand (stiusd.h)
description: A still image minidriver's IStiUSD::RawReadCommand method reads command information from a still image device.
old-location: image\istiusd_rawreadcommand.htm
tech.root: image
ms.assetid: 603f8b76-eb3b-41aa-932c-322f5405a29b
ms.date: 05/03/2018
keywords: ["IStiUSD::RawReadCommand"]
ms.keywords: IStiUSD interface [Imaging Devices],RawReadCommand method, IStiUSD.RawReadCommand, IStiUSD::RawReadCommand, RawReadCommand, RawReadCommand method [Imaging Devices], RawReadCommand method [Imaging Devices],IStiUSD interface, image.istiusd_rawreadcommand, stifnc_911a418d-3e30-4ddd-b40e-68ed302f18bb.xml, stiusd/IStiUSD::RawReadCommand
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiUSD::RawReadCommand
 - stiusd/IStiUSD::RawReadCommand
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiUSD.RawReadCommand
---

# IStiUSD::RawReadCommand


## -description

A still image minidriver's <b>IStiUSD::RawReadCommand</b> method reads command information from a still image device.

## -parameters

### -param lpBuffer

Caller-supplied pointer to a buffer to receive data read from the device.

### -param lpdwNumberOfBytes

Caller-supplied pointer to a DWORD. The caller loads the DWORD with the number of bytes in the buffer pointed to by <i>lpBuffer</i>. The driver must replace this value with the number of bytes actually read.

### -param lpOverlapped

Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).

## -returns

If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

It is only necessary to implement <b>IStiUSD::RawReadCommand</b> if command and data information are read from a device by different methods. For other devices, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-rawreaddata">IStiUSD::RawReadData</a> can be used for both commands and data. If the call is not implemented, it must return STIERR_UNSUPPORTED.

Implementation of this method, along with the meaning of buffer contents, are vendor-defined.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-rawreadcommand">IStiDevice::RawReadCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_image/index">IStiUSD</a>

