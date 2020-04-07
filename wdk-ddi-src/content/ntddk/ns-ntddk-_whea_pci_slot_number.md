---
UID: NS:ntddk._WHEA_PCI_SLOT_NUMBER
title: _WHEA_PCI_SLOT_NUMBER (ntddk.h)
description: The WHEA_PCI_SLOT_NUMBER structure describes a logical PCI slot.
old-location: whea\whea_pci_slot_number.htm
tech.root: whea
ms.assetid: 4e2938a2-6301-4d2a-a467-eca1f5bbb260
ms.date: 02/20/2018
keywords: ["_WHEA_PCI_SLOT_NUMBER structure"]
ms.keywords: "*PWHEA_PCI_SLOT_NUMBER, PWHEA_PCI_SLOT_NUMBER, PWHEA_PCI_SLOT_NUMBER structure pointer [WHEA Drivers and Applications], WHEA_PCI_SLOT_NUMBER, WHEA_PCI_SLOT_NUMBER structure [WHEA Drivers and Applications], _WHEA_PCI_SLOT_NUMBER, ntddk/PWHEA_PCI_SLOT_NUMBER, ntddk/WHEA_PCI_SLOT_NUMBER, whea.whea_pci_slot_number, whearef_6999e061-3501-48fe-bd6c-383493056665.xml"
f1_keywords:
 - "ntddk/WHEA_PCI_SLOT_NUMBER"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
- ntddk.h
api_name:
- WHEA_PCI_SLOT_NUMBER
product:
- Windows
targetos: Windows
req.typenames: WHEA_PCI_SLOT_NUMBER, *PWHEA_PCI_SLOT_NUMBER
---

# _WHEA_PCI_SLOT_NUMBER structure


## -description


The WHEA_PCI_SLOT_NUMBER structure describes a logical PCI slot.


## -struct-fields




### -field u

A union that contains the following members:


### -field u.bits

A structure that describes the logical PCI slot.


### -field u.bits.DeviceNumber

The device number that is assigned to the logical PCI slot. 


### -field u.bits.FunctionNumber

The specific function on the device that is located in the logical PCI slot. 


### -field u.bits.Reserved

Reserved for system use. 


### -field u.AsULONG

A ULONG representation of the contents of the WHEA_PCI_SLOT_NUMBER structure.


## -remarks



A WHEA_PCI_SLOT_NUMBER structure is contained within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_bridge_descriptor">WHEA_AER_BRIDGE_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_endpoint_descriptor">WHEA_AER_ENDPOINT_DESCRIPTOR</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_rootport_descriptor">WHEA_AER_ROOTPORT_DESCRIPTOR</a> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_bridge_descriptor">WHEA_AER_BRIDGE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_endpoint_descriptor">WHEA_AER_ENDPOINT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_aer_rootport_descriptor">WHEA_AER_ROOTPORT_DESCRIPTOR</a>
 

 

