---
UID: NI:pcivirt.IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
title: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE (pcivirt.h)
description: The IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request indicates that the virtualization stack wants to update to the mitigation ranges.
old-location: pci\ioctl-sriov-mitigated-range-update.htm
tech.root: PCI
ms.assetid: f49e6d9e-0b62-4742-9868-1717f8482d9a
ms.date: 02/24/2018
ms.keywords: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE, IOCTL_SRIOV_MITIGATED_RANGE_UPDATE control code [Buses], PCI.ioctl-sriov-mitigated-range-update, pcivirt/IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
ms.topic: ioctl
f1_keywords:
 - "pcivirt/IOCTL_SRIOV_MITIGATED_RANGE_UPDATE"
req.header: pcivirt.h
req.include-header:
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_MITIGATED_RANGE_UPDATE IOCTL


##  Major Code:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>

## -description


The  <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request indicates that the virtualization stack wants to update to the mitigation ranges.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ns-pcivirt-_sriov_mitigated_range_update_input">SRIOV_MITIGATED_RANGE_UPDATE_INPUT</a> structure.


### -input-buffer-length
Size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ns-pcivirt-_sriov_mitigated_range_update_input">SRIOV_MITIGATED_RANGE_UPDATE_INPUT</a> structure.


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code.


## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes MITIGABLE_DEVICE_INTERFACE.

The stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. When that range of memory is updated, the stack sends this request.

The physical function (PF driver) keeps the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request in its queue until the request is either cancelled by the virtualization stack or the PF driver
wants to send a request to the virtual function (VF) driver to update to the mitigation ranges for
a particular VF.  When the VF completes the request, the PF completes the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request.  Upon completion, the virtualization stack reinitializes the mitigation
maps by sending <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> and
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_ranges">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> requests.  The stack may additionally  call any
user mode device simulation for additional ranges to mitigate. The <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request is sent for each active virtual function.



