---
UID: NS:pepfx._PEP_QUERY_COMPONENT_PERF_STATES
title: _PEP_QUERY_COMPONENT_PERF_STATES (pepfx.h)
description: The PEP_QUERY_COMPONENT_PERF_STATES structure contains a list of discrete performance state (P-state) values for the specified P-state set.
old-location: kernel\pep_query_component_perf_states.htm
tech.root: kernel
ms.assetid: D14CB726-2576-490E-B3FD-E970F8B3C87F
ms.date: 04/30/2018
keywords: ["PEP_QUERY_COMPONENT_PERF_STATES structure"]
ms.keywords: "*PPEP_QUERY_COMPONENT_PERF_STATES, PEP_QUERY_COMPONENT_PERF_STATES, PEP_QUERY_COMPONENT_PERF_STATES structure [Kernel-Mode Driver Architecture], PPEP_QUERY_COMPONENT_PERF_STATES, PPEP_QUERY_COMPONENT_PERF_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_QUERY_COMPONENT_PERF_STATES, kernel.pep_query_component_perf_states, pepfx/PEP_QUERY_COMPONENT_PERF_STATES, pepfx/PPEP_QUERY_COMPONENT_PERF_STATES"
req.header: pepfx.h
req.include-header: Pep_x.h
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
req.typenames: PEP_QUERY_COMPONENT_PERF_STATES, *PPEP_QUERY_COMPONENT_PERF_STATES
f1_keywords:
 - _PEP_QUERY_COMPONENT_PERF_STATES
 - pepfx/_PEP_QUERY_COMPONENT_PERF_STATES
 - PPEP_QUERY_COMPONENT_PERF_STATES
 - pepfx/PPEP_QUERY_COMPONENT_PERF_STATES
 - PEP_QUERY_COMPONENT_PERF_STATES
 - pepfx/PEP_QUERY_COMPONENT_PERF_STATES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_QUERY_COMPONENT_PERF_STATES
---

# _PEP_QUERY_COMPONENT_PERF_STATES structure (pepfx.h)


## -description

The <b>PEP_QUERY_COMPONENT_PERF_STATES</b> structure contains a list of discrete performance state (P-state) values for the specified P-state set.

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

### -field Set

[in] The index that identifies this P-state set. If M is the number of P-state sets for this component, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_capabilities">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification.

### -field States

[in] A pointer to an output buffer. The PEP writes an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_perf_state">PEP_PERF_STATE</a> structures to this buffer. Each array element describes one P-state in the P-state set specified by the <b>Set</b> member. The Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) allocated this buffer, which is guaranteed to be large enough to contain an array of the length that the PEP previously wrote to the <b>Discrete.Count</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_set">PEP_QUERY_COMPONENT_PERF_SET</a> structure in response to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_set">PEP_DPM_QUERY_COMPONENT_PERF_SET</a> notification.

## -remarks

This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_states">PEP_DPM_QUERY_COMPONENT_PERF_STATES</a> notification. All four members of this structure contain input values that are supplied by PoFx when this notification is sent.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_query_component_perf_states">PEP_DPM_QUERY_COMPONENT_PERF_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_perf_state">PEP_PERF_STATE</a>

