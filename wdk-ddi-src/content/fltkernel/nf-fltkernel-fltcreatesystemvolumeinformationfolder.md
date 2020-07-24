---
UID: NF:fltkernel.FltCreateSystemVolumeInformationFolder
title: FltCreateSystemVolumeInformationFolder function (fltkernel.h)
description: FltCreateSystemVolumeInformationFolder verifies the existence of the "System Volume Information" folder on a file system volume. If the folder is not present, then the folder is created.
old-location: ifsk\fltcreatesystemvolumeinformationfolder.htm
tech.root: ifsk
ms.assetid: 1da9bd59-d45e-40e0-9947-c4f56309acc7
ms.date: 04/16/2018
keywords: ["FltCreateSystemVolumeInformationFolder function"]
ms.keywords: FltApiRef_a_to_d_cceaf5ba-8497-4026-94af-8b59afe9c24d.xml, FltCreateSystemVolumeInformationFolder, FltCreateSystemVolumeInformationFolder function [Installable File System Drivers], fltkernel/FltCreateSystemVolumeInformationFolder, ifsk.fltcreatesystemvolumeinformationfolder
f1_keywords:
 - "fltkernel/FltCreateSystemVolumeInformationFolder"
 - "FltCreateSystemVolumeInformationFolder"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCreateSystemVolumeInformationFolder
targetos: Windows
req.typenames: 
---

# FltCreateSystemVolumeInformationFolder function

## -description

**FltCreateSystemVolumeInformationFolder** verifies the existence of the "System Volume Information" folder on a file system volume. If the folder is not present, then the folder is created.

## -parameters

### -param Instance [in]

Opaque instance pointer for an instance that is attached to the volume.

## -returns

**FltCreateSystemVolumeInformationFolder** returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 

|Return code|Description|
|----|----|
|**STATUS_INSUFFICIENT_RESOURCES**|A temporary buffer required by this function could not be allocated.|

## -remarks

**FltCreateSystemVolumeInformationFolder** verifies the existence of the "System Volume Information" folder in the root directory of the volume to which the given *Instance* is attached.

If the folder is not present, then the folder is created. If the volume is an NTFS volume, the folder is created with an access control list ([ACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)) containing one access control entry ([ACE](https://docs.microsoft.com/windows-hardware/drivers/ifs/ace)) indicating full access for the local SYSTEM account, and the ACE will have the inheritance bits set. The folder will be created with the FILE_ATTRIBUTE_HIDDEN and FILE_ATTRIBUTE_SYSTEM attributes set.

If the folder is already present and the volume is an NTFS volume, the ACE that indicates full control for SYSTEM will be checked and if necessary modified to have the inheritance bits set.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## -see-also

[ACE](https://docs.microsoft.com/windows-hardware/drivers/ifs/ace)

[ACL](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl)

[RtlCreateSystemVolumeInformationFolder](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-rtlcreatesystemvolumeinformationfolder)
