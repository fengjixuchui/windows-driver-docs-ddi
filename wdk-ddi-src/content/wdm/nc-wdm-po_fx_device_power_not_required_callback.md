---
UID: NC:wdm.PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
title: PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK (wdm.h)
description: The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state.
old-location: kernel\devicepowernotrequiredcallback.htm
tech.root: kernel
ms.assetid: 4BE1EEF7-7053-47AF-91E8-7313C3A56718
ms.date: 04/30/2018
keywords: ["PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback function"]
ms.keywords: DevicePowerNotRequiredCallback, DevicePowerNotRequiredCallback routine [Kernel-Mode Driver Architecture], PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK, kernel.devicepowernotrequiredcallback, wdm/DevicePowerNotRequiredCallback
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
targetos: Windows
req.typenames: 
f1_keywords:
 - PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
 - wdm/PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - DevicePowerNotRequiredCallback
---

# PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback function


## -description

The <i>DevicePowerNotRequiredCallback</i> callback routine notifies the device driver that the device is not required to stay in the D0 power state.

## -parameters

### -param Context 

[in]
A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.

## -remarks

When PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine, the driver must first decide whether to initiate a transition to a low-power Dx state (by sending an <a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> request down the device stack) or to remain in the D0 state. Next, without waiting for any Dx transition to complete, the driver must call the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompletedevicepowernotrequired">PoFxCompleteDevicePowerNotRequired</a> routine to notify PoFx that the driver completed its response to the <i>DevicePowerNotRequiredCallback</i> callback. The driver can call <b>PoFxCompleteDevicePowerNotRequired</b> before or after the <i>DevicePowerNotRequiredCallback</i> routine returns.

When a device is in the D0 state, and the Fx state or active/idle condition of a component in the device changes, PoFx evaluates whether the device can enter a low-power Dx state or must remain in the D0 state. If the device can enter a low-power Dx state, PoFx calls the driver's <i>DevicePowerNotRequiredCallback</i> routine.

If the device enters a low-power Dx state in response to a <i>DevicePowerNotRequiredCallback</i> callback, but PoFx later determines that the device must enter the D0 state, PoFx calls the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback">DevicePowerRequiredCallback</a> routine. In response to this call, the device must enter the D0 state.


#### Examples

To define a <i>DevicePowerNotRequiredCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>DevicePowerNotRequiredCallback</i> callback routine that is named <code>MyDevicePowerNotRequiredCallback</code>, use the PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK type as shown in this code example:


```
PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK MyDevicePowerNotRequiredCallback;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID
  MyDevicePowerNotRequiredCallback(
    PVOID Context
    )
  {
      // Function body
  }

```

The PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_device_power_required_callback">DevicePowerRequiredCallback</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_device_v1">PO_FX_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxcompletedevicepowernotrequired">PoFxCompleteDevicePowerNotRequired</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>