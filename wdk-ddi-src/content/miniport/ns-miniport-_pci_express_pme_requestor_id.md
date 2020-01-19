---
UID: NS:miniport._PCI_EXPRESS_PME_REQUESTOR_ID
title: _PCI_EXPRESS_PME_REQUESTOR_ID (miniport.h)
description: The PCI_EXPRESS_PME_REQUESTOR_ID structure describes the identifier of the requester of a power management event (PME).
old-location: pci\pci_express_pme_requestor_id.htm
tech.root: PCI
ms.assetid: 2305ffbd-22c8-4f63-bbe4-fd297bf98e39
ms.date: 02/24/2018
ms.keywords: "*PPCI_EXPRESS_PME_REQUESTOR_ID, PCI.pci_express_pme_requestor_id, PCI_EXPRESS_PME_REQUESTOR_ID, PCI_EXPRESS_PME_REQUESTOR_ID union [Buses], PPCI_EXPRESS_PME_REQUESTOR_ID, PPCI_EXPRESS_PME_REQUESTOR_ID union pointer [Buses], _PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PCI_EXPRESS_PME_REQUESTOR_ID, ntddk/PPCI_EXPRESS_PME_REQUESTOR_ID, pci_struct_0cb11d1f-7426-42fc-9d77-373516a492ae.xml"
ms.topic: struct
f1_keywords:
 - "miniport/PCI_EXPRESS_PME_REQUESTOR_ID"
req.header: miniport.h
req.include-header: Ntddk.h, Miniport.h
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PCI_EXPRESS_PME_REQUESTOR_ID
product:
- Windows
targetos: Windows
req.typenames: PCI_EXPRESS_PME_REQUESTOR_ID, *PPCI_EXPRESS_PME_REQUESTOR_ID
---

# _PCI_EXPRESS_PME_REQUESTOR_ID structure


## -description


The PCI_EXPRESS_PME_REQUESTOR_ID structure describes the identifier of the requester of a power management event (PME).


## -syntax


```cpp
typedef union _PCI_EXPRESS_PME_REQUESTOR_ID {
  struct {
    USHORT FunctionNumber  :3;
    USHORT DeviceNumber  :5;
    USHORT BusNumber  :3;
  };
  USHORT AsUSHORT;
} PCI_EXPRESS_PME_REQUESTOR_ID, *PPCI_EXPRESS_PME_REQUESTOR_ID;
```


## -struct-fields




### -field DUMMYSTRUCTNAME




### -field AsUSHORT

A USHORT representation of the contents of the PCI_EXPRESS_PME_REQUESTOR_ID structure.


#### - BusNumber

The bus number of the requester.


#### - DeviceNumber

The device number of the requester.


#### - FunctionNumber

The function number of the requester.


## -remarks



The PCI_EXPRESS_PME_REQUESTOR_ID structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_PME_REQUESTOR_ID structure is contained in the <b>PMERequestorId</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_status_register">PCI_EXPRESS_ROOT_STATUS_REGISTER</a> structure.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_pci_express_root_status_register">PCI_EXPRESS_ROOT_STATUS_REGISTER</a>



 

 


