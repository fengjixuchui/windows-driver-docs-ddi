---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_SET_PROPERTY
title: IOCTL_POINT_OF_SERVICE_SET_PROPERTY (pointofservicedriverinterface.h)
description: This I/O control function sets the specified property on the device.
old-location: pos\ioctl_point_of_service_set_property.htm
tech.root: pos
ms.assetid: 8907a99f-37b0-4c09-b92a-ac720328020e
ms.date: 02/23/2018
keywords: ["IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_SET_PROPERTY, IOCTL_POINT_OF_SERVICE_SET_PROPERTY control, IOCTL_POINT_OF_SERVICE_SET_PROPERTY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_SET_PROPERTY, pos.ioctl_point_of_service_set_property
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_SET_PROPERTY"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
- pointofservicedriverinterface.h
api_name:
- IOCTL_POINT_OF_SERVICE_SET_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL


## -description


This I/O control function sets the specified property on the device.


## -ioctlparameters




### -input-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ne-pointofservicedriverinterface-_pospropertyid">PosPropertyId</a> of the property to set followed by the value of the property. The encoding for the type follows the property ID in the byte stream.


### -input-buffer-length

Set to sizeof(<i>PosPropertyId</i>) + the size of the property value.


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following is a common error value (other return values may be returned as defined by your property callback implementation):

- STATUS_ACCESS_DENIED: The device is currently claimed by another client.

The client must successfully call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a> before using this IOCTL.
