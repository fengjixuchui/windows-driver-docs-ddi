---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
title: IOCTL_INTERNAL_I8042_HOOK_KEYBOARD (ntdd8042.h)
description: The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following:Adds an initialization callback routine to the I8042prt keyboard initialization routineAdds an ISR callback routine to the I8042prt keyboard ISRThe initialization and ISR callbacks are optional and are provided by an upper-level filter driver for a PS/2-style keyboard device.After I8042prt receives an IOCTL_INTERNAL_KEYBOARD_CONNECT request, it sends a synchronous IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request to the top of the keyboard device stack.After Kbfiltr receives the hook keyboard request, Kbfiltr filters the request in the following way:Saves the upper-level information passed to Kbfiltr, which includes the context of an upper-level device object, a pointer to an initialization callback, and a pointer to an ISR callbackReplaces the upper-level information with its ownSaves the context of I8042prt and pointers to callbacks that the Kbfiltr ISR callback can useFor more information about this request and the callbacks, see the following topics:I8042prt Callback RoutinesKbfiltr Callback Routines.
old-location: hid\ioctl_internal_i8042_hook_keyboard.htm
tech.root: hid
ms.assetid: 74580730-1cbb-40fb-a4a3-20523f933171
ms.date: 04/30/2018
keywords: ["IOCTL_INTERNAL_I8042_HOOK_KEYBOARD IOCTL"]
ms.keywords: IOCTL_INTERNAL_I8042_HOOK_KEYBOARD, IOCTL_INTERNAL_I8042_HOOK_KEYBOARD control, IOCTL_INTERNAL_I8042_HOOK_KEYBOARD control code [Human Input Devices], hid.ioctl_internal_i8042_hook_keyboard, kfilref_d213e6a4-db1b-4fed-8cd9-503703ee59dd.xml, ntdd8042/IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
f1_keywords:
 - "ntdd8042/IOCTL_INTERNAL_I8042_HOOK_KEYBOARD"
 - "IOCTL_INTERNAL_I8042_HOOK_KEYBOARD"
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- ntdd8042.h
api_name:
- IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_I8042_HOOK_KEYBOARD IOCTL


## -description



The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following:

<ul>
<li>
Adds an initialization callback routine to the I8042prt keyboard initialization routine

</li>
<li>
Adds an ISR callback routine to the I8042prt keyboard ISR

</li>
</ul>
The initialization and ISR callbacks are optional and are provided by an upper-level filter driver for a PS/2-style keyboard device.

After I8042prt receives an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_keyboard_connect">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request, it sends a synchronous IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request to the top of the keyboard device stack.

After Kbfiltr receives the hook keyboard request, Kbfiltr filters the request in the following way:

<ul>
<li>
Saves the upper-level information passed to Kbfiltr, which includes the context of an upper-level device object, a pointer to an initialization callback, and a pointer to an ISR callback

</li>
<li>
Replaces the upper-level information with its own

</li>
<li>
Saves the context of I8042prt and pointers to callbacks that the Kbfiltr ISR callback can use

</li>
</ul>
For more information about this request and the callbacks, see the following topics:

<dl>
<dd>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">I8042prt Callback Routines</a>


</dd>
<dd>

<a href="https://docs.microsoft.com/previous-versions/ff542302(v=vs.85)">Kbfiltr Callback Routines</a>


</dd>
</dl>



## -ioctlparameters




### -input-buffer

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_KEYBOARD structure. This structure includes the following members:




#### -InitializationRoutine

Pointer to an optional callback that the I8042prt keyboard initialization routine calls when it initializes a keyboard device.


#### -IsrRoutine

Pointer to an optional callback that is called by the I8042prt keyboard ISR.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value that is greater than or equal to the size, in bytes, of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_hook_keyboard">INTERNAL_I8042_HOOK_KEYBOARD</a> structure.


### -output-buffer

None


### -output-buffer-length

None


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Status</b> member is set to one of the following values:




**STATUS_INVALID_PARAMETER**

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of an INTERNAL_I8042_HOOK_KEYBOARD structure.


**STATUS_SUCCESS**

The request completed successfully. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_hook_keyboard">INTERNAL_I8042_HOOK_KEYBOARD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_keyboard_connect">IOCTL_INTERNAL_KEYBOARD_CONNECT</a>
 

 

