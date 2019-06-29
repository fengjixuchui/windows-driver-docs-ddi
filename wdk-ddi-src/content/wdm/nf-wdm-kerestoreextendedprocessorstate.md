---
UID: NF:wdm.KeRestoreExtendedProcessorState
title: KeRestoreExtendedProcessorState function (wdm.h)
description: The KeRestoreExtendedProcessorState routine restores extended processor state information that was previously saved.
old-location: kernel\kerestoreextendedprocessorstate.htm
tech.root: kernel
ms.assetid: ea5e654a-9cb5-4d4d-9660-339410a6a20f
ms.date: 04/30/2018
ms.keywords: KeRestoreExtendedProcessorState, KeRestoreExtendedProcessorState routine [Kernel-Mode Driver Architecture], k105_35142457-ddfe-4773-b4ed-d2d84d5c74d0.xml, kernel.kerestoreextendedprocessorstate, wdm/KeRestoreExtendedProcessorState
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRestoreExtendedProcessorState
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRestoreExtendedProcessorState function


## -description


The <b>KeRestoreExtendedProcessorState</b> routine restores extended processor state information that was previously saved.


## -parameters




### -param XStateSave [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">XSTATE_SAVE</a> structure that contains the extended processor state information to restore. The contents of this structure must have been previously saved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesaveextendedprocessorstate">KeSaveExtendedProcessorState</a> routine.


## -returns



None




## -remarks



Kernel-mode driver code must ensure that calls to <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> are properly nested. This is required so that, at each nesting level, the state that was restored by the <b>KeRestoreExtendedProcessorState</b> call is the same state that was saved by the corresponding <b>KeSaveExtendedProcessorState</b> call. To ensure proper nesting, kernel-mode driver code must follow these rules:

<ul>
<li>
A <b>KeRestoreExtendedProcessorState</b> call that restores a saved state must be running at the same IRQL as the <b>KeSaveExtendedProcessorState</b> call that saved the state. 

</li>
<li>
If a pair of <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls is nested within a pair of surrounding <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls, the IRQL for the nested calls must not be lower than the IRQL for the surrounding calls. 

</li>
<li>
Typically, the caller-allocated <b>XSTATE_SAVE</b> structure that contains the state that was saved by <b>KeSaveExtendedProcessorState</b> resides on the stack. The stack naturally preserves the nesting of saved state information. If driver code stores the state in a location other than the stack, the driver writer must take special care to preserve the nesting of the <b>KeSaveExtendedProcessorState</b> and <b>KeRestoreExtendedProcessorState</b> calls.

</li>
<li>
The <b>KeRestoreExtendedProcessorState</b> call that restores a saved state must be running in the same thread as the <b>KeSaveExtendedProcessorState</b> call that saved the state. 

</li>
</ul>
A similar set of rules apply to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesavefloatingpointstate">KeSaveFloatingPointState</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kerestorefloatingpointstate">KeRestoreFloatingPointState</a> routines.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kerestorefloatingpointstate">KeRestoreFloatingPointState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesaveextendedprocessorstate">KeSaveExtendedProcessorState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kesavefloatingpointstate">KeSaveFloatingPointState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">XSTATE_SAVE</a>
 

 

