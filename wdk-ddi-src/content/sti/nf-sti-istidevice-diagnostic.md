---
UID: NF:sti.IStiDevice.Diagnostic
title: IStiDevice::Diagnostic (sti.h)
description: The IStiDevice::Diagnostic method executes diagnostic tests on a still image device.
old-location: image\istidevice_diagnostic.htm
tech.root: image
ms.assetid: eee5c6d7-17a3-461f-85e0-17f6b7114b19
ms.date: 05/03/2018
keywords: ["IStiDevice::Diagnostic"]
ms.keywords: Diagnostic, Diagnostic method [Imaging Devices], Diagnostic method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],Diagnostic method, IStiDevice.Diagnostic, IStiDevice::Diagnostic, image.istidevice_diagnostic, sti/IStiDevice::Diagnostic, stifnc_68471629-529f-48c5-bcaf-8be60f5f50c0.xml
req.header: sti.h
req.include-header: Sti.h
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
 - IStiDevice::Diagnostic
 - sti/IStiDevice::Diagnostic
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - sti.h
api_name:
 - IStiDevice.Diagnostic
---

# IStiDevice::Diagnostic


## -description

The <b>IStiDevice::Diagnostic</b> method executes diagnostic tests on a still image device.

## -parameters

### -param pBuffer 

[in, out]
Caller-supplied pointer to an <a href="/windows-hardware/drivers/ddi/sti/ns-sti-_sti_diag">STI_DIAG</a> structure specifying the type of tests to be run. On return, the structure contains status information.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The <b>IStiDevice::Diagnostic</b> method calls <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-diagnostic">IStiUSD::Diagnostic</a>, which is exported by vendor-supplied minidrivers. The Scanners and Cameras Control Panel calls <b>IStiDevice::Diagnostic</b> when a user presses the Test button.

Before calling <b>IStiDevice::Diagnostic</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.

A call to <b>IStiDevice::Diagnostic</b> must be preceded by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-lockdevice">IStiDevice::LockDevice</a> and followed by a call to <a href="/windows-hardware/drivers/ddi/sti/nf-sti-istidevice-unlockdevice">IStiDevice::UnLockDevice</a>.