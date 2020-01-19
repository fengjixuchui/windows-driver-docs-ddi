---
UID: NF:wudfddi.IPnpCallbackSelfManagedIo.OnSelfManagedIoRestart
title: IPnpCallbackSelfManagedIo::OnSelfManagedIoRestart (wudfddi.h)
description: The OnSelfManagedIoRestart method restarts a device's self-managed I/O operations.
old-location: wdf\ipnpcallbackselfmanagedio_onselfmanagediorestart.htm
tech.root: wdf
ms.assetid: dccc4be0-0724-44b6-8476-276b46acee6a
ms.date: 02/26/2018
ms.keywords: IPnpCallbackSelfManagedIo interface,OnSelfManagedIoRestart method, IPnpCallbackSelfManagedIo.OnSelfManagedIoRestart, IPnpCallbackSelfManagedIo::OnSelfManagedIoRestart, OnSelfManagedIoRestart, OnSelfManagedIoRestart method, OnSelfManagedIoRestart method,IPnpCallbackSelfManagedIo interface, UMDFDeviceObjectRef_c570a334-c420-443d-8844-b4ff2bf35f47.xml, umdf.ipnpcallbackselfmanagedio_onselfmanagediorestart, wdf.ipnpcallbackselfmanagedio_onselfmanagediorestart, wudfddi/IPnpCallbackSelfManagedIo::OnSelfManagedIoRestart
ms.topic: method
f1_keywords:
 - "wudfddi/IPnpCallbackSelfManagedIo.OnSelfManagedIoRestart"
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackSelfManagedIo.OnSelfManagedIoRestart
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackSelfManagedIo::OnSelfManagedIoRestart


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnSelfManagedIoRestart</b> method restarts a device's self-managed I/O operations.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface for the device object of the device for which the self-managed I/O operations are restarted.


## -returns



If the <b>OnSelfManagedIoRestart</b> callback encounters no errors, it must return
        S_OK or another status code for which SUCCEEDED(status) equals <b>TRUE</b>.

  If it returns a status code for which SUCCEEDED(status) equals <b>FALSE</b>, the framework will stop the device and unload the device's drivers. In this case, the framework  calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagedioflush">IPnpCallbackSelfManagedIo::OnSelfManagedIoFlush</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackselfmanagedio-onselfmanagediocleanup">IPnpCallbackSelfManagedIo::OnSelfManagedIoCleanup</a> callback methods.

HRESULT error codes are defined in Winerror.h. 




## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a> interface when it calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackselfmanagedio">IPnpCallbackSelfManagedIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
 

 

