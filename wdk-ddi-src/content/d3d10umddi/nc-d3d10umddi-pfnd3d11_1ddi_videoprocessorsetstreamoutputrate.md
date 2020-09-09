---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE (d3d10umddi.h)
description: Sets the rate at which the video processor produces output frames for an input stream.
old-location: display\videoprocessorsetstreamoutputrate.htm
ms.assetid: fc1236f2-fcbf-4b3f-978f-a34260b78159
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback, d3d10umddi/pfnVideoProcessorSetStreamOutputRate, display.videoprocessorsetstreamoutputrate, pfnVideoProcessorSetStreamOutputRate, pfnVideoProcessorSetStreamOutputRate callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamOutputRate
product:
 - Windows
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback function


## -description

Sets the rate at which the video processor produces output frames for an input stream.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*RepeatFrame* [in]

Specifies how the driver performs frame-rate conversion, if it is required.



If the <i>RepeatFrame</i> parameter is <b>TRUE</b>,  the driver should repeat frames. 



If the <i>RepeatFrame</i> parameter is <b>FALSE</b>,  the driver should interpolate frames.

<div class="alert"><b>Note</b>  If the <b>VideoProcessorSetStreamOutputRate</b> function is never called, the driver should interpolate frames by default.</div>
<div> </div>

### -param Arg5

*OutputRate* [in]

The output rate, specified as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a> value.

For more information, see the Remarks section.

### -param Arg6

*pCustomRate* [in]

A pointer to a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure. If the <i>OutputRate</i> parameter is set to <b>D3D11_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM</b>, this parameter specifies the exact output rate. Otherwise, this parameter is ignored and can be set to NULL.

## -remarks

The standard output rates that are defined by  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a> enumeration values are normal frame-rate (<b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL</b>) and half frame-rate (<b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF</b>). 

If the driver supports custom rates for rate conversion or inverse telecine, it can use a custom rate if the <i>OutputRate</i> parameter is set to <b>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM</b>. The custom rate is specified by the <i>pCustomRate</i> parameter.

<div class="alert"><b>Note</b>  The driver reports its custom rates  in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate">GetVideoProcessorCustomRate</a> function.

</div>
<div> </div>
Depending on the output rate, the driver might have to convert the frame rate. If so, the value of the <i>RepeatFrame</i> parameter controls whether the driver creates interpolated frames or repeats input frames.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate">D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate">GetVideoProcessorCustomRate</a>

