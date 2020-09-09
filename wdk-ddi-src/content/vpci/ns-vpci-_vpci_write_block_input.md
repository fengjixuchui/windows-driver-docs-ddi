---
UID: NS:vpci._VPCI_WRITE_BLOCK_INPUT
title: _VPCI_WRITE_BLOCK_INPUT (vpci.h)
description: The VPCI_WRITE_BLOCK_INPUT structure is used in an IOCTL_VPCI_WRITE_BLOCK IOCTL request to write data to a specified configuration block for a PCI Express (PCIe) virtual function (VF).
old-location: kernel\vpci_write_block_input.htm
tech.root: pci
ms.assetid: 57519a7c-7710-4482-82f2-32067b1af22f
ms.date: 04/30/2018
keywords: ["VPCI_WRITE_BLOCK_INPUT structure"]
ms.keywords: "*PVPCI_WRITE_BLOCK_INPUT, PVPCI_WRITE_BLOCK_INPUT, PVPCI_WRITE_BLOCK_INPUT structure pointer [Kernel-Mode Driver Architecture], VPCI_WRITE_BLOCK_INPUT, VPCI_WRITE_BLOCK_INPUT structure [Kernel-Mode Driver Architecture], _VPCI_WRITE_BLOCK_INPUT, kernel.vpci_write_block_input, vpci/PVPCI_WRITE_BLOCK_INPUT, vpci/VPCI_WRITE_BLOCK_INPUT"
req.header: vpci.h
req.include-header: Vpci.h
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
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
f1_keywords:
 - _VPCI_WRITE_BLOCK_INPUT
 - vpci/_VPCI_WRITE_BLOCK_INPUT
 - PVPCI_WRITE_BLOCK_INPUT
 - vpci/PVPCI_WRITE_BLOCK_INPUT
 - VPCI_WRITE_BLOCK_INPUT
 - vpci/VPCI_WRITE_BLOCK_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Vpci.h
api_name:
 - VPCI_WRITE_BLOCK_INPUT
---

# _VPCI_WRITE_BLOCK_INPUT structure


## -description

The <b>VPCI_WRITE_BLOCK_INPUT</b> structure is used in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a> IOCTL request to write data to a specified configuration block for a PCI Express (PCIe) virtual function (VF).

This IOCTL request is issued by the driver of a PCIe  VF on a device that supports the single root I/O virtualization (SR-IOV) interface.

## -struct-fields

### -field BlockId

A <b>ULONG</b> value that specifies the VF configuration block to be read.  This value is defined by the driver for the PCIe physical function (PF) of the device.

### -field DataLength

The size, in bytes, of the data to be written from the <b>Data</b> member.

### -field Data

A variable-size array that contains the data to be written to the configuration block that is specified by the <b>BlockId</b> member.

## -remarks

A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the drivers of the PF and VF.</div>
<div> </div>

## -see-also

<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/vpci/ni-vpci-ioctl_vpci_write_block">IOCTL_VPCI_WRITE_BLOCK</a>

