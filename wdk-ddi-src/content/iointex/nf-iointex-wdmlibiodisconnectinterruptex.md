---
UID: NF:iointex.WdmlibIoDisconnectInterruptEx
title: WdmlibIoDisconnectInterruptEx function (iointex.h)
description: The WdmlibIoDisconnectInterruptEx function unregisters an interrupt service routine (ISR) that was registered by a previous call to the WdmlibIoConnectInterruptEx function.
old-location: kernel\wdmlibiodisconnectinterruptex.htm
tech.root: kernel
ms.assetid: B6F8663C-3A13-45DA-80FE-CC8B9194D083
ms.date: 04/30/2018
keywords: ["WdmlibIoDisconnectInterruptEx function"]
ms.keywords: IoDisconnectInterruptEx, WdmlibIoDisconnectInterruptEx, WdmlibIoDisconnectInterruptEx function [Kernel-Mode Driver Architecture], iointex/IoDisconnectInterruptEx, iointex/WdmlibIoDisconnectInterruptEx, kernel.wdmlibiodisconnectinterruptex
req.header: iointex.h
req.include-header: Iointex.h, Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista. Drivers that must also work Microsoft Windows 2000, Windows XP, or Windows Server 2003 can instead link to Iointex.lib to use the routine.
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
req.lib: NtosKrnl.lib; Iointex.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdmlibIoDisconnectInterruptEx
 - iointex/WdmlibIoDisconnectInterruptEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - WdmlibIoDisconnectInterruptEx
 - IoDisconnectInterruptEx
---

# WdmlibIoDisconnectInterruptEx function


## -description

The  <b>WdmlibIoDisconnectInterruptEx</b> function unregisters an interrupt service routine (ISR) that was registered by a previous call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a> function.

## -parameters

### -param Parameters 

[in, out]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_disconnect_interrupt_parameters">IO_DISCONNECT_INTERRUPT_PARAMETERS</a> structure that contains the connection context for  the interrupt being disconnected.

## -returns

None.

## -remarks

The driver should configure the device to issue interrupts only when these interrupts are connected. Failure to prevent a device from issuing interrupts when the interrupts are disconnected might cause system instability. For example, if a device shares a level-triggered interrupt line with other devices, and the device issues an interrupt request when the device's interrupts are disconnected, the other devices on the line will not acknowledge the interrupt and the interrupt will continue to fire. Before calling <b>WdmlibIoDisconnectInterruptEx</b>, the driver should configure the device to stop issuing interrupts. After calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a>, the driver should configure the device to start issuing interrupts.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_disconnect_interrupt_parameters">IO_DISCONNECT_INTERRUPT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iointex/nf-iointex-wdmlibioconnectinterruptex">WdmlibIoConnectInterruptEx</a>

