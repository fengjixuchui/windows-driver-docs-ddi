---
UID: NS:pep_x._PEP_POWER_CONTROL_REQUEST
title: _PEP_POWER_CONTROL_REQUEST (pep_x.h)
description: The PEP_POWER_CONTROL_REQUEST structure contains a request from a driver for a power control operation.
old-location: kernel\pep_power_control_request.htm
tech.root: kernel
ms.assetid: E6665E96-5C58-4533-906A-D9525BA6824C
ms.date: 04/30/2018
ms.keywords: "*PPEP_POWER_CONTROL_REQUEST, PEP_POWER_CONTROL_REQUEST, PEP_POWER_CONTROL_REQUEST structure [Kernel-Mode Driver Architecture], PPEP_POWER_CONTROL_REQUEST, PPEP_POWER_CONTROL_REQUEST structure pointer [Kernel-Mode Driver Architecture], _PEP_POWER_CONTROL_REQUEST, kernel.pep_power_control_request, pepfx/PEP_POWER_CONTROL_REQUEST, pepfx/PPEP_POWER_CONTROL_REQUEST"
ms.topic: struct
req.header: pep_x.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_POWER_CONTROL_REQUEST
product:
- Windows
targetos: Windows
req.typenames: PEP_POWER_CONTROL_REQUEST, *PPEP_POWER_CONTROL_REQUEST
---

# _PEP_POWER_CONTROL_REQUEST structure


## -description


The <b>PEP_POWER_CONTROL_REQUEST</b> structure contains a request from a driver for a power control operation.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PowerControlCode

[in] A pointer to a <a href="https://docs.microsoft.com/previous-versions/aa373931(v=vs.80)">GUID</a> value that specifies the power control operation to perform. This is the same value that the requesting driver supplied as the <i>PowerControlCode</i> parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxpowercontrol">PoFxPowerControl</a> routine.


### -field InBuffer

[in] A pointer to a driver-allocated input buffer that contains the input parameters for this power control operation. This is the same value that the requesting driver supplied as the <i>InBuffer</i> parameter to the <b>PoFxPowerControl</b> routine.


### -field InBufferSize

[in] The size in bytes of the buffer pointed to by <b>InBuffer</b>. This is the same value that the requesting driver supplied as the <i>InBufferSize</i> parameter to the <b>PoFxPowerControl</b> routine.


### -field OutBuffer

[in] A pointer to a driver-allocated output buffer to which the PEP writes the results of this power control operation. This is the same value that the requesting driver supplied as the <i>OutBuffer</i> parameter to the <b>PoFxPowerControl</b> routine.


### -field OutBufferSize

[in] The size in bytes of the buffer pointed to by <b>OutBuffer</b>.


### -field BytesReturned

[out] The number of bytes that the PEP wrote to the output buffer pointed to by <b>OutBuffer</b>.


### -field Status

[out] The status of the requested power control operation. If the operation is successful, the PEP sets this member to STATUS_SUCCESS. Otherwise, the PEP sets this member to an appropriate error status code.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_power_control_request">PEP_DPM_POWER_CONTROL_REQUEST</a> notification. The first six members of the structure contain input values that are supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management Framework</a> (PoFx). The last two members contain values that the PEP writes to the structure in response to this notification. In addition, the PEP writes to the output buffer pointed to by the <b>OutBuffer</b> member.

If the output buffer is too small to receive all of the result data from the operation, the PEP sets the <b>Status</b> member of the structure to STATUS_INSUFFICIENT_RESOURCES, sets  the <b>BytesReturned</b> member to the required size of the output buffer, and (typically) writes no data to the output buffer.

The driver for a device can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxpowercontrol">PoFxPowerControl</a> routine to request a power control operation on the device. During this call, PoFx delegates the handling of this request to the PEP that owns the device. The <b>PowerControlCode</b> member of the <b>PEP_POWER_CONTROL_REQUEST</b> structure contains a custom control code whose meaning is understood by both the driver and the PEP for the device.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_power_control_request">PEP_DPM_POWER_CONTROL_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pofxpowercontrol">PoFxPowerControl</a>
 

 

