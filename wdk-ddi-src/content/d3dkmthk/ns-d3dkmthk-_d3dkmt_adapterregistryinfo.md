---
UID: NS:d3dkmthk._D3DKMT_ADAPTERREGISTRYINFO
title: _D3DKMT_ADAPTERREGISTRYINFO (d3dkmthk.h)
description: The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.
old-location: display\d3dkmt_adapterregistryinfo.htm
ms.assetid: b1bad6e8-8592-457a-8f66-40fc5040ae96
ms.date: 05/10/2018
keywords: ["D3DKMT_ADAPTERREGISTRYINFO structure"]
ms.keywords: D3DKMT_ADAPTERREGISTRYINFO, D3DKMT_ADAPTERREGISTRYINFO structure [Display Devices], OpenGL_Structs_0d97d602-7fc3-40a2-aa06-2966a6fc04f7.xml, _D3DKMT_ADAPTERREGISTRYINFO, d3dkmthk/D3DKMT_ADAPTERREGISTRYINFO, display.d3dkmt_adapterregistryinfo
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
tech.root: display
req.typenames: D3DKMT_ADAPTERREGISTRYINFO
f1_keywords:
 - _D3DKMT_ADAPTERREGISTRYINFO
 - d3dkmthk/_D3DKMT_ADAPTERREGISTRYINFO
 - D3DKMT_ADAPTERREGISTRYINFO
 - d3dkmthk/D3DKMT_ADAPTERREGISTRYINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_ADAPTERREGISTRYINFO
---

# _D3DKMT_ADAPTERREGISTRYINFO structure


## -description

The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.

## -struct-fields

### -field AdapterString

[out] A string that contains the name of the graphics adapter.

### -field BiosString

[out] A string that contains the name of the BIOS for the graphics adapter.

### -field DacType

[out] A string that contains the DAC type for the graphics adapter.

### -field ChipType

[out] A string that contains the chip type for the graphics adapter.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>

