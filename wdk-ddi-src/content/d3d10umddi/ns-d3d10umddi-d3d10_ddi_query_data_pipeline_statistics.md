---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
title: D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS (d3d10umddi.h)
description: The D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_pipeline_statistics.htm
ms.assetid: 5e481453-1e01-46b4-a04e-e9c575cd65b9
ms.date: 05/10/2018
keywords: ["D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure"]
ms.keywords: D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS, D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_66e61d2d-0a0d-41aa-a25d-a7fa3ef08b4c.xml, d3d10umddi/D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS, display.d3d10_ddi_query_data_pipeline_statistics
f1_keywords:
 - "d3d10umddi/D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS"
 - "D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS"
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
- D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
---

# D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure


## -description


The D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function to return information about the query. 


## -struct-fields




### -field IAVertices

The number of input assembler (IA) veritces. 


### -field IAPrimitives

The number of IA primitives. 


### -field VSInvocations

The number of vertex shader (VS) invocations. 


### -field GSInvocations

The number of geometry shader (GS) invocations. 


### -field GSPrimitives

The number of GS primitives. 


### -field CInvocations

The number of clipper invocations. 


### -field CPrimitives

The number of clipper primitives. 


### -field PSInvocations

The number of pixel shader (PS) invocations. 


## -remarks



The driver associates a D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure with the D3D10DDI_QUERY_PIPELINESTATS query type value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a> enumeration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a>
 

 

