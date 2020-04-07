---
UID: NS:wdm._PCI_EXPRESS_AER_CAPABILITIES
title: _PCI_EXPRESS_AER_CAPABILITIES (wdm.h)
description: The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_aer_capabilities.htm
tech.root: PCI
ms.assetid: 7cb25991-4e82-4da2-9d1f-fadc035b25a3
ms.date: 02/24/2018
keywords: ["_PCI_EXPRESS_AER_CAPABILITIES structure"]
ms.keywords: "*PPCI_EXPRESS_AER_CAPABILITIES, PCI.pci_express_aer_capabilities, PCI_EXPRESS_AER_CAPABILITIES, PCI_EXPRESS_AER_CAPABILITIES union [Buses], PPCI_EXPRESS_AER_CAPABILITIES, PPCI_EXPRESS_AER_CAPABILITIES union pointer [Buses], _PCI_EXPRESS_AER_CAPABILITIES, pci_struct_e316ea91-d32a-4726-ba80-8fc6bd8e3163.xml, wdm/PCI_EXPRESS_AER_CAPABILITIES, wdm/PPCI_EXPRESS_AER_CAPABILITIES"
f1_keywords:
 - "wdm/PCI_EXPRESS_AER_CAPABILITIES"
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_EXPRESS_AER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_AER_CAPABILITIES, *PPCI_EXPRESS_AER_CAPABILITIES
req.product: Windows 10 or later.
---

# _PCI_EXPRESS_AER_CAPABILITIES structure


## -description


The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure.


## -syntax


```cpp
typedef union _PCI_EXPRESS_AER_CAPABILITIES {
  struct {
    ULONG FirstErrorPointer  :5;
    ULONG ECRCGenerationCapable  :1;
    ULONG ECRCGenerationEnable  :1;
    ULONG ECRCCheckCapable  :1;
    ULONG ECRCCheckEnable  :1;
    ULONG Reserved  :23;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_AER_CAPABILITIES, *PPCI_EXPRESS_AER_CAPABILITIES;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_AER_CAPABILITIES structure.


#### - ECRCCheckCapable

A single bit that indicates that the device is capable of checking ECRC.


#### - ECRCCheckEnable

A single bit that indicates that ECRC checking is enabled.


#### - ECRCGenerationCapable

A single bit that indicates that the device is capable of generating end-to-end cyclic redundancy checks (ECRC).


#### - ECRCGenerationEnable

A single bit that indicates that ECRC generation is enabled.


#### - FirstErrorPointer

The bit position of the first error that was reported in the PCIe uncorrectable error status register.


#### - Reserved

Reserved.


## -remarks



The PCI_EXPRESS_AER_CAPABILITIES structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_AER_CAPABILITIES structure is contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a> structures.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_aer_capability">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_rootport_aer_capability">PCI_EXPRESS_ROOTPORT_AER_CAPABILITY</a>



 

 


