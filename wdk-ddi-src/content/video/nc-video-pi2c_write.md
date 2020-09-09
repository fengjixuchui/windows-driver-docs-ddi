---
UID: NC:video.PI2C_WRITE
title: PI2C_WRITE (video.h)
description: The I2CWrite function writes data over the I2C channel.
old-location: display\i2cwrite.htm
tech.root: display
ms.assetid: 5aaebf38-bc09-4fb5-969e-7b456773d5ac
ms.date: 05/10/2018
keywords: ["PI2C_WRITE callback function"]
ms.keywords: I2CWrite, I2CWrite callback function [Display Devices], PI2C_WRITE, PI2C_WRITE callback, VideoPort_Functions_3e35f4d8-7c13-4c2c-b0e4-c518bc63e6f6.xml, display.i2cwrite, video/I2CWrite
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PI2C_WRITE
 - video/PI2C_WRITE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - I2CWrite
---

# PI2C_WRITE callback function


## -description

The <i>I2CWrite</i> function writes data over the <a href="https://docs.microsoft.com/windows-hardware/drivers/">I2C</a> channel.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's per-adapter device extension.

### -param I2CCallbacks 

[in]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_i2c_callbacks">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.

### -param Buffer 

[in]
Pointer to the data to be written.

### -param Length 

[in]
Specifies the number of bytes to be written.

## -returns

<i>I2CWrite</i> returns <b>TRUE</b> if the data was successfully written, and <b>FALSE</b> otherwise.

## -remarks

The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a>

