---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_HOOK_MOUSE
title: IOCTL_INTERNAL_I8042_HOOK_MOUSE (ntdd8042.h)
description: The IOCTL_INTERNAL_I8042_HOOK_MOUSE request adds an ISR callback routine to the I8042prt mouse ISR.
old-location: hid\ioctl_internal_i8042_hook_mouse.htm
tech.root: hid
ms.assetid: 606b9ae4-186c-47b1-84aa-3d380eaad672
ms.date: 04/30/2018
keywords: ["IOCTL_INTERNAL_I8042_HOOK_MOUSE IOCTL"]
ms.keywords: IOCTL_INTERNAL_I8042_HOOK_MOUSE, IOCTL_INTERNAL_I8042_HOOK_MOUSE control, IOCTL_INTERNAL_I8042_HOOK_MOUSE control code [Human Input Devices], hid.ioctl_internal_i8042_hook_mouse, mfilref_d95cd233-bc97-4bd6-8675-2560b83f4715.xml, ntdd8042/IOCTL_INTERNAL_I8042_HOOK_MOUSE
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_INTERNAL_I8042_HOOK_MOUSE
 - ntdd8042/IOCTL_INTERNAL_I8042_HOOK_MOUSE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdd8042.h
api_name:
 - IOCTL_INTERNAL_I8042_HOOK_MOUSE
---

# IOCTL_INTERNAL_I8042_HOOK_MOUSE IOCTL


## -description

The IOCTL_INTERNAL_I8042_HOOK_MOUSE request adds an ISR callback routine to the I8042prt mouse ISR. The ISR callback is optional and is provided by an upper-level mouse filter driver.

I8042prt sends this request after it receives an <a href="/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_mouse_connect">IOCTL_INTERNAL_MOUSE_CONNECT</a> request. I8042prt sends a synchronous IOCTL_INTERNAL_I8042_HOOK_MOUSE request to the top of the mouse device stack.

After Moufiltr receives the hook mouse request, it filters the request in the following way:

<ul>
<li>
Saves the upper-level information passed to Moufiltr, which includes the context of an upper-level device object and a pointer to an ISR callback

</li>
<li>
Replaces the upper-level information with its own

</li>
<li>
Saves the context of I8042prt and pointers to callbacks that the Moufiltr ISR callbacks can use

</li>
</ul>
For more information about this request and the callbacks, see the following topics:

<dl>
<dd>

<a href="/windows-hardware/drivers/ddi/index">I8042prt Callback Routines</a>


</dd>
<dd>

<a href="/previous-versions/ff542384(v=vs.85)">Moufiltr Callback Routines</a>


</dd>
</dl>

## -ioctlparameters

### -input-buffer

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value greater than or equal to the size, in bytes, of an <a href="/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_hook_mouse">INTERNAL_I8042_HOOK_MOUSE</a> structure.

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_MOUSE structure that is allocated and set initially by I8042prt.

### -input-buffer-length

The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_MOUSE structure that is allocated and set initially by I8042prt.

### -output-buffer

None

### -output-buffer-length

None

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Status</b> member is set to one of the following values:




**STATUS_INVALID_PARAMETER**

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of an INTERNAL_I8042_HOOK_MOUSE structure.


**STATUS_SUCCESS**

The request completed successfully.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdd8042/ns-ntdd8042-_internal_i8042_hook_mouse">INTERNAL_I8042_HOOK_MOUSE</a>



<a href="/windows-hardware/drivers/ddi/kbdmou/ni-kbdmou-ioctl_internal_mouse_connect">IOCTL_INTERNAL_MOUSE_CONNECT</a>