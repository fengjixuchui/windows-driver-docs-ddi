---
UID: NS:wdfdevice._WDF_DEVICE_STATE
title: _WDF_DEVICE_STATE (wdfdevice.h)
description: The WDF_DEVICE_STATE structure specifies a device's Plug and Play state.
old-location: wdf\wdf_device_state.htm
tech.root: wdf
ms.assetid: 5d0a2303-df2b-45fe-9c88-df4bb19a2a9f
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_STATE structure"]
ms.keywords: "*PWDF_DEVICE_STATE, DFDeviceObjectGeneralRef_a5705164-b38f-4307-8b7d-5b3156aadf62.xml, PWDF_DEVICE_STATE, PWDF_DEVICE_STATE structure pointer, WDF_DEVICE_STATE, WDF_DEVICE_STATE structure, _WDF_DEVICE_STATE, kmdf.wdf_device_state, wdf.wdf_device_state, wdfdevice/PWDF_DEVICE_STATE, wdfdevice/WDF_DEVICE_STATE"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
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
targetos: Windows
req.typenames: WDF_DEVICE_STATE, *PWDF_DEVICE_STATE
f1_keywords:
 - _WDF_DEVICE_STATE
 - wdfdevice/_WDF_DEVICE_STATE
 - PWDF_DEVICE_STATE
 - wdfdevice/PWDF_DEVICE_STATE
 - WDF_DEVICE_STATE
 - wdfdevice/WDF_DEVICE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_DEVICE_STATE
---

# _WDF_DEVICE_STATE structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_STATE</b> structure specifies a device's Plug and Play state.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Disabled

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is disabled. For more information about the <b>WDF_TRI_STATE</b> type, see the following Remarks section.

### -field DontDisplayInUI

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is hidden (not displayed) in Device Manager. For more information, see <a href="/windows-hardware/drivers/install/viewing-hidden-devices">Viewing Hidden Devices</a>. (After you set this member to <b>WdfTrue</b>, changing its value has no effect.)

### -field Failed

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device is present but has failed.

### -field NotDisableable

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device cannot be disabled.

### -field Removed

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device has been removed.

### -field ResourcesChanged

A <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value that, if set to <b>WdfTrue</b>, indicates that the device's resource requirements have changed.

## -remarks

Structure members use the <a href="/windows-hardware/drivers/ddi/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a> type. A value of <b>WdfUseDefault</b> indicates the framework will use the value that was provided by a lower driver in the stack. For example, if a bus driver specifies <b>WdfTrue</b> for <b>NotDisableable</b> and the device's function driver specifies <b>WdfUseDefault</b>, the framework uses <b>WdfTrue</b> for the device state.

The <b>WDF_DEVICE_STATE</b> structure is used as a parameter to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdevicestate">WdfDeviceSetDeviceState</a> and <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicestate">WdfDeviceGetDeviceState</a>.

To initialize a <b>WDF_DEVICE_STATE</b> structure, the driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_device_state_init">WDF_DEVICE_STATE_INIT</a>.

For more information about the members of the <b>WDF_DEVICE_STATE</b> structure, see [PNP_DEVICE_STATE](/windows-hardware/drivers/kernel/handling-an-irp-mn-surprise-removal-request#about-pnp_device_state).