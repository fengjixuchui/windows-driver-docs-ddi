---
UID: NN:wudfddi.IWDFRemoteInterface
title: IWDFRemoteInterface (wudfddi.h)
description: UMDF drivers receive a pointer to this interface by calling the IWDFDevice2::CreateRemoteInterface method.
old-location: wdf\iwdfremoteinterface.htm
tech.root: wdf
ms.assetid: 10d4cd20-c797-455c-b16d-00982be5c1b7
ms.date: 02/26/2018
keywords: ["IWDFRemoteInterface interface"]
ms.keywords: IWDFRemoteInterface, IWDFRemoteInterface interface, IWDFRemoteInterface interface, described, wdf.iwdfremoteinterface, wudfddi/IWDFRemoteInterface
req.header: wudfddi.h
req.include-header: 
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
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
f1_keywords:
 - IWDFRemoteInterface
 - wudfddi/IWDFRemoteInterface
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRemoteInterface
---

# IWDFRemoteInterface interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

UMDF drivers receive a pointer to this interface by calling the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremoteinterface">IWDFDevice2::CreateRemoteInterface</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremoteinterfacecallbackevent-onremoteinterfaceevent">IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iremoteinterfacecallbackremoval-onremoteinterfaceremoval">IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremoteinterface">IWDFDevice2::CreateRemoteInterface</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openremoteinterface">IWDFRemoteTarget::OpenRemoteInterface</a>