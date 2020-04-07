---
UID: NF:wdtfpnpaction.IWDTFPNPAction2.EDTCancelStopDevice
title: IWDTFPNPAction2::EDTCancelStopDevice (wdtfpnpaction.h)
description: Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.
old-location: dtf\iwdtfpnpaction2_edtcancelstopdevice.htm
tech.root: dtf
ms.assetid: 5ddce998-2f64-4711-b820-5baa88096d99
ms.date: 04/04/2018
keywords: ["IWDTFPNPAction2::EDTCancelStopDevice"]
ms.keywords: EDTCancelStopDevice, EDTCancelStopDevice method [Windows Device Testing Framework], EDTCancelStopDevice method [Windows Device Testing Framework],IWDTFPNPAction2 interface, IWDTFPNPAction2 interface [Windows Device Testing Framework],EDTCancelStopDevice method, IWDTFPNPAction2.EDTCancelStopDevice, IWDTFPNPAction2::EDTCancelStopDevice, Microsoft.WDTF.IWDTFPNPAction2.EDTCancelStopDevice, Microsoft::WDTF::IWDTFPNPAction2::EDTCancelStopDevice, dtf.iwdtfpnpaction2_edtcancelstopdevice, wdtfpnpaction/IWDTFPNPAction2::EDTCancelStopDevice
f1_keywords:
 - "wdtfpnpaction/IWDTFPNPAction2.EDTCancelStopDevice"
req.header: wdtfpnpaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFPNPAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPNPAction.Interop.dll
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
- WDTFDriverPNPAction.Interop.dll
api_name:
- IWDTFPNPAction2.EDTCancelStopDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFPNPAction2::EDTCancelStopDevice


## -description


Sends an IRP_MN_CANCEL_STOP_DEVICE event to the target device.


## -parameters




### -param pbSuccess [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<div class="alert"><b>Note</b>  The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-enable">IWDTFEnhancedDeviceTestSupportAction2::Enable</a>  
method must be called for the target device before calling this method.</div>
<div> </div>
<b>EDTCancelStopDevice</b> attempts to trigger an IRP_MN_CANCEL_STOP_DEVICE 
event by causing the system to send an IRP_MN_QUERY_STOP_DEVICE event and by intentionally failing 
the query IRP in the DeviceManagement2 helper driver.

It is possible for the filter drivers that are loaded above the helper driver 
to fail the query IRP as well. In that case, the helper driver will indicate this condition 
by setting EDTRS_QueryStopVetoed in ppResult.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a>
 

 

