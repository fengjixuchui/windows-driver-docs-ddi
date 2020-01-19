---
UID: NF:wdtfpnpaction.IWDTFPNPActions2.EDTSurpriseRemoveDevice
title: IWDTFPNPActions2::EDTSurpriseRemoveDevice (wdtfpnpaction.h)
description: Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.
old-location: dtf\iwdtfpnpactions2_edtsurpriseremovedevice.htm
tech.root: dtf
ms.assetid: 9f4511b8-c41f-4a7f-81e6-20c30a131f64
ms.date: 04/04/2018
ms.keywords: EDTSurpriseRemoveDevice, EDTSurpriseRemoveDevice method [Windows Device Testing Framework], EDTSurpriseRemoveDevice method [Windows Device Testing Framework],IWDTFPNPActions2 interface, IWDTFPNPActions2 interface [Windows Device Testing Framework],EDTSurpriseRemoveDevice method, IWDTFPNPActions2.EDTSurpriseRemoveDevice, IWDTFPNPActions2::EDTSurpriseRemoveDevice, dtf.iwdtfpnpactions2_edtsurpriseremovedevice, wdtfpnpaction/IWDTFPNPActions2::EDTSurpriseRemoveDevice
ms.topic: method
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPActions2.EDTSurpriseRemoveDevice"
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
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
- wdtfpnpaction.h
api_name:
- IWDTFPNPActions2.EDTSurpriseRemoveDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPActions2::EDTSurpriseRemoveDevice


## -description


Sends an IRP_MN_SURPRISE_REMOVAL event to the target device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTSurpriseRemoveDevice</b> attempts to trigger a surprise removal of the target device. 
This operation is useful for testing 
how drivers and driver/device aware applications handle the IRP_MN_SURPRISE_REMOVAL event, e.g. scenarios in which 
the device unexpectedly fails or is removed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFPNPActions2</a>
 

 

