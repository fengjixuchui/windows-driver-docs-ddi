---
UID: NS:d3dhal._D3DHAL_DP2CREATEQUERY
title: _D3DHAL_DP2CREATEQUERY (d3dhal.h)
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2createquery.htm
tech.root: display
ms.assetid: 9998743d-57d5-4289-91c5-1c810bf4ca65
ms.date: 05/10/2018
keywords: ["_D3DHAL_DP2CREATEQUERY structure"]
ms.keywords: "*LPD3DHAL_DP2CREATEQUERY, D3DHAL_DP2CREATEQUERY, D3DHAL_DP2CREATEQUERY structure [Display Devices], LPD3DHAL_DP2CREATEQUERY, LPD3DHAL_DP2CREATEQUERY structure pointer [Display Devices], _D3DHAL_DP2CREATEQUERY, d3dhal/D3DHAL_DP2CREATEQUERY, d3dhal/LPD3DHAL_DP2CREATEQUERY, d3dstrct_d90487be-ec5e-416b-9ca8-fc431596cb27.xml, display.d3dhal_dp2createquery"
f1_keywords:
 - "d3dhal/D3DHAL_DP2CREATEQUERY"
req.header: d3dhal.h
req.include-header: D3dhal.h
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
- d3dhal.h
api_name:
- D3DHAL_DP2CREATEQUERY
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2CREATEQUERY
---

# _D3DHAL_DP2CREATEQUERY structure


## -description



   DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2CREATEQUERY structures are parsed from the command buffer by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_CREATEQUERY, and are used to create resources for queries.


## -struct-fields




### -field dwQueryID

Identifies the query.


### -field QueryType

Specifies a value from the D3DQUERYTYPE enumeration that indicates the query capability for which the driver creates resources.


## -remarks



The runtime uses D3DHAL_DP2CREATEQUERY to identify each query with a unique identifier and a query type. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2CREATEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and creates resources for the queries that they represent as necessary. 

The driver creates resources for the following query types:

<ul>
<li>
BOOL for D3DQUERYTYPE_EVENT. Before responding with D3DDP2OP_RESPONSEQUERY for an event, the driver must ensure that the graphics processing unit (GPU) is finished processing all <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ne-d3dhal-_d3dhal_dp2operation">D3DHAL_DP2OPERATION</a> operations that are related to the event. That is, the driver only responds after the event's ISSUE_END state occurs. The driver must always set the event's BOOL value to <b>TRUE</b> when responding.

</li>
<li>
DWORD for D3DQUERYTYPE_OCCLUSION. The driver sets this DWORD to the number of pixels for which the z-test passed for all primitives between the begin and end of the query. If the depth buffer is multisampled, the driver determines the number of pixels from the number of samples. However, if the display device is capable of per-multisample z-test accuracy, the conversion to number of pixels should generally be rounded up. An application can then check the occlusion result against 0, to effectively mean "fully occluded". Drivers that convert multisampled quantities to pixel quantities should detect render target multisampling changes and continue to compute the query results appropriately.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d9types/ns-d3d9types-_d3ddevinfo_vcache">D3DDEVINFO_VCACHE</a> structure for D3DQUERYTYPE_VCACHE.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d9types/ns-d3d9types-_d3ddevinfo_vcache">D3DDEVINFO_VCACHE</a>



D3DDP2OP_CREATEQUERY



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2deletequery">D3DHAL_DP2DELETEQUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>
 

 

