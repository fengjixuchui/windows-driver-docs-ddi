---
UID: NF:wdfdevice.WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT
title: WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function (wdfdevice.h)
description: The WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure.
old-location: wdf\wdf_device_power_policy_wake_settings_init.htm
tech.root: wdf
ms.assetid: bb712c92-c926-4a7a-a126-db4db3bc728f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_2608d30e-282b-4a19-acb7-ced01cb6bc1a.xml, WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT, WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function, kmdf.wdf_device_power_policy_wake_settings_init, wdf.wdf_device_power_policy_wake_settings_init, wdfdevice/WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT
ms.topic: function
f1_keywords:
 - "wdfdevice/WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b> function initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_wake_settings">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure.


## -parameters




### -param Settings [out]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_wake_settings">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure.


## -returns



None




## -remarks



The <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_power_policy_wake_settings">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. Then the function sets the structure's <b>Enabled</b> member to <b>WdfUseDefault</b>, sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>, and sets the <b>UserControlOfWakeSettings</b> member to <b>WakeAllowUserControl</b>.

For a code example that uses <b>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceassignsxwakesettings">WdfDeviceAssignSxWakeSettings</a>.



