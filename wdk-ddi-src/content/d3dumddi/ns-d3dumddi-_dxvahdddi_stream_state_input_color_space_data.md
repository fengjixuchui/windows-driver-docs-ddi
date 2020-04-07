---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
title: _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure describes stream-state data that specifies the color space of the input stream.
old-location: display\dxvahdddi_stream_state_input_color_space_data.htm
tech.root: display
ms.assetid: cced26ea-bbb8-4716-b22d-8355b81102c0
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure"]
ms.keywords: DXVA2_Structs_4e403294-5aa5-4170-a635-567f89a34e8e.xml, DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA, DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA, display.dxvahdddi_stream_state_input_color_space_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
---

# _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure describes stream-state data that specifies the color space of the input stream. 


## -struct-fields




### -field Type

[in] A UINT value that specifies whether the input stream is video or graphics. The driver can optimize the processing and the filtering based on the stream type. The default value is 0, which indicates a video stream.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001). 


### -field RGB_Range

[in] A UINT value that specifies whether the input stream is full range RGB (that is, 0 to 255) or limited range RGB (that is, 16 to 235). The default value is 0, which indicates full range RGB.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002). 


### -field YCbCr_Matrix

[in] A UINT value that specifies whether the input stream is BT.601 (for standard digital television) or BT.709 (for high-definition television). The default value is 0, which indicates BT.601.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004). 


### -field YCbCr_xvYCC

[in] A UINT value that specifies whether the input stream is conventional YCbCr or extended YCbCr (xvYCC). The default is 0, which indicates conventional YCbCr.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008). 


### -field Nominal_Range

[in] A UINT value that specifies that the luminance range of YUV data is described by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_nominal_range">DXVAHDDDI_NOMINAL_RANGE</a> enumeration. The default is zero, which indicates the studio luminance range of 16 to 255, inclusive [16, 235].

For more information on luminance range, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/yuv-format-ranges">YUV format ranges in Windows 8.1</a>.

Setting this member is equivalent to setting the fifth and sixth bits of the 32-bit <b>Value</b> member (0x00000030).

Supported starting with Windows 8.1.


### -field Reserved

[in] Reserved. Must be zero.

This member is equivalent to the remaining 26 bits (0xFFFFFFC0) of the 32-bit <b>Value</b> member.


### -field Value

[in] A 32-bit value that describes stream-state data that specifies the color space of the input stream. 


## -remarks



If the driver does not set the DXVAHDDDI_DEVICE_CAPS_xvYCC value in the <b>DeviceCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, the driver ignores the <b>YCbCr_xvYCC</b> member.

Either RGB or YCbCr flags that correspond to the color space of the input format are referred. However, the driver might have to perform the intermediate color space conversion, in which case both RGB and YCbCr flags are referred.

For more information about the intermediate color space conversion, see the <b>InputFormatCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure.

For more information about color space, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_dxvahdddi_nominal_range">DXVAHDDDI_NOMINAL_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

