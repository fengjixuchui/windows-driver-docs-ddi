---
UID: NS:mountmgr._MOUNTMGR_MOUNT_POINTS
title: _MOUNTMGR_MOUNT_POINTS (mountmgr.h)
description: The MOUNTMGR_MOUNT_POINTS structure is used by mount manager to send a client the list of mount points associated with a device.
old-location: storage\mountmgr_mount_points.htm
tech.root: storage
ms.assetid: e85c0d92-d989-4afc-8516-c63535d2c728
ms.date: 03/29/2018
keywords: ["MOUNTMGR_MOUNT_POINTS structure"]
ms.keywords: "*PMOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS, MOUNTMGR_MOUNT_POINTS structure [Storage Devices], PMOUNTMGR_MOUNT_POINTS, PMOUNTMGR_MOUNT_POINTS structure pointer [Storage Devices], _MOUNTMGR_MOUNT_POINTS, mountmgr/MOUNTMGR_MOUNT_POINTS, mountmgr/PMOUNTMGR_MOUNT_POINTS, storage.mountmgr_mount_points, structs-mntmgr_844fdf51-1324-4b1d-b68f-abba5f471652.xml"
req.header: mountmgr.h
req.include-header: Mountmgr.h
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
req.typenames: MOUNTMGR_MOUNT_POINTS, *PMOUNTMGR_MOUNT_POINTS
f1_keywords:
 - _MOUNTMGR_MOUNT_POINTS
 - mountmgr/_MOUNTMGR_MOUNT_POINTS
 - PMOUNTMGR_MOUNT_POINTS
 - mountmgr/PMOUNTMGR_MOUNT_POINTS
 - MOUNTMGR_MOUNT_POINTS
 - mountmgr/MOUNTMGR_MOUNT_POINTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mountmgr.h
api_name:
 - MOUNTMGR_MOUNT_POINTS
---

# _MOUNTMGR_MOUNT_POINTS structure


## -description

The MOUNTMGR_MOUNT_POINTS structure is used by mount manager to send a client the list of mount points associated with a device.

## -struct-fields

### -field Size

Contains the size, in bytes, of the output buffer.

### -field NumberOfMountPoints

Contains the number of mount points that the mount manager is returning.

### -field MountPoints

Contains an array of elements of type MOUNTMGR_MOUNT_POINT that contain information about each mount point associated with the device.

## -remarks

For a discussion of the different between symbolic links, unique IDs, and nonpersistent device names, see <a href="/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver">Supporting Mount Manager Requests in a Storage Class Driver</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/mountmgr/ni-mountmgr-ioctl_mountmgr_query_points">IOCTL_MOUNTMGR_QUERY_POINTS</a>