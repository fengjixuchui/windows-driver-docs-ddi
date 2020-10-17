---
UID: NN:wudfddi.IPnpCallbackRemoteInterfaceNotification
title: IPnpCallbackRemoteInterfaceNotification (wudfddi.h)
description: A driver's IPnpCallbackRemoteInterfaceNotification interface provides a callback function that the framework calls to notify the driver when a device interface becomes available.
old-location: wdf\ipnpcallbackremoteinterfacenotification.htm
tech.root: wdf
ms.assetid: 99d670dd-2358-4f1a-b111-72484bf3132c
ms.date: 02/26/2018
keywords: ["IPnpCallbackRemoteInterfaceNotification interface"]
ms.keywords: IPnpCallbackRemoteInterfaceNotification, IPnpCallbackRemoteInterfaceNotification interface, IPnpCallbackRemoteInterfaceNotification interface,described, UMDFDeviceObjectRef_4701eb20-04aa-412f-8511-f44a2590ee5b.xml, umdf.ipnpcallbackremoteinterfacenotification, wdf.ipnpcallbackremoteinterfacenotification, wudfddi/IPnpCallbackRemoteInterfaceNotification
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPnpCallbackRemoteInterfaceNotification
 - wudfddi/IPnpCallbackRemoteInterfaceNotification
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Wudfddi.h
api_name:
 - IPnpCallbackRemoteInterfaceNotification
---

# IPnpCallbackRemoteInterfaceNotification interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>IPnpCallbackRemoteInterfaceNotification</b> interface provides a callback function that the framework calls to notify the driver when a <a href="/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> becomes available.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackRemoteInterfaceNotification</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallbackRemoteInterfaceNotification</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

If your driver supports an <b>IPnpCallbackRemoteInterfaceNotification</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> must return the interface.