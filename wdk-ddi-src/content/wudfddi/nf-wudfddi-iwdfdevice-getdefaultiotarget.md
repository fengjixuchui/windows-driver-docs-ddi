---
UID: NF:wudfddi.IWDFDevice.GetDefaultIoTarget
title: IWDFDevice::GetDefaultIoTarget (wudfddi.h)
description: The GetDefaultIoTarget method retrieves the interface of the default I/O target for a device instance.
old-location: wdf\iwdfdevice_getdefaultiotarget.htm
tech.root: wdf
ms.assetid: 27bc5f1b-128d-486b-ae09-0356b1164ae0
ms.date: 02/26/2018
keywords: ["IWDFDevice::GetDefaultIoTarget"]
ms.keywords: GetDefaultIoTarget, GetDefaultIoTarget method, GetDefaultIoTarget method,IWDFDevice interface, IWDFDevice interface,GetDefaultIoTarget method, IWDFDevice.GetDefaultIoTarget, IWDFDevice::GetDefaultIoTarget, UMDFDeviceObjectRef_33807b94-79d4-4bb9-85a4-69de9d7c33dc.xml, umdf.iwdfdevice_getdefaultiotarget, wdf.iwdfdevice_getdefaultiotarget, wudfddi/IWDFDevice::GetDefaultIoTarget
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDevice::GetDefaultIoTarget
 - wudfddi/IWDFDevice::GetDefaultIoTarget
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDevice.GetDefaultIoTarget
---

# IWDFDevice::GetDefaultIoTarget


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDefaultIoTarget</b> method retrieves the interface of the default I/O target for a device instance.

## -parameters

### -param ppWdfIoTarget 

[out]
A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a> interface for the default I/O target object.

## -remarks

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/initializing-a-general-i-o-target-in-umdf">Initializing a General I/O Target in UMDF</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>

