---
UID: NS:wdm._IO_INTERRUPT_MESSAGE_INFO
title: _IO_INTERRUPT_MESSAGE_INFO (wdm.h)
description: The IO_INTERRUPT_MESSAGE_INFO structure describes the driver's message-signaled interrupts.
old-location: kernel\io_interrupt_message_info.htm
tech.root: kernel
ms.assetid: d740d55e-6549-494d-9b2a-39d5c2e670d3
ms.date: 04/30/2018
ms.keywords: "*PIO_INTERRUPT_MESSAGE_INFO, IO_INTERRUPT_MESSAGE_INFO, IO_INTERRUPT_MESSAGE_INFO structure [Kernel-Mode Driver Architecture], PIO_INTERRUPT_MESSAGE_INFO, PIO_INTERRUPT_MESSAGE_INFO structure pointer [Kernel-Mode Driver Architecture], _IO_INTERRUPT_MESSAGE_INFO, kernel.io_interrupt_message_info, kstruct_b_e1d88b03-cc13-433c-b821-43315d776deb.xml, wdm/IO_INTERRUPT_MESSAGE_INFO, wdm/PIO_INTERRUPT_MESSAGE_INFO"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- Wdm.h
api_name:
- IO_INTERRUPT_MESSAGE_INFO
product:
- Windows
targetos: Windows
req.typenames: IO_INTERRUPT_MESSAGE_INFO, *PIO_INTERRUPT_MESSAGE_INFO
---

# _IO_INTERRUPT_MESSAGE_INFO structure


## -description


The <b>IO_INTERRUPT_MESSAGE_INFO</b> structure describes the driver's message-signaled interrupts.


## -struct-fields




### -field UnifiedIrql

Specifies the IRQL at which the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kmessage_service_routine">InterruptMessageService</a> routine runs. If the driver specified an interrupt spin lock for its interrupts, <b>UnifiedIrql</b> also specifies the IRQL at which the interrupt spin lock is acquired. 


### -field MessageCount

Specifies the number of message-signaled interrupts allocated for the driver.


### -field MessageInfo

Variable-length array that specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_interrupt_message_info_entry">IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structure for each message-signaled interrupt allocated for the driver. The <b>MessageCount</b> member specifies the number of entries in this array. 


## -remarks



When a driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a> to register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kmessage_service_routine">InterruptMessageService</a> routine, <b>IoConnectInterruptEx</b> provides a pointer to <b>IO_INTERRUPT_MESSAGE_INFO</b> in <i>Parameters</i>-><b>MessageBased.ConnectionContext</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_connect_interrupt_parameters">IO_CONNECT_INTERRUPT_PARAMETERS</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_connect_interrupt_parameters">IO_CONNECT_INTERRUPT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_interrupt_message_info_entry">IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioconnectinterruptex">IoConnectInterruptEx</a>
 

 

