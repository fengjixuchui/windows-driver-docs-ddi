---
UID: NE:wdm._IO_ALLOCATION_ACTION
title: _IO_ALLOCATION_ACTION (wdm.h)
description: The IO_ALLOCATION_ACTION enumerated type is used to specify return values for AdapterControl and ControllerControl routines.
old-location: kernel\io_allocation_action.htm
tech.root: kernel
ms.assetid: 245d35a1-e877-4446-a0da-e50ece3656b1
ms.date: 04/30/2018
keywords: ["IO_ALLOCATION_ACTION enumeration"]
ms.keywords: "*PIO_ALLOCATION_ACTION, DeallocateObject, DeallocateObjectKeepRegisters, IO_ALLOCATION_ACTION, IO_ALLOCATION_ACTION enumeration [Kernel-Mode Driver Architecture], KeepObject, PIO_ALLOCATION_ACTION, PIO_ALLOCATION_ACTION enumeration pointer [Kernel-Mode Driver Architecture], _IO_ALLOCATION_ACTION, kernel.io_allocation_action, sysenum_26c04e01-0e17-4f1b-93c9-b9ad8d9ca4d5.xml, wdm/DeallocateObject, wdm/DeallocateObjectKeepRegisters, wdm/IO_ALLOCATION_ACTION, wdm/KeepObject, wdm/PIO_ALLOCATION_ACTION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
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
req.typenames: IO_ALLOCATION_ACTION, *PIO_ALLOCATION_ACTION
f1_keywords:
 - _IO_ALLOCATION_ACTION
 - wdm/_IO_ALLOCATION_ACTION
 - PIO_ALLOCATION_ACTION
 - wdm/PIO_ALLOCATION_ACTION
 - IO_ALLOCATION_ACTION
 - wdm/IO_ALLOCATION_ACTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IO_ALLOCATION_ACTION
---

# _IO_ALLOCATION_ACTION enumeration


## -description

The <b>IO_ALLOCATION_ACTION</b> enumerated type is used to specify return values for <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_control">AdapterControl</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routines.

## -enum-fields

### -field KeepObject

Indicates that you want the driver to retain ownership of the adapter or controller object.

### -field DeallocateObject

Indicates that you do not want the driver to retain ownership of the adapter or controller object.

### -field DeallocateObjectKeepRegisters

<u>For adapter objects only.</u> Indicates that you do not want the driver to retain ownership of the adapter object, but you do want the driver to retain ownership of the allocated map registers.

## -remarks

If an <i>AdapterControl</i> or <i>ControllerControl</i> routine completes an IRP, or if it can set up an operation (such as a disk seek) for a target device object that could be overlapped with an operation for another device object, it should return <b>DeallocateObject</b>.

If a driver uses packet-based bus-master DMA, its <i>AdapterControl</i> routine should return <b>DeallocateObjectKeepRegisters</b>.

Otherwise, the driver should return <b>KeepObject</b>.