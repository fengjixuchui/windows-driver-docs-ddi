---
UID: NS:ntddstor._DEVICE_DATA_SET_REPAIR_PARAMETERS
title: _DEVICE_DATA_SET_REPAIR_PARAMETERS (ntddstor.h)
description: The DEVICE_DATA_SET_REPAIR_PARAMETERS structure specifies the parameters of a storage spaces repair operation specified for a data set management action.
old-location: storage\device_data_set_repair_parameters.htm
tech.root: storage
ms.assetid: BBA834D0-4D21-42EF-98B0-9AF3FF28E6E2
ms.date: 03/29/2018
ms.keywords: "*PDEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS structure [Storage Devices], PDEVICE_DATA_SET_REPAIR_PARAMETERS, PDEVICE_DATA_SET_REPAIR_PARAMETERS structure pointer [Storage Devices], _DEVICE_DATA_SET_REPAIR_PARAMETERS, ntddstor/DEVICE_DATA_SET_REPAIR_PARAMETERS, ntddstor/PDEVICE_DATA_SET_REPAIR_PARAMETERS, storage.device_data_set_repair_parameters"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- ntddstor.h
api_name:
- DEVICE_DATA_SET_REPAIR_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DATA_SET_REPAIR_PARAMETERS, *PDEVICE_DATA_SET_REPAIR_PARAMETERS
---

# _DEVICE_DATA_SET_REPAIR_PARAMETERS structure


## -description


The <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b> structure specifies the parameters of a  storage spaces  repair operation specified for a data set management action.

This parameter structure is used in a repair action for an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.  The <b>Action</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure is set to <b>DeviceDsmAction_Repair</b>, and <b>ParameterBlockOffset</b> indicates the location of <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b>.


## -struct-fields




### -field NumberOfRepairCopies

The total  number of copies to repair.


### -field SourceCopy

The source copy number.


### -field RepairCopies

An array of copy numbers for the copies to repair.


## -remarks



The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members  of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> are set to the location and length of the  <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b> structure in the system buffer of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.

The <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> specify the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_data_set_range">DEVICE_DATA_SET_RANGE</a> structures containing the extents of the repair copies.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/device-data-management-set-action">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ns-ntddstor-_device_manage_data_set_attributes">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_manage_data_set_attributes">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

