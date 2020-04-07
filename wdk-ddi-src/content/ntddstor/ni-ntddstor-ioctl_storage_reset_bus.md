---
UID: NI:ntddstor.IOCTL_STORAGE_RESET_BUS
title: IOCTL_STORAGE_RESET_BUS (ntddstor.h)
description: Resets an I/O bus and, indirectly, each device on the bus.
old-location: storage\ioctl_storage_reset_bus.htm
tech.root: storage
ms.assetid: 26c9d499-2d53-48b8-8704-3ec7b15e15d8
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_RESET_BUS IOCTL"]
ms.keywords: IOCTL_STORAGE_RESET_BUS, IOCTL_STORAGE_RESET_BUS control, IOCTL_STORAGE_RESET_BUS control code [Storage Devices], k307_8a5629b9-44e4-4ed7-a481-a5b9efbeb083.xml, ntddstor/IOCTL_STORAGE_RESET_BUS, storage.ioctl_storage_reset_bus
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_RESET_BUS"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- Ntddstor.h
api_name:
- IOCTL_STORAGE_RESET_BUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_RESET_BUS IOCTL


## -description



Resets an I/O bus and, indirectly, each device on the bus. Resetting the bus clears all device reservations and transfer speed settings, which must then be renegotiated, making it a time-consuming operation that should be used very rarely. The caller requires only read access to issue a bus reset. 

The <b>SrbStatus</b> flag of pending SRBs is set to SRB_STATUS_BUS_RESET. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_bus_reset_request">STORAGE_BUS_RESET_REQUEST</a> structure that specifies the path ID of the bus to reset.


### -input-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_bus_reset_request">STORAGE_BUS_RESET_REQUEST</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, or STATUS_INVALID_DEVICE_REQUEST.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_bus_reset_request">STORAGE_BUS_RESET_REQUEST</a>
 

 

