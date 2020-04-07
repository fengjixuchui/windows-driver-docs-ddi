---
UID: NF:ntddk.IoReportDetectedDevice
title: IoReportDetectedDevice function (ntddk.h)
description: The IoReportDetectedDevice routine reports a non-PnP device to the PnP manager.
old-location: kernel\ioreportdetecteddevice.htm
tech.root: kernel
ms.assetid: b7756f69-feab-4a28-88d5-0262f86db54b
ms.date: 04/30/2018
keywords: ["IoReportDetectedDevice function"]
ms.keywords: IoReportDetectedDevice, IoReportDetectedDevice routine [Kernel-Mode Driver Architecture], k104_b906486e-318a-49b5-aa6a-683c1889c10b.xml, kernel.ioreportdetecteddevice, ntddk/IoReportDetectedDevice
f1_keywords:
 - "ntddk/IoReportDetectedDevice"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoReportDetectedDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoReportDetectedDevice function


## -description


The <b>IoReportDetectedDevice</b> routine reports a non-PnP device to the PnP manager.


## -parameters




### -param DriverObject [in]

Pointer to the driver object of the driver that detected the device.


### -param LegacyBusType [in]

Specifies the type of bus on which the device resides. The PnP manager uses this information to match the reported device to its PnP-enumerated instance, if one exists.

The interface types, such as <b>PCIBus</b>, are defined in Wdm.h. If a driver does not know the <i>LegacyBusType</i> for the device, the driver supplies the value <b>InterfaceTypeUndefined</b> for this parameter.


### -param BusNumber [in]

Specifies the bus number for the device. The PnP manager uses this information to match the reported device to its PnP-enumerated instance, if one exists.

The bus number distinguishes the bus on which the device resides from other buses of the same type on the computer. The bus-numbering scheme is bus-specific. If a driver does not know the <i>BusNumber</i> for the device, the driver supplies the value -1 for this parameter. 


### -param SlotNumber [in]

Specifies the logical slot number of the device. The PnP manager uses this information to match the reported device to its PnP-enumerated instance, if one exists.

If a driver does not know the <i>SlotNumber</i> for the device, the driver supplies the value -1 for this parameter.


### -param ResourceList [in, optional]

Pointer to the resource list the driver used to detect the device. Resources in this list are in raw, untranslated form. 


### -param ResourceRequirements [in, optional]

Optionally points to a resource requirements list for the detected device. <b>NULL</b> if the caller does not have this information for the device.


### -param ResourceAssigned [in]

Specifies whether the device's resources have already been reported to the PnP manager. If <i>ResourceAssigned</i> is <b>TRUE</b>, the resources have already been reported, possibly with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportresourcefordetection">IoReportResourceForDetection</a>, and the PnP manager will not attempt to claim them on behalf of the device. If <b>TRUE</b>, the PnP manager will also not claim resources when the device is root-enumerated on subsequent boots.


### -param DeviceObject [in, out]

Optionally points to a PDO for the detected device. 

<b>NULL</b> if the caller does not have a PDO for the device, which is typically the case. If <i>DeviceObject</i> is <b>NULL</b>, the PnP manager creates a PDO for the device and returns a pointer to the caller.

If the caller supplies a PDO, the PnP manager does not create a new PDO. On a given call to this routine the <i>DeviceObject</i> parameter is either an IN or an OUT parameter, but not both. 


## -returns



<b>IoReportDetectedDevice</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -remarks



Drivers for legacy devices use <b>IoReportDetectedDevice</b> to report their devices to the system. A driver should only call <b>IoReportDetectedDevice</b> to report a legacy, non-PnP device. PnP devices should be reported in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> request.

Drivers only need to call <b>IoReportDetectedDevice</b> the first time they are loaded because the PnP manager caches the reported information. Drivers that use this routine should store a flag in the registry to indicate whether they have already done device detection.

A driver typically calls this routine from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. A few drivers, like certain NDIS or EISA drivers, might call this routine from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

On successful completion of <b>IoReportDetectedDevice</b>, the caller should attach an FDO to the PDO returned at <i>DeviceObject</i>. Once the caller attaches its FDO, the caller is the function driver for the device, at least temporarily. There are no filter drivers. The PnP manager owns the PDO.

The PnP manager considers the device to be started and therefore does not call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine and does not send an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a> request. The driver must be prepared to handle all other PnP IRPs, however. 

<b>IoReportDetectedDevice</b> marks the device as a root-enumerated device and this identification is persistent across system boots. During subsequent system boots the PnP manager "detects" the device on the root-enumerated list and configures it like a PnP device: the PnP manager queries for device information, identifies the appropriate drivers and calls their <i>AddDevice</i> routines, and sends all the appropriate PnP IRPs.

The system generates two compatible ID strings for the device, of the form DETECTED<i>Interface</i>\<i>Driver</i> and DETECTED\<i>Driver</i>. <i>Interface</i> is the string name of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_interface_type">INTERFACE_TYPE</a> of the first bus specified in the <i>ResourceList</i> parameter. <i>Interface</i> is set to "Internal" if no bus is specified. <i>Driver</i> is the driver's service name. A driver can provide additional hardware IDs or compatible IDs by handling the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-id">IRP_MN_QUERY_ID</a> request.

A driver writer must provide an INF file that matches any of the specified hardware IDs or compatible IDs. The INF file should specify the original driver that called <b>IoReportDetectedDevice</b> as the driver to load for those IDs. The system uses this information to rebuild the driver stack for the device, for example on restart. Callers of <b>IoReportDetectedDevice</b> must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreportresourcefordetection">IoReportResourceForDetection</a>
 

 

