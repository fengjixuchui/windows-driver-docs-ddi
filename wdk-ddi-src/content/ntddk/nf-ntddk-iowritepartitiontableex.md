---
UID: NF:ntddk.IoWritePartitionTableEx
title: IoWritePartitionTableEx function (ntddk.h)
description: The IoWritePartitionTableEx routine writes partition tables from the entries in the partition list buffer for each partition on the disk represented by the given device object.
old-location: storage\iowritepartitiontableex.htm
tech.root: storage
ms.assetid: b49ea2db-bb1e-4293-bfac-cbb3e62bca91
ms.date: 03/29/2018
keywords: ["IoWritePartitionTableEx function"]
ms.keywords: IoWritePartitionTableEx, IoWritePartitionTableEx routine [Storage Devices], ntddk/IoWritePartitionTableEx, rtns-disk_b84c8b07-5cdc-4e39-964f-a8f6b28e7346.xml, storage.iowritepartitiontableex
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWritePartitionTableEx
 - ntddk/IoWritePartitionTableEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWritePartitionTableEx
---

# IoWritePartitionTableEx function


## -description

The <b>IoWritePartitionTableEx</b> routine writes partition tables from the entries in the partition list buffer for each partition on the disk represented by the given device object.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object representing the disk whose partition tables are to be written.

### -param DriveLayout

<p>Pointer to the drive layout buffer that contains the partition list entries. For more detailed information see <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information_ex"><b>DRIVE_LAYOUT_INFORMATION_EX</b></a>.</p>

## -returns

<b>IoWritePartitionTabloEx</b> returns a status code of STATUS_SUCCESS if all writes were completed without error. In case of failure, the error codes returned by <b>IoWritePartitionTableEx</b> might include, but are not limited to, the following list:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
Indicates a failure read the correct disk geometry.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates a failure to allocate necessary resources (for example, heap memory, IRPs, and so on).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that sector zero did not have the expected MBR disk signature.

</td>
</tr>
</table>

## -remarks

<b>IoWritePartitionTableEx</b> replaces the obsolete routine <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iowritepartitiontable">IoWritePartitionTable</a>. Unlike the older routine, it can write to GUID Partition Tables as well as Master Boot Record Partition Tables. 

<b>IoWritePartitionTableEx</b> must only be used by disk drivers. Other drivers should use the <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_set_drive_layout_ex">IOCTL_DISK_SET_DRIVE_LAYOUT_EX</a> disk I/O request instead.

When a disk device driver receives an IRP_MJ_DEVICE_CONTROL request to set the partition type in a partition table entry, or to repartition the disk, it should call <b>IoWritePartionTableEx</b>. The device control request is generally issued by the format utility, which performs I/O control functions on the partitions and disks in the machine.

To reset a partition type, the driver passes a pointer to the device object, representing the physical disk, and the number of the partition associated with the device object that the format utility has open. When a disk is to be repartitioned dynamically, the disk driver must tear down its set of device objects representing the current disk partitions and create a new set of device objects representing the new partitions on the disk.

In order tot create or delete partitions a full description of the system must be obtained by a call to <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontableex">IoReadPartitionTableEx</a>. The drive layout structure can be modified by the system format utility to reflect a new configuration of the disk.

<b>IoWritePartitionTableEx</b> is synchronous. It must be called by the disk driver's Dispatch routine or by a driver thread. Thus, all user and file system threads must be prepared to enter a wait state when issuing the device control request to reset partition types for the device.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontableex">IoReadPartitionTableEx</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetpartitioninformationex">IoSetPartitionInformationEx</a>