---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_SO_STATISTICS
title: D3D10_DDI_QUERY_DATA_SO_STATISTICS (d3d10umddi.h)
description: The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_so_statistics.htm
ms.assetid: 641c8f8d-e398-4ca4-9e28-bba2ef7d1bd3
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_QUERY_DATA_SO_STATISTICS, D3D10_DDI_QUERY_DATA_SO_STATISTICS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3748a5db-9ce8-4763-baac-4110b754188d.xml, d3d10umddi/D3D10_DDI_QUERY_DATA_SO_STATISTICS, display.d3d10_ddi_query_data_so_statistics
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3D10_DDI_QUERY_DATA_SO_STATISTICS"
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
- D3D10_DDI_QUERY_DATA_SO_STATISTICS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_QUERY_DATA_SO_STATISTICS
---

# D3D10_DDI_QUERY_DATA_SO_STATISTICS structure


## -description


The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS 

query type and in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a> function to return information about the query. 


## -struct-fields




### -field NumPrimitivesWritten

The number of primitives that is written to the stream output resource. 


### -field PrimitivesStorageNeeded

The number of primitives that would have been written to the stream output resource if the resource was big enough. 


## -remarks



The driver associates a D3D10_DDI_QUERY_DATA_SO_STATISTICS structure with the D3D10DDI_QUERY_STREAMOUTPUTSTATS query type value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a> enumeration.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createquery">CreateQuery(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3d10ddi_query">D3D10DDI_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_querygetdata">QueryGetData</a>
 

 

