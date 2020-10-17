---
UID: NC:wdfdevice.EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION
title: EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDevicePnpStateChange event callback function informs the driver that a device's Plug and Play (PnP) state machine is moving from one state to another.
old-location: wdf\evtdevicepnpstatechange.htm
tech.root: wdf
ms.assetid: 5f08d331-0e58-45a3-93a3-b5e9a40b5af3
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback function"]
ms.keywords: DFDeviceObjectGeneralRef_484dd3d0-689b-4c81-bdc2-85d14db47499.xml, EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION, EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback, EvtDevicePnpStateChange, EvtDevicePnpStateChange callback function, kmdf.evtdevicepnpstatechange, wdf.evtdevicepnpstatechange, wdfdevice/EvtDevicePnpStateChange
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION
 - wdfdevice/EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDevicePnpStateChange
---

# EVT_WDF_DEVICE_PNP_STATE_CHANGE_NOTIFICATION callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

>[!NOTE]
>This callback function is for Microsoft-internal use only.

A driver's <i>EvtDevicePnpStateChange</i> event callback function informs the driver that a device's Plug and Play (PnP) state machine is moving from one state to another.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param NotificationData 

[in]
A pointer to a framework-supplied <a href="/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_notification_data">WDF_DEVICE_PNP_NOTIFICATION_DATA</a> structure that identifies the state machine's old and new states.

## -remarks

To register an <i>EvtDevicePnpStateChange</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback">WdfDeviceInitRegisterPnpStateChangeCallback</a>.

For more information about the framework's PnP state machine, see <a href="/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification">EvtDevicePowerPolicyStateChange</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_power_state_change_notification">EvtDevicePowerStateChange</a>