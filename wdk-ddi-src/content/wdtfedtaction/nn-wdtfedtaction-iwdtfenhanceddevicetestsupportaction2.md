---
UID: NN:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2
title: IWDTFEnhancedDeviceTestSupportAction2 (wdtfedtaction.h)
description: Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2.htm
tech.root: dtf
ms.assetid: 273eb6e9-10cb-4ed3-86a4-103dea801b77
ms.date: 04/04/2018
ms.keywords: IWDTFEnhancedDeviceTestSupportAction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2, dtf.iwdtfenhanceddevicetestsupportaction2, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2
ms.topic: interface
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Windows
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
- IWDTFEnhancedDeviceTestSupportAction2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFEnhancedDeviceTestSupportAction2 interface


## -description


Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFEnhancedDeviceTestSupportAction2</b> interface inherits from <b>IWDTFActionWithCustomActions2</b>. <b>IWDTFEnhancedDeviceTestSupportAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFEnhancedDeviceTestSupportAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-disable">Disable</a>
</td>
<td align="left" width="63%">
Disables the Enhanced Device Test (EDT) filter driver on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Enable</a>
</td>
<td align="left" width="63%">
Enables the Enhanced Device Test (EDT) filter driver on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfedtaction/nf-wdtfedtaction-iwdtfenhanceddevicetestsupportaction2-isenabled">IsEnabled</a>
</td>
<td align="left" width="63%">
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">IsRebootRequired</a>
</td>
<td align="left" width="63%">
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFEnhancedDeviceTestSupportAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh451010(v=vs.85)">SkipRestart</a>


</td>
<td align="left" width="10%">
Write-only

</td>
<td align="left" width="63%">
Sets a value that indicates whether the target device should be restarted by default.

</td>
</tr>
</table> 


## -remarks



The EDT filter driver provides support for the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfpnpaction/nn-wdtfpnpaction-iwdtfpnpaction2">IWDTFPNPAction2</a> interface methods 
that are prefixed with <b>EDT</b>.



