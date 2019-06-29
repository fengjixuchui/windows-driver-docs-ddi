---
UID: NS:storport._MESSAGE_INTERRUPT_INFORMATION
title: _MESSAGE_INTERRUPT_INFORMATION (storport.h)
description: The MESSAGE_INTERRUPT_INFORMATION structure describes a message signaled interrupt (MSI).
old-location: storage\message_interrupt_information.htm
tech.root: storage
ms.assetid: 469896b3-3ae0-4edd-9fb0-ee5869633872
ms.date: 03/29/2018
ms.keywords: "*PMESSAGE_INTERRUPT_INFORMATION, MESSAGE_INTERRUPT_INFORMATION, MESSAGE_INTERRUPT_INFORMATION structure [Storage Devices], PMESSAGE_INTERRUPT_INFORMATION, PMESSAGE_INTERRUPT_INFORMATION structure pointer [Storage Devices], _MESSAGE_INTERRUPT_INFORMATION, storage.message_interrupt_information, storport/MESSAGE_INTERRUPT_INFORMATION, storport/PMESSAGE_INTERRUPT_INFORMATION, structs-storport_a918acbf-24eb-4112-8bab-bb2ee441064e.xml"
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
- storport.h
api_name:
- MESSAGE_INTERRUPT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: MESSAGE_INTERRUPT_INFORMATION, *PMESSAGE_INTERRUPT_INFORMATION
---

# _MESSAGE_INTERRUPT_INFORMATION structure


## -description


The <b>MESSAGE_INTERRUPT_INFORMATION</b> structure describes a message signaled interrupt (MSI).


## -struct-fields




### -field MessageId

An identifier identifies the MSI interrupt. A miniport driver can pass this value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportacquiremsispinlock">StorPortAcquireMSISpinLock</a> in the <i>MessageId</i> parameter to obtain a spin lock for synchronization purposes. 


### -field MessageData

The data associated with the message. 


### -field MessageAddress

The physical address associated with the message. 


### -field InterruptVector

The interrupt vector associated with the message. 


### -field InterruptLevel

The interrupt level associated with the message. 


### -field InterruptMode

A value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a> that specifies the interrupt mode associated with the message.  


## -remarks



Miniport drivers retrieve the MSI information in a <b>MESSAGE_INTERRUPT_INFORMATION</b> structure by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportgetmsiinfo">StorPortGetMSIInfo</a> routine. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportgetmsiinfo">StorPortGetMSIInfo</a>
 

 

