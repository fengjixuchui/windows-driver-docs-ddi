---
UID: NF:video.VideoPortCheckForDeviceExistence
title: VideoPortCheckForDeviceExistence function (video.h)
description: The VideoPortCheckForDeviceExistence function determines whether the specified PCI device exists in the system.
old-location: display\videoportcheckfordeviceexistence.htm
tech.root: display
ms.assetid: 2e0480a5-39d3-4977-9c0f-508bcf6c29a8
ms.date: 05/10/2018
keywords: ["VideoPortCheckForDeviceExistence function"]
ms.keywords: VideoPortCheckForDeviceExistence, VideoPortCheckForDeviceExistence function [Display Devices], VideoPort_Functions_3cb7198b-a2fe-423c-b0f3-11a154d087af.xml, display.videoportcheckfordeviceexistence, video/VideoPortCheckForDeviceExistence
f1_keywords:
 - "video/VideoPortCheckForDeviceExistence"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortCheckForDeviceExistence
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortCheckForDeviceExistence function


## -description


The <b>VideoPortCheckForDeviceExistence</b> function determines whether the specified PCI device exists in the system.


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VendorId [in]

Specifies the vendor ID.


### -param DeviceId [in]

Specifies the device ID.


### -param RevisionId [in]

Specifies the revision ID.


### -param SubVendorId [in]

Specifies the subvendor ID.


### -param SubSystemId [in]

Specifies the subsystem ID.


### -param Flags [in]

Is a set of flags that determine whether the <i>RevisionID</i> and <i>SubSystemID</i> parameters should be used in checking for the new device. This parameter can be the logical OR of the following values:

|Value|Meaning|
|--- |--- |
|CDE_USE_REVISION|Use the value in the RevisionID parameter in checking for the new device.|
|CDE_USE_SUBSYSTEM_IDS|Use the value in the SubSystemID parameter in checking for the new device.|
 
## -returns

<b>VideoPortCheckForDeviceExistence</b> returns <b>TRUE</b> if the device exists in the system, and <b>FALSE</b> otherwise.

## -remarks

For more information about PCI identifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>. 



