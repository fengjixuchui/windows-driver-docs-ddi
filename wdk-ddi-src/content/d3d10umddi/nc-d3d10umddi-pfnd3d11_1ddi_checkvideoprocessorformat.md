---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT
title: PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT (d3d10umddi.h)
description: Queries whether the video processor supports a specified video format.
old-location: display\checkvideoprocessorformat.htm
ms.assetid: f5f18a53-d121-445a-86b7-649624a2f175
ms.date: 05/10/2018
ms.keywords: CheckVideoProcessorFormat, CheckVideoProcessorFormat callback function [Display Devices], PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT, PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT callback, d3d10umddi/CheckVideoProcessorFormat, display.checkvideoprocessorformat
ms.topic: callback
f1_keywords:
 - "d3d10umddi/CheckVideoProcessorFormat"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- CheckVideoProcessorFormat
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT callback function


## -description


Queries whether the video processor supports a specified video format.


## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessorEnum* [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function. 

### -param Arg3

*Format* [in]

The video format to query.

### -param *

*pSupported* [out]

Specifies a bitwise OR of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_format_support">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT</a> enumeration.

For more information, see the Remarks section.


## -returns



This callback function does not return a value.




## -remarks



If the driver can support the format as an input format for the video processor, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support the format as a video processing render target output format, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support neither, it must set the <i>pSupported</i> parameter to 0.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_format_support">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT</a>
 

 

