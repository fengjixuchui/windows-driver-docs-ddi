---
UID: NE:portabledevice.tagDELETE_OBJECT_OPTIONS
title: DELETE_OBJECT_OPTIONS (portabledevice.h)
description: The DELETE_OBJECT_OPTIONS enumeration type describes options that are supported by a device when deleting an object.
old-location: wpddk\delete_object_options.htm
tech.root: wpd_dk
ms.assetid: 38ad1645-1c38-440a-bec2-13052b9082a9
ms.date: 02/15/2018
keywords: ["tagDELETE_OBJECT_OPTIONS enumeration"]
ms.keywords: DELETE_OBJECT_OPTIONS, DELETE_OBJECT_OPTIONS enumeration, PORTABLE_DEVICE_DELETE_NO_RECURSION, PORTABLE_DEVICE_DELETE_WITH_RECURSION, enumeration, portabledevice/DELETE_OBJECT_OPTIONS, portabledevice/PORTABLE_DEVICE_DELETE_NO_RECURSION, portabledevice/PORTABLE_DEVICE_DELETE_WITH_RECURSION, tagDELETE_OBJECT_OPTIONS, wpddk.delete_object_options
req.header: portabledevice.h
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
req.irql: 
targetos: Windows
req.typenames: DELETE_OBJECT_OPTIONS
ms.custom: RS5
f1_keywords:
 - tagDELETE_OBJECT_OPTIONS
 - portabledevice/tagDELETE_OBJECT_OPTIONS
 - DELETE_OBJECT_OPTIONS
 - portabledevice/DELETE_OBJECT_OPTIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PortableDevice.h
api_name:
 - DELETE_OBJECT_OPTIONS
---

# tagDELETE_OBJECT_OPTIONS enumeration


## -description

The <b>DELETE_OBJECT_OPTIONS</b> enumeration type describes options that are supported by a device when deleting an object.

## -enum-fields

### -field PORTABLE_DEVICE_DELETE_NO_RECURSION

Delete the object only and fail if it has children.

### -field PORTABLE_DEVICE_DELETE_WITH_RECURSION

Delete the object and all its children.

## -remarks

An application can retrieve the deletion options that the device supports by calling the <b>IPortableDeviceCapabilities::GetCommandOptions</b> method for the <b>WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS</b> command. It should examine the <b>WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED</b> option value that this method returns in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevaluescollection">IPortableDeviceValuesCollection</a> object.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>

