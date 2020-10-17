---
UID: NC:wdm.PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK
title: PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK (wdm.h)
description: The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states.
old-location: kernel\componentcriticaltransitioncallback.htm
tech.root: kernel
ms.assetid: 6E551951-E903-4970-8B30-6780C9FF4FC6
ms.date: 04/30/2018
keywords: ["PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback function"]
ms.keywords: ComponentCriticalTransitionCallback, ComponentCriticalTransitionCallback routine [Kernel-Mode Driver Architecture], PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK, kernel.componentcriticaltransitioncallback, wdm/ComponentCriticalTransitionCallback
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK
 - wdm/PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ComponentCriticalTransitionCallback
---

# PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback function


## -description

The <i>ComponentCriticalTransitionCallback</i> callback routine handles a transition of the specified component between the F0 (fully on) and low-power F<i>x</i> component power states.

## -parameters

### -param Context 

[in]
A pointer to the device context. The device driver uses this context to store information about the current power state of the device. This context is driver-defined and is opaque to PoFx. The driver specified this pointer in the <b>DeviceContext</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_po_fx_core_device">PO_FX_CORE_DEVICE</a> structure that the driver used to register the device with the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

### -param Component 

[in]
The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_CORE_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -param Active 

[in]
Indicates whether this notification is for a transition to the F0 component power state. If TRUE, the component has just completed a transition from a low-power F<i>x</i> state to F0. If FALSE, the component is about to start a transition from F0 to a low-power F<i>x</i> state.

## -remarks

This callback routine is implemented by a device driver, and is called by PoFx. PoFx calls this routine to notify the driver of power transitions of device components.

The <b>ComponentCriticalTransitionCallback</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_po_fx_core_device">PO_FX_CORE_DEVICE</a> structure is a pointer to a <i>ComponentCriticalTransitionCallback</i> callback routine. A pointer to a <b>PO_FX_CORE_DEVICE</b> structure is passed as an input parameter in the PoFxRegisterCoreDevice call that registers a core device with the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

To handle calls to this routine, the device driver saves or restores the register state or other hardware context of the specified component in the device.

If <i>Active</i> = TRUE, PoFx has called this routine <i>after</i> the component completed a transition from a low-power F<i>x</i> state to F0. In this call, the routine restores the previously saved hardware context of the component.

If <i>Active</i> = FALSE, PoFx has called this routine <i>before</i> the component starts a pending transition from F0 to a low-power F<i>x</i> state. In this call, the routine saves the component's hardware context so that this context can later be restored.

For more information about F<i>x</i> component power states, see <a href="/windows-hardware/drivers/kernel/component-level-power-management">Component-Level Power Management</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_po_fx_core_device">PO_FX_CORE_DEVICE</a>