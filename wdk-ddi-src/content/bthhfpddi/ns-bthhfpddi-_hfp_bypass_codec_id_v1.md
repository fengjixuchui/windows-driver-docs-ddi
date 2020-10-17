---
UID: NS:bthhfpddi._HFP_BYPASS_CODEC_ID_V1
title: _HFP_BYPASS_CODEC_ID_V1 (bthhfpddi.h)
description: The HFP_BYPASS_CODEC_ID_V1 structure defines version 1 of the supported codec ID structure.
old-location: audio\hfp_bypass_codec_id_v1.htm
tech.root: audio
ms.assetid: FB618271-A1E9-4F47-97DC-F4ACAA01028C
ms.date: 05/08/2018
keywords: ["HFP_BYPASS_CODEC_ID_V1 structure"]
ms.keywords: "*PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1 structure [Audio Devices], PHFP_BYPASS_CODEC_ID_V1, PHFP_BYPASS_CODEC_ID_V1 structure pointer [Audio Devices], _HFP_BYPASS_CODEC_ID_V1, audio.hfp_bypass_codec_id_v1, bthhfpddi/HFP_BYPASS_CODEC_ID_V1, bthhfpddi/PHFP_BYPASS_CODEC_ID_V1"
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
f1_keywords:
 - _HFP_BYPASS_CODEC_ID_V1
 - bthhfpddi/_HFP_BYPASS_CODEC_ID_V1
 - PHFP_BYPASS_CODEC_ID_V1
 - bthhfpddi/PHFP_BYPASS_CODEC_ID_V1
 - HFP_BYPASS_CODEC_ID_V1
 - bthhfpddi/HFP_BYPASS_CODEC_ID_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthhfpddi.h
api_name:
 - HFP_BYPASS_CODEC_ID_V1
---

# _HFP_BYPASS_CODEC_ID_V1 structure


## -description

The HFP_BYPASS_CODEC_ID_V1 structure defines version 1 of the supported codec ID structure.

## -struct-fields

### -field CodecId

The codec ID can be any of the values in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0</td>
<td>Undefined codec</td>
</tr>
<tr>
<td>1</td>
<td>CVSD codec (narrow band) </td>
</tr>
<tr>
<td>2</td>
<td>mSBC codec (wide band speech)</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/bthhfpddi/ne-bthhfpddi-_hfp_bypass_codec_id_version">HFP_BYPASS_CODEC_ID_VERSION</a>



<a href="/windows-hardware/drivers/ddi/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_codec_id">IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</a>