---
UID: NC:usbcamdi.PCAM_START_CAPTURE_ROUTINE_EX
title: PCAM_START_CAPTURE_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamStartCaptureEx callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camstartcaptureex.htm
tech.root: stream
ms.assetid: ab2222ed-3166-4984-b76c-5499879f91d5
ms.date: 04/23/2018
keywords: ["PCAM_START_CAPTURE_ROUTINE_EX callback function"]
ms.keywords: CamStartCaptureEx, CamStartCaptureEx routine [Streaming Media Devices], PCAM_START_CAPTURE_ROUTINE_EX, stream.camstartcaptureex, usbcamdi/CamStartCaptureEx, usbcmdpr_b6e64f48-1afd-40b0-adbe-dc5afb83d045.xml
f1_keywords:
 - "usbcamdi/CamStartCaptureEx"
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
- UserDefined
api_location:
- usbcamdi.h
api_name:
- CamStartCaptureEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCAM_START_CAPTURE_ROUTINE_EX callback function


## -description


A camera minidriver's <b>CamStartCaptureEx</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param StreamNumber

Indicates the stream number.


## -returns



<b>CamStartCaptureEx</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.




## -remarks



The original USBCAMD does not call <b>CamStartCaptureEx</b>.

This function is required.



