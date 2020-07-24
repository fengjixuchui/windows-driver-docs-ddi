---
UID: NF:sti.IStiDevice.GetLastErrorInfo
title: IStiDevice::GetLastErrorInfo (sti.h)
description: The IStiDevice::GetLastErrorInfo method returns information about the last known error associated with a still image device.
old-location: image\istidevice_getlasterrorinfo.htm
tech.root: image
ms.assetid: de2f8897-c75f-4c37-aecb-f36d0f9933f9
ms.date: 05/03/2018
keywords: ["IStiDevice::GetLastErrorInfo"]
ms.keywords: GetLastErrorInfo, GetLastErrorInfo method [Imaging Devices], GetLastErrorInfo method [Imaging Devices],IStiDevice interface, IStiDevice interface [Imaging Devices],GetLastErrorInfo method, IStiDevice.GetLastErrorInfo, IStiDevice::GetLastErrorInfo, image.istidevice_getlasterrorinfo, sti/IStiDevice::GetLastErrorInfo, stifnc_f54b574c-5894-4029-888c-fe60738858d7.xml
f1_keywords:
 - "sti/IStiDevice.GetLastErrorInfo"
 - "IStiDevice.GetLastErrorInfo"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- sti.h
api_name:
- IStiDevice.GetLastErrorInfo
targetos: Windows
req.typenames: 
---

# IStiDevice::GetLastErrorInfo


## -description


The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the last known error associated with a still image device.


## -parameters




### -param pLastErrorInfo






#### - pLastErrorInf [out]

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/ns-sti-_error_infow">STI_ERROR_INFO</a> structure to receive error information.


## -returns



If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.




## -remarks



The <b>IStiDevice::GetLastErrorInfo</b> method returns information about the most recent error by filling in the caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sti/ns-sti-_error_infow">STI_ERROR_INFO</a> structure. The method calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-getlasterrorinfo">IStiUSD::GetLastErrorInfo</a>, which is exported by vendor-supplied minidrivers.

Before calling <b>IStiDevice::GetLastErrorInfo</b>, clients of the <b>IStiDevice</b> COM interface must call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff543778(v=vs.85)">IStillImage::CreateDevice</a> to obtain an <b>IStiDevice</b> interface pointer, which provides access to a specified device.



