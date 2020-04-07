---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 (d3d12umddi.h)
description: Defines the deinterlacing video processor capabilities.
old-location: display\d3d12ddi_video_process_deinterlace_flags.htm
ms.assetid: 7E34CCE5-A771-4EBE-A09B-79424405BFF3
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 enumeration"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_BOB, D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_CUSTOM, D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020, d3d12umddi/D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_BOB, d3d12umddi/D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_CUSTOM, d3d12umddi/D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_NONE, display.d3d12ddi_video_process_deinterlace_flags
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 enumeration


## -description


Defines the deinterlacing video processor capabilities.


## -enum-fields




### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_NONE

No deinterlacing.


### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_BOB

The video processor can perform bob deinterlacing. In bob deinterlacing, missing field lines are interpolated from the lines above and below. Bob deinterlacing does not require reference frames.


### -field D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAG_0020_CUSTOM

The video processor can perform a custom high quality deinterlacing. This feature requires the number of reference frames indicated in [D3D12DDI_VIDEO_DECODE_REFERENCE_FRAMES_0032](ns-d3d12umddi-d3d12ddi_video_decode_reference_frames_0032.md). If the video processor does not have the necessary number of reference frames, it falls back to bob deinterlacing.

