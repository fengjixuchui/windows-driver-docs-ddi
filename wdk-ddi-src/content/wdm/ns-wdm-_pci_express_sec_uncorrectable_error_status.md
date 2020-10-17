---
UID: NS:wdm._PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
title: _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS (wdm.h)
description: The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure.
old-location: pci\pci_express_sec_uncorrectable_error_status.htm
tech.root: PCI
ms.assetid: 8f6b1764-e2c0-4c9e-a2ec-56cc19520d2e
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure"]
ms.keywords: "*PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PCI.pci_express_sec_uncorrectable_error_status, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union [Buses], PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS union pointer [Buses], _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, pci_struct_cb52bea2-b001-47a7-bad9-9816787133d3.xml, wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS"
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
targetos: Windows
req.typenames: PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
req.product: Windows 10 or later.
f1_keywords:
 - _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - wdm/_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - wdm/PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
 - wdm/PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS
---

# _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure (wdm.h)


## -description

The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure.


#### - DelayedTransactionDiscardTimerExpired

A single bit that indicates that the delayed transaction discard timer has expired.


#### - InternalBridgeError

A single bit that indicates that an internal bridge error has occurred.


#### - MasterAbortOnSplitCompletion

A single bit that indicates that a master abort on split completion has occurred.


#### - PERRAsserted

A single bit that indicates that a PERR# assertion was detected.


#### - ReceivedMasterAbort

A single bit that indicates that a master abort has been received.


#### - ReceivedTargetAbort

A single bit that indicates that a target abort has been received.


#### - Reserved

Reserved for system use.


#### - RsvdZ

Reserved for system use.


#### - SERRAsserted

A single bit that indicates that a SERR# assertion was detected.


#### - TargetAbortOnSplitCompletion

A single bit that indicates that a target abort on split completion has occurred.


#### - UncorrectableAddressError

A single bit that indicates that an uncorrectable address error has occurred.


#### - UncorrectableAttributeError

A single bit that indicates that an uncorrectable attribute error has occurred.


#### - UncorrectableDataError

A single bit that indicates that an uncorrectable data error has occurred.


#### - UncorrectableSplitCompletion

A single bit that indicates that an uncorrectable split completion message data error has occurred.


#### - UnexpectedSplitCompletionError

A single bit that indicates that an unexpected split completion error has occurred.

## -syntax

```cpp
typedef union _PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS {
  struct {
    ULONG TargetAbortOnSplitCompletion  :1;
    ULONG MasterAbortOnSplitCompletion  :1;
    ULONG ReceivedTargetAbort  :1;
    ULONG ReceivedMasterAbort  :1;
    ULONG RsvdZ  :1;
    ULONG UnexpectedSplitCompletionError  :1;
    ULONG UncorrectableSplitCompletion  :1;
    ULONG UncorrectableDataError  :1;
    ULONG UncorrectableAttributeError  :1;
    ULONG UncorrectableAddressError  :1;
    ULONG DelayedTransactionDiscardTimerExpired  :1;
    ULONG PERRAsserted  :1;
    ULONG SERRAsserted  :1;
    ULONG InternalBridgeError  :1;
    ULONG Reserved  :18;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS, *PPCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS;
```

## -remarks

The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure is contained in the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_express_bridge_aer_capability">PCI_EXPRESS_BRIDGE_AER_CAPABILITY</a>