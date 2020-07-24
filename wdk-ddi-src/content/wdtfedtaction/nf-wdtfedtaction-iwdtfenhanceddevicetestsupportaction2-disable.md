---
UID: NF:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2.Disable
title: IWDTFEnhancedDeviceTestSupportAction2::Disable (wdtfedtaction.h)
description: Disables the Enhanced Device Test (EDT) filter driver on the target device.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2_disable.htm
tech.root: dtf
ms.assetid: cf67d391-8c73-43d7-aab3-57837c78dbc4
ms.date: 04/04/2018
keywords: ["IWDTFEnhancedDeviceTestSupportAction2::Disable"]
ms.keywords: Disable, Disable method [Windows Device Testing Framework], Disable method [Windows Device Testing Framework],IWDTFEnhancedDeviceTestSupportAction2 interface, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],Disable method, IWDTFEnhancedDeviceTestSupportAction2.Disable, IWDTFEnhancedDeviceTestSupportAction2::Disable, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2.Disable, Microsoft::WDTF::IWDTFEnhancedDeviceTestSupportAction2::Disable, dtf.iwdtfenhanceddevicetestsupportaction2_disable, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2::Disable
f1_keywords:
 - "wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2.Disable"
 - "IWDTFEnhancedDeviceTestSupportAction2.Disable"
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFEDTAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverEDTAction.Interop.dll
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
- WDTFDriverEDTAction.Interop.dll
api_name:
- IWDTFEnhancedDeviceTestSupportAction2.Disable
targetos: Windows
req.typenames: 
---

# IWDTFEnhancedDeviceTestSupportAction2::Disable


## -description


Disables the Enhanced Device Test (EDT) filter driver on the target device.


## -parameters




### -param pbRebootRequired [out, retval]

True if the operation requires a restart to complete; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfedtaction/nn-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2">IWDTFEnhancedDeviceTestSupportAction2</a>
 

 

