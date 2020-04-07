---
UID: NS:d3d10umddi.D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
title: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY (d3d10umddi.h)
description: The D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.
old-location: display\d3d10ddiarg_stream_output_declaration_entry.htm
ms.assetid: 42d01b63-ca3b-4348-bf50-a1d648548266
ms.date: 05/10/2018
keywords: ["D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure"]
ms.keywords: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY, D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_bdfafade-cf99-4cbb-9ae1-d1bd57997dac.xml, d3d10umddi/D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY, display.d3d10ddiarg_stream_output_declaration_entry
f1_keywords:
 - "d3d10umddi/D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY
---

# D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure


## -description


The D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY structure describes a portion of the stream output for a geometry shader.


## -struct-fields




### -field OutputSlot

[in] The number of the slot for the portion of the stream output. 


### -field RegisterIndex

[in] The number of the register for the portion of the stream output.


### -field RegisterMask

[in] The xyzw register mask for the portion of the stream output. That is, the four least signifigant bits (LSBs) of the mask represent xyzw respectively. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_creategeometryshaderwithstreamoutput">D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>
 

 

