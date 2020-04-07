---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
title: IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION (pointofservicedriverinterface.h)
description: This I/O control function retrieves the device authentication type.
old-location: pos\ioctl_point_of_service_msr_retrieve_device_authentication.htm
tech.root: pos
ms.assetid: 6f086416-ab50-46fc-933e-a3d48c7dbf4c
ms.date: 02/23/2018
keywords: ["IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION control, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION, pos.ioctl_point_of_service_msr_retrieve_device_authentication
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION"
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
- IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL


## -description


This I/O control function retrieves the device authentication type.


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Pointer to a buffer that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data">MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</a>.


### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(<b>MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</b>).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




